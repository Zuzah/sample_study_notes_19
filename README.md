# sample_study_notes_19
AML/KYC help

mainifst

```python
import csv
import json
from datetime import datetime, timezone
from pathlib import Path

from app.core.logging import log


class ManifestService:
    """Structured JSON manifest (.mrk) sidecar, for reports that need a
    downstream ingestion-framework manifest instead of a SHA256 checksum (see
    marker_service.py). Opt in via ReportDefinition.marker_type. One shape
    built so far (Fircosoft's contract) - a different shape gets its own
    create_*_for_file method here, not a parameter on this one."""

    @staticmethod
    def _record_count(csv_path: Path) -> int:
        with csv_path.open("r", encoding="utf-8", newline="") as stream:
            reader = csv.reader(stream)
            next(reader, None)  # header row
            return sum(1 for _ in reader)

    @staticmethod
    def _render_fields(fields: dict, indent: int) -> str:
        pad = " " * indent
        lines = [
            f"{pad}{json.dumps(str(k))}: {json.dumps(str(v))}"
            for k, v in fields.items()
        ]
        return ",\n".join(lines) + "\n"

    @classmethod
    def create_fircosoft_manifest_for_file(
        cls,
        source_file_path: Path,
        source_appl: dict,
        source_file_static: dict,
    ) -> Path:
        # dataFileURI = the real resolved filename, never an independently
        # templated string that could drift from what's actually delivered.
        source_file_path = Path(source_file_path)
        if not source_file_path.exists():
            raise FileNotFoundError(f"Source file not found: {source_file_path}")

        date_stamp = datetime.now(timezone.utc).strftime("%Y%m%d")
        record_count = cls._record_count(source_file_path)

        source_appl = {**source_appl, "buste": date_stamp}
        source_file = dict(source_file_static)
        source_file["recordCount"] = str(record_count)
        source_file["dataFileURI"] = source_file_path.name

        # Hand-built, not json.dumps(indent=N): the real Fircosoft sample
        # (sample_edl_mark.csv.mrk) uses a non-standard, asymmetric layout -
        # 4-space indent, no space before "{"/"[", and sourceFiles' one-object
        # array collapsed onto one opening line with its closing brace
        # outdented to match - no standard pretty-printer option produces this.
        manifest_text = (
            "{\n"
            '    "specVersion": "2.0",\n'
            '    "sourceAppl":{\n'
            + cls._render_fields(source_appl, indent=8)
            + "    },\n"
            '    "sourceFiles":[{\n'
            + cls._render_fields(source_file, indent=12)
            + "    }]\n"
            "}\n"
        )

        manifest_path = Path(str(source_file_path) + ".mrk")
        manifest_path.write_text(manifest_text, encoding="utf-8")
        log.info(f"Fircosoft manifest generated successfully: {manifest_path}")
        return manifest_path

```

tests/services/test_manifest_service.py:

```python
import json
from datetime import datetime, timezone
from pathlib import Path

import pytest

from app.services.manifest_service import ManifestService

SOURCE_APPL = {
    "providingParty": "gbm",
    "country": "can",
    "region": "nam",
    "appAcronym": "b8fb",
    "frequency": "dly",
    "securityClassification": "cpi",
    "operation": "f",
    "ingestionFramework": "y",
    "fileTransfer": "push",
}
SOURCE_FILE_STATIC = {
    "dataRention": "",
    "compressType": "",
    "ingestMetadata": "Fircosoft_EDL_Metadata_V8.xml",
    "fileCompressed": "n",
    "toCharSet": "",
    "recordCount": "",
    "dataFileMD5": "",
    "fromCharSet": "",
    "invalidRecordThreshold": "0",
    "fileExtension": "csv",
    "dataFileURI": "",
    "charSetConv": "n",
}


def _csv(tmp_path, rows):
    path = tmp_path / "Fircosoft_Fcore_EDL_Data_20261008.csv"
    lines = ["Fenergo ID,Legal Entity Name"] + rows
    path.write_text("\n".join(lines) + "\n")
    return path


def test_create_fircosoft_manifest_for_file_builds_correct_json(tmp_path):
    csv_path = _csv(tmp_path, ["1,Acme Corp", "2,Beta Inc", "3,Gamma LLC"])

    marker_path = ManifestService.create_fircosoft_manifest_for_file(
        csv_path, SOURCE_APPL, SOURCE_FILE_STATIC
    )

    manifest = json.loads(marker_path.read_text())
    today = datetime.now(timezone.utc).strftime("%Y%m%d")

    assert manifest["specVersion"] == "2.0"
    assert manifest["sourceAppl"]["buste"] == today
    assert manifest["sourceAppl"]["providingParty"] == "gbm"
    assert manifest["sourceAppl"]["appAcronym"] == "b8fb"
    source_file = manifest["sourceFiles"][0]
    assert source_file["recordCount"] == "3"
    assert source_file["dataFileURI"] == "Fircosoft_Fcore_EDL_Data_20261008.csv"
    assert source_file["ingestMetadata"] == "Fircosoft_EDL_Metadata_V8.xml"
    assert source_file["fileExtension"] == "csv"


def test_create_fircosoft_manifest_for_file_counts_only_data_rows_not_header(
    tmp_path,
):
    csv_path = _csv(tmp_path, ["1,Acme Corp"])

    marker_path = ManifestService.create_fircosoft_manifest_for_file(
        csv_path, SOURCE_APPL, SOURCE_FILE_STATIC
    )

    manifest = json.loads(marker_path.read_text())
    assert manifest["sourceFiles"][0]["recordCount"] == "1"


def test_create_fircosoft_manifest_for_file_dataFileURI_matches_real_filename(
    tmp_path,
):
    """dataFileURI must always equal the real delivered filename - never an
    independently-templated string that could drift from what's actually sent."""
    csv_path = tmp_path / "some_other_name.csv"
    csv_path.write_text("Fenergo ID\n1\n")

    marker_path = ManifestService.create_fircosoft_manifest_for_file(
        csv_path, SOURCE_APPL, SOURCE_FILE_STATIC
    )

    manifest = json.loads(marker_path.read_text())
    assert manifest["sourceFiles"][0]["dataFileURI"] == "some_other_name.csv"


def test_create_fircosoft_manifest_for_file_preserves_field_order(tmp_path):
    """recordCount/dataFileURI land at whatever position SOURCE_FILE_STATIC
    declares them at (toCharSet->recordCount, fileExtension->dataFileURI->
    charSetConv), matching the real sample manifest byte for byte - not
    appended at the end."""
    csv_path = _csv(tmp_path, ["1,Acme Corp"])

    marker_path = ManifestService.create_fircosoft_manifest_for_file(
        csv_path, SOURCE_APPL, SOURCE_FILE_STATIC
    )

    manifest = json.loads(marker_path.read_text())
    keys = list(manifest["sourceFiles"][0].keys())
    assert keys == [
        "dataRention",
        "compressType",
        "ingestMetadata",
        "fileCompressed",
        "toCharSet",
        "recordCount",
        "dataFileMD5",
        "fromCharSet",
        "invalidRecordThreshold",
        "fileExtension",
        "dataFileURI",
        "charSetConv",
    ]


def test_create_fircosoft_manifest_for_file_matches_expected_formatting(tmp_path):
    """Exact format Fircosoft's ingestion team confirmed correct (feedback
    2026-10-20) - 4-space indent, no space before "{"/"[", sourceFiles' one-
    object array collapsed onto its opening line with the closing brace
    outdented to match. None of this is producible via json.dumps(indent=N),
    so this guards against silently drifting back to standard pretty-printing.
    Expected text is inlined here rather than loaded from a reference file -
    the one used to originally confirm this (sample_edl_mark.csv.mrk) isn't
    meant to stay in the repo long-term."""
    csv_path = _csv(tmp_path, ["1,Acme Corp", "2,Beta Inc"])

    marker_path = ManifestService.create_fircosoft_manifest_for_file(
        csv_path, SOURCE_APPL, SOURCE_FILE_STATIC
    )

    today = datetime.now(timezone.utc).strftime("%Y%m%d")
    expected = (
        "{\n"
        '    "specVersion": "2.0",\n'
        '    "sourceAppl":{\n'
        '        "providingParty": "gbm",\n'
        '        "country": "can",\n'
        '        "region": "nam",\n'
        '        "appAcronym": "b8fb",\n'
        '        "frequency": "dly",\n'
        '        "securityClassification": "cpi",\n'
        '        "operation": "f",\n'
        '        "ingestionFramework": "y",\n'
        '        "fileTransfer": "push",\n'
        f'        "buste": "{today}"\n'
        "    },\n"
        '    "sourceFiles":[{\n'
        '            "dataRention": "",\n'
        '            "compressType": "",\n'
        '            "ingestMetadata": "Fircosoft_EDL_Metadata_V8.xml",\n'
        '            "fileCompressed": "n",\n'
        '            "toCharSet": "",\n'
        '            "recordCount": "2",\n'
        '            "dataFileMD5": "",\n'
        '            "fromCharSet": "",\n'
        '            "invalidRecordThreshold": "0",\n'
        '            "fileExtension": "csv",\n'
        '            "dataFileURI": "Fircosoft_Fcore_EDL_Data_20261008.csv",\n'
        '            "charSetConv": "n"\n'
        "    }]\n"
        "}\n"
    )

    assert marker_path.read_text() == expected


def test_create_fircosoft_manifest_for_file_raises_when_source_missing():
    with pytest.raises(FileNotFoundError):
        ManifestService.create_fircosoft_manifest_for_file(
            Path("/tmp/does_not_exist_edl.csv"), SOURCE_APPL, SOURCE_FILE_STATIC
        )


def test_create_fircosoft_manifest_for_file_returns_mrk_path(tmp_path):
    csv_path = _csv(tmp_path, ["1,Acme Corp"])

    marker_path = ManifestService.create_fircosoft_manifest_for_file(
        csv_path, SOURCE_APPL, SOURCE_FILE_STATIC
    )

    assert marker_path.name == "Fircosoft_Fcore_EDL_Data_20261008.csv.mrk"
```
