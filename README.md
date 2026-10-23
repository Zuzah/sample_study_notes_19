# sample_study_notes_19
AML/KYC help


assets/templates/Fenergo_RegCentral.xml:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<ExtractConfig ExtractType="CSV" DateFormat="M/d/yyyy h:mm:ss tt" MaxRetry="5">
    <RecordTemplate>
        <Column Assignment="1" Source="fenergo_id" Target="fenergo_id" DataType="String" />
        <Column Assignment="2" Source="legal_entity_name" Target="legal_entity_name" DataType="String" />
        <Column Assignment="3" Source="pca_principal_type_df" Target="pca_principal_type_df" DataType="String" />
        <Column Assignment="4" Source="pca_principal_type_cdn" Target="pca_principal_type_cdn" DataType="String" />
        <Column Assignment="5" Source="fin_entity_protocol_1" Target="fin_entity_protocol_1" DataType="String" />
        <Column Assignment="6" Source="fin_entity_protocol_2" Target="fin_entity_protocol_2" DataType="String" />
        <Column Assignment="7" Source="clearing_category" Target="clearing_category" DataType="String" />
        <Column Assignment="8" Source="elected_end_user_exception_type" Target="elected_end_user_exception_type" DataType="String" />
        <Column Assignment="9" Source="country_of_incorp_establishment" Target="country_of_incorp_establishment" DataType="String" />
        <Column Assignment="10" Source="conduit_affiliate_representation_2013" Target="conduit_affiliate_representation_2013" DataType="String" />
        <Column Assignment="11" Source="guarantee_representations_2013" Target="guarantee_representations_2013" DataType="String" />
        <Column Assignment="12" Source="legal_entity_type" Target="legal_entity_type" DataType="String" />
        <Column Assignment="13" Source="agrmt_to_rpting_party_rules" Target="agrmt_to_rpting_party_rules" DataType="String" />
        <Column Assignment="14" Source="registered_derivatives_dealer_in_canada" Target="registered_derivatives_dealer_in_canada" DataType="String" />
        <Column Assignment="15" Source="cad_person_representation" Target="cad_person_representation" DataType="String" />
        <Column Assignment="16" Source="juris_of_incorp_ho_ppb" Target="juris_of_incorp_ho_ppb" DataType="String" />
        <Column Assignment="17" Source="clearing_exception" Target="clearing_exception" DataType="String" />
        <Column Assignment="18" Source="master_agrmt_type" Target="master_agrmt_type" DataType="String" />
        <Column Assignment="19" Source="counterparty_LEI" Target="counterparty_LEI" DataType="String" />
        <Column Assignment="20" Source="canadian_reporting_requirements_completed" Target="canadian_reporting_requirements_completed" DataType="String" />
        <Column Assignment="21" Source="ISDA _August_2012_DF_Protocol _(Protocol 1)_Adherence" Target="ISDA _August_2012_DF_Protocol _(Protocol 1)_Adherence" DataType="String" />
        <Column Assignment="22" Source="ISDA_March_2013_DF_Protocol_(Protocol 2)_Adherence" Target="ISDA_March_2013_DF_Protocol_(Protocol 2)_Adherence" DataType="String" />
        <Column Assignment="23" Source="EMIR_ISDA_protocol_adherence" Target="EMIR_ISDA_protocol_adherence" DataType="String" />
        <Column Assignment="24" Source="delegated_reporting" Target="delegated_reporting" DataType="String" />
        <Column Assignment="25" Source="consent_to_disclosure" Target="consent_to_disclosure" DataType="String" />
        <Column Assignment="26" Source="client_consent_to_trade_reporting" Target="client_consent_to_trade_reporting" DataType="String" />
        <Column Assignment="27" Source="affiliate_of_a_responsible_canadian_person" Target="affiliate_of_a_responsible_canadian_person" DataType="String" />
        <Column Assignment="28" Source="multilateral_agreement_dealers_cdn" Target="multilateral_agreement_dealers_cdn" DataType="String" />
        <Column Assignment="29" Source="addl_covenant_rpting_resp" Target="addl_covenant_rpting_resp" DataType="String" />
        <Column Assignment="30" Source="enterprise_SIC" Target="enterprise_SIC" DataType="String" />
        <Column Assignment="31" Source="primary_business_location" Target="primary_business_location" DataType="String" />
        <Column Assignment="32" Source="above_local_cparty_threshold" Target="above_local_cparty_threshold" DataType="String" />
        <Column Assignment="33" Source="above_participant_aff_threshold" Target="above_participant_aff_threshold" DataType="String" />
        <Column Assignment="34" Source="participant_of_clearing_agency" Target="participant_of_clearing_agency" DataType="String" />
        <Column Assignment="35" Source="crown_corp" Target="crown_corp" DataType="String" />
        <Column Assignment="36" Source="us_prsn_rep_cftc_2013" Target="us_prsn_rep_cftc_2013" DataType="String" />
        <Column Assignment="37" Source="swap_entity_significant_risk_subsidiary" Target="swap_entity_significant_risk_subsidiary" DataType="String" />
        <Column Assignment="38" Source="us_person_guarantees_cftc_2020" Target="us_person_guarantees_cftc_2020" DataType="String" />
        <Column Assignment="39" Source="jurisdiction_registered_derivatives_dealer" Target="jurisdiction_registered_derivatives_dealer" DataType="String" />
        <Column Assignment="40" Source="Jurisdiction_affiliate_responsible_canadian_person" Target="Jurisdiction_affiliate_responsible_canadian_person" DataType="String" />
        <Column Assignment="41" Source="consent_to_all_reporting_requirements" Target="consent_to_all_reporting_requirements" DataType="String" />
        <Column Assignment="42" Source="named_entity_natural_person_resident_entity_us" Target="named_entity_natural_person_resident_entity_us" DataType="String" />
        <Column Assignment="43" Source="us_person_representation_cftc_sec_2020" Target="us_person_representation_cftc_sec_2020" DataType="String" />
        <Column Assignment="44" Source="swaps_recipient_us_branch" Target="swaps_recipient_us_branch" DataType="String" />
        <Column Assignment="45" Source="swaps_recipient_foreign_branch" Target="swaps_recipient_foreign_branch" DataType="String" />
        <Column Assignment="46" Source="active_flag" Target="active_flag" DataType="String" />
        <Column Assignment="47" Source="Named_Entity_any_of_the_following" Target="Named_Entity_any_of_the_following" DataType="String" />
        <Column Assignment="48" Source="Jurisdiction_addl_covenant_rpting_resp" Target="Jurisdiction_addl_covenant_rpting_resp" DataType="String" />
        <Column Assignment="49" Source="cander_delegated_reporting" Target="cander_delegated_reporting" DataType="String" />
        <Column Assignment="50" Source="registered_state/county" Target="registered_state/county" DataType="String" />
        <Column Assignment="51" Source="headquarters_state/county" Target="headquarters_state/county" DataType="String" />
        <Column Assignment="52" Source="principal_place_of_business_state/county" Target="principal_place_of_business_state/county" DataType="String" />
        <Column Assignment="53" Source="fei" Target="fei" DataType="String" />
        <Column Assignment="54" Source="sec_delegate_reporting" Target="sec_delegate_reporting" DataType="String" />
        <Column Assignment="55" Source="client_an_investment_fund_or_specified_entity" Target="client_an_investment_fund_or_specified_entity" DataType="String" />
    </RecordTemplate>
</ExtractConfig>

```
