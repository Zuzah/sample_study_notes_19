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
