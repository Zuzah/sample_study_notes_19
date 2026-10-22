# sample_study_notes_19
AML/KYC help


assets/templates/CCD_Email.xml:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<!-- Source=Target deliberately identical for now - real Target renames come later,
     once transform is actually needed (see docs/decisions.md). -->
<ExtractConfig ExtractType="CSV" DateFormat="M/d/yyyy h:mm:ss tt" MaxRetry="5">
    <RecordTemplate>
        <Column Assignment="1" Source="FID" Target="FID" DataType="String" />
        <Column Assignment="2" Source="DF Protocol 1 Email" Target="DF Protocol 1 Email" DataType="String" />
        <Column Assignment="3" Source="DF Protocol 2 Email" Target="DF Protocol 2 Email" DataType="String" />
    </RecordTemplate>
</ExtractConfig>

```

assets/templates/CCD.xml:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<!-- Source=Target deliberately identical for now - real Target renames come later,
     once transform is actually needed (see docs/decisions.md). -->
<ExtractConfig ExtractType="CSV" DateFormat="M/d/yyyy h:mm:ss tt" MaxRetry="5">
    <RecordTemplate>
        <Column Assignment="1" Source="FenergoId" Target="FenergoId" DataType="String" />
        <Column Assignment="2" Source="LegalEntityName" Target="LegalEntityName" DataType="String" />
        <Column Assignment="3" Source="LegalEntitySubtype" Target="LegalEntitySubtype" DataType="String" />
        <Column Assignment="4" Source="LegalEntitySubtypeId" Target="LegalEntitySubtypeId" DataType="String" />
        <Column Assignment="5" Source="CountryOfIncorporation" Target="CountryOfIncorporation" DataType="String" />
        <Column Assignment="6" Source="BookingPoint" Target="BookingPoint" DataType="String" />
        <Column Assignment="7" Source="PrimaryBusinessLocation" Target="PrimaryBusinessLocation" DataType="String" />
        <Column Assignment="8" Source="AssetManager" Target="AssetManager" DataType="String" />
        <Column Assignment="9" Source="ParentLEInFenergo" Target="ParentLEInFenergo" DataType="String" />
        <Column Assignment="10" Source="AVID" Target="AVID" DataType="String" />
        <Column Assignment="11" Source="LEI" Target="LEI" DataType="String" />
        <Column Assignment="12" Source="DateOfIncorporation" Target="DateOfIncorporation" DataType="String" />
        <Column Assignment="13" Source="NAICS_Code" Target="NAICS_Code" DataType="String" />
        <Column Assignment="14" Source="NAICS_Description" Target="NAICS_Description" DataType="String" />
        <Column Assignment="15" Source="SIC_ParentCode" Target="SIC_ParentCode" DataType="String" />
        <Column Assignment="16" Source="SIC_EnterpriseCode" Target="SIC_EnterpriseCode" DataType="String" />
        <Column Assignment="17" Source="SIC_USCode" Target="SIC_USCode" DataType="String" />
        <Column Assignment="18" Source="SIC_Description" Target="SIC_Description" DataType="String" />
        <Column Assignment="19" Source="RegulatedBy" Target="RegulatedBy" DataType="String" />
        <Column Assignment="20" Source="OPAdd_Street" Target="OPAdd_Street" DataType="String" />
        <Column Assignment="21" Source="OPAdd_Building" Target="OPAdd_Building" DataType="String" />
        <Column Assignment="22" Source="OPAdd_City" Target="OPAdd_City" DataType="String" />
        <Column Assignment="23" Source="OPAdd_State" Target="OPAdd_State" DataType="String" />
        <Column Assignment="24" Source="OPAdd_Postal_Code" Target="OPAdd_Postal_Code" DataType="String" />
        <Column Assignment="25" Source="OPAdd_Country" Target="OPAdd_Country" DataType="String" />
        <Column Assignment="26" Source="RegAdd_STREET" Target="RegAdd_STREET" DataType="String" />
        <Column Assignment="27" Source="RegAdd_BUILDING" Target="RegAdd_BUILDING" DataType="String" />
        <Column Assignment="28" Source="RegAdd_CITY" Target="RegAdd_CITY" DataType="String" />
        <Column Assignment="29" Source="RegAdd_STATE" Target="RegAdd_STATE" DataType="String" />
        <Column Assignment="30" Source="RegAdd_POSTAL_CODE" Target="RegAdd_POSTAL_CODE" DataType="String" />
        <Column Assignment="31" Source="RegAdd_COUNTRY" Target="RegAdd_COUNTRY" DataType="String" />
        <Column Assignment="32" Source="CRS_Exempt" Target="CRS_Exempt" DataType="String" />
        <Column Assignment="33" Source="CRS_ExemptType" Target="CRS_ExemptType" DataType="String" />
        <Column Assignment="34" Source="CRS_Status" Target="CRS_Status" DataType="String" />
        <Column Assignment="35" Source="CRS_AccountHolderTaxRegimeType" Target="CRS_AccountHolderTaxRegimeType" DataType="String" />
        <Column Assignment="36" Source="CRS_AccountHolderTaxREGIMESTATUS" Target="CRS_AccountHolderTaxREGIMESTATUS" DataType="String" />
        <Column Assignment="37" Source="TIN1" Target="TIN1" DataType="String" />
        <Column Assignment="38" Source="TIN1_IssuingCountry" Target="TIN1_IssuingCountry" DataType="String" />
        <Column Assignment="39" Source="TIN1_ResidentCountry" Target="TIN1_ResidentCountry" DataType="String" />
        <Column Assignment="40" Source="TIN1_ResidentCountryCertificationStatus" Target="TIN1_ResidentCountryCertificationStatus" DataType="String" />
        <Column Assignment="41" Source="TIN2" Target="TIN2" DataType="String" />
        <Column Assignment="42" Source="TIN2_IssuingCountry" Target="TIN2_IssuingCountry" DataType="String" />
        <Column Assignment="43" Source="TIN2_ResidentCountry" Target="TIN2_ResidentCountry" DataType="String" />
        <Column Assignment="44" Source="TIN2_ResidentCountryCertificationStatus" Target="TIN2_ResidentCountryCertificationStatus" DataType="String" />
        <Column Assignment="45" Source="TIN3" Target="TIN3" DataType="String" />
        <Column Assignment="46" Source="TIN3_IssuingCountry" Target="TIN3_IssuingCountry" DataType="String" />
        <Column Assignment="47" Source="TIN3_ResidentCountry" Target="TIN3_ResidentCountry" DataType="String" />
        <Column Assignment="48" Source="TIN3_ResidentCountryCertificationStatus" Target="TIN3_ResidentCountryCertificationStatus" DataType="String" />
        <Column Assignment="49" Source="OwnershipType" Target="OwnershipType" DataType="String" />
        <Column Assignment="50" Source="CH3_TaxEntityType" Target="CH3_TaxEntityType" DataType="String" />
        <Column Assignment="51" Source="CH3_TaxIdentificationType" Target="CH3_TaxIdentificationType" DataType="String" />
        <Column Assignment="52" Source="TFD_TaxForm" Target="TFD_TaxForm" DataType="String" />
        <Column Assignment="53" Source="W8BENE_ExpiryDate" Target="W8BENE_ExpiryDate" DataType="String" />
        <Column Assignment="54" Source="DoddFrank_SWAPParticipation" Target="DoddFrank_SWAPParticipation" DataType="String" />
        <Column Assignment="55" Source="DoddFrank_EndUserExemption" Target="DoddFrank_EndUserExemption" DataType="String" />
        <Column Assignment="56" Source="DoddFrank_EndUserExemptionCategory" Target="DoddFrank_EndUserExemptionCategory" DataType="String" />
        <Column Assignment="57" Source="DoddFrank_Juristiction" Target="DoddFrank_Juristiction" DataType="String" />
        <Column Assignment="58" Source="DoddFrank_Onboarding" Target="DoddFrank_Onboarding" DataType="String" />
        <Column Assignment="59" Source="DoddFrank_ISDAAug2012ProtocolAdherence" Target="DoddFrank_ISDAAug2012ProtocolAdherence" DataType="String" />
        <Column Assignment="60" Source="DoddFrank_ISDAMar2013ProtocolAdherence" Target="DoddFrank_ISDAMar2013ProtocolAdherence" DataType="String" />
        <Column Assignment="61" Source="DoddFrank_USPersonType" Target="DoddFrank_USPersonType" DataType="String" />
        <Column Assignment="62" Source="DoddFrank_ProductArrangingEntity" Target="DoddFrank_ProductArrangingEntity" DataType="String" />
        <Column Assignment="63" Source="DoddFrank_ProductRegActivityEntity" Target="DoddFrank_ProductRegActivityEntity" DataType="String" />
        <Column Assignment="64" Source="DoddFrank_InitialMarginSegregationElection" Target="DoddFrank_InitialMarginSegregationElection" DataType="String" />
        <Column Assignment="65" Source="DoddFrank_SpecialEntity" Target="DoddFrank_SpecialEntity" DataType="String" />
        <Column Assignment="66" Source="DoddFrank_USAffiliate" Target="DoddFrank_USAffiliate" DataType="String" />
        <Column Assignment="67" Source="DoddFrank_USFinancialEntity" Target="DoddFrank_USFinancialEntity" DataType="String" />
        <Column Assignment="68" Source="DoddFrank_USGuarantor" Target="DoddFrank_USGuarantor" DataType="String" />
        <Column Assignment="69" Source="DoddFrank_USLegalEntity" Target="DoddFrank_USLegalEntity" DataType="String" />
        <Column Assignment="70" Source="DoddFrank_ActiveFund" Target="DoddFrank_ActiveFund" DataType="String" />
        <Column Assignment="71" Source="DoddFrank_CommodityPool" Target="DoddFrank_CommodityPool" DataType="String" />
        <Column Assignment="72" Source="DoddFrank_Category2Entity" Target="DoddFrank_Category2Entity" DataType="String" />
        <Column Assignment="73" Source="DoddFrank_PortfolioReconPref" Target="DoddFrank_PortfolioReconPref" DataType="String" />
        <Column Assignment="74" Source="DoddFrank_OptOutOfAnnualFiling" Target="DoddFrank_OptOutOfAnnualFiling" DataType="String" />
        <Column Assignment="75" Source="DoddFrank_FinanceAffiliateException" Target="DoddFrank_FinanceAffiliateException" DataType="String" />
        <Column Assignment="76" Source="DoddFrank_HedgeingAffException" Target="DoddFrank_HedgeingAffException" DataType="String" />
        <Column Assignment="77" Source="DoddFrank_SmallBankExemption" Target="DoddFrank_SmallBankExemption" DataType="String" />
        <Column Assignment="78" Source="DoddFrank_SecIssuerFiler" Target="DoddFrank_SecIssuerFiler" DataType="String" />
        <Column Assignment="79" Source="DoddFrank_ReceiveElectionApproval" Target="DoddFrank_ReceiveElectionApproval" DataType="String" />
        <Column Assignment="80" Source="DoddFrank_SecCentralIndexKeyNumber" Target="DoddFrank_SecCentralIndexKeyNumber" DataType="String" />
        <Column Assignment="81" Source="DoddFrank_WrittenCreditSupportAgreement" Target="DoddFrank_WrittenCreditSupportAgreement" DataType="String" />
        <Column Assignment="82" Source="DoddFrank_PledgedOrSegregatedAssets" Target="DoddFrank_PledgedOrSegregatedAssets" DataType="String" />
        <Column Assignment="83" Source="DoddFrank_WrittenThirdPartyGuarantee" Target="DoddFrank_WrittenThirdPartyGuarantee" DataType="String" />
        <Column Assignment="84" Source="DoddFrank_AvailableFinancialResources" Target="DoddFrank_AvailableFinancialResources" DataType="String" />
        <Column Assignment="85" Source="DoddFrank_OtherMeans" Target="DoddFrank_OtherMeans" DataType="String" />
        <Column Assignment="86" Source="DoddFrank_Descope" Target="DoddFrank_Descope" DataType="String" />
        <Column Assignment="87" Source="Emir_Onboarding" Target="Emir_Onboarding" DataType="String" />
        <Column Assignment="88" Source="Emir_Jurisdiction" Target="Emir_Jurisdiction" DataType="String" />
        <Column Assignment="89" Source="Emir_IsdaProtocolAdherence" Target="Emir_IsdaProtocolAdherence" DataType="String" />
        <Column Assignment="90" Source="Emir_EULegalEntity" Target="Emir_EULegalEntity" DataType="String" />
        <Column Assignment="91" Source="Emir_BranchIndicator" Target="Emir_BranchIndicator" DataType="String" />
        <Column Assignment="92" Source="Emir_FinancialCounterparty" Target="Emir_FinancialCounterparty" DataType="String" />
        <Column Assignment="93" Source="Emir_QtcLegalEntity" Target="Emir_QtcLegalEntity" DataType="String" />
        <Column Assignment="94" Source="Emir_Art14Counterparty" Target="Emir_Art14Counterparty" DataType="String" />
        <Column Assignment="95" Source="Emir_Art15Counterparty" Target="Emir_Art15Counterparty" DataType="String" />
        <Column Assignment="96" Source="Emir_PendingClassification" Target="Emir_PendingClassification" DataType="String" />
        <Column Assignment="97" Source="Emir_ReportingModel" Target="Emir_ReportingModel" DataType="String" />
        <Column Assignment="98" Source="Emir_DelegatorIndicator" Target="Emir_DelegatorIndicator" DataType="String" />
        <Column Assignment="99" Source="Emir_ClearingCategory" Target="Emir_ClearingCategory" DataType="String" />
        <Column Assignment="100" Source="Emir_AboveClearingThreshold" Target="Emir_AboveClearingThreshold" DataType="String" />
        <Column Assignment="101" Source="Emir_NonEeaCp" Target="Emir_NonEeaCp" DataType="String" />
        <Column Assignment="102" Source="Emir_CorporateSectorCode" Target="Emir_CorporateSectorCode" DataType="String" />
        <Column Assignment="103" Source="Emir_PortfolioData" Target="Emir_PortfolioData" DataType="String" />
        <Column Assignment="104" Source="Emir_ExemptFromClearing" Target="Emir_ExemptFromClearing" DataType="String" />
        <Column Assignment="105" Source="Emir_ClearingExemption" Target="Emir_ClearingExemption" DataType="String" />
        <Column Assignment="106" Source="Emir_ExemptComment" Target="Emir_ExemptComment" DataType="String" />
        <Column Assignment="107" Source="Emir_MasterAgreementType" Target="Emir_MasterAgreementType" DataType="String" />
        <Column Assignment="108" Source="Emir_Descope" Target="Emir_Descope" DataType="String" />
        <Column Assignment="109" Source="Fatca_USOnboarding" Target="Fatca_USOnboarding" DataType="String" />
        <Column Assignment="110" Source="Fatca_UKOnboarding" Target="Fatca_UKOnboarding" DataType="String" />
        <Column Assignment="111" Source="Fatca_USJurisdiction" Target="Fatca_USJurisdiction" DataType="String" />
        <Column Assignment="112" Source="Fatca_UKJurisdiction" Target="Fatca_UKJurisdiction" DataType="String" />
        <Column Assignment="113" Source="Fatca_EntityType" Target="Fatca_EntityType" DataType="String" />
        <Column Assignment="114" Source="Fatca_Status" Target="Fatca_Status" DataType="String" />
        <Column Assignment="115" Source="Fatca_RecommendedWithholding" Target="Fatca_RecommendedWithholding" DataType="String" />
        <Column Assignment="116" Source="Fatca_GIIN" Target="Fatca_GIIN" DataType="String" />
        <Column Assignment="117" Source="Fatca_TIN" Target="Fatca_TIN" DataType="String" />
        <Column Assignment="118" Source="Fatca_WithholdAgent" Target="Fatca_WithholdAgent" DataType="String" />
        <Column Assignment="119" Source="Fatca_BranchIndicator" Target="Fatca_BranchIndicator" DataType="String" />
        <Column Assignment="120" Source="Fatca_Isda" Target="Fatca_Isda" DataType="String" />
        <Column Assignment="121" Source="Fatca_USPerson" Target="Fatca_USPerson" DataType="String" />
        <Column Assignment="122" Source="Fatca_Recalcitrant" Target="Fatca_Recalcitrant" DataType="String" />
        <Column Assignment="123" Source="Fatca_LimitedBranch" Target="Fatca_LimitedBranch" DataType="String" />
        <Column Assignment="124" Source="Fatca_Descope" Target="Fatca_Descope" DataType="String" />
        <Column Assignment="125" Source="CanadianFIU_CTROnboarding" Target="CanadianFIU_CTROnboarding" DataType="String" />
        <Column Assignment="126" Source="CanadianFIU_Inscope" Target="CanadianFIU_Inscope" DataType="String" />
        <Column Assignment="127" Source="CanadianFIU_JurisOfIncHeadOffPrincBus" Target="CanadianFIU_JurisOfIncHeadOffPrincBus" DataType="String" />
        <Column Assignment="128" Source="CanadianFIU_LocalCP" Target="CanadianFIU_LocalCP" DataType="String" />
        <Column Assignment="129" Source="CanadianFIU_LocalCPProvince" Target="CanadianFIU_LocalCPProvince" DataType="String" />
        <Column Assignment="130" Source="CanadianFIU_RegisteredDealer" Target="CanadianFIU_RegisteredDealer" DataType="String" />
        <Column Assignment="131" Source="CanadianFIU_RegDealerProvince" Target="CanadianFIU_RegDealerProvince" DataType="String" />
        <Column Assignment="132" Source="CanadianFIU_Affiliate" Target="CanadianFIU_Affiliate" DataType="String" />
        <Column Assignment="133" Source="CanadianFIU_AffiliateProvince" Target="CanadianFIU_AffiliateProvince" DataType="String" />
        <Column Assignment="134" Source="CanadianFIU_ReportingDealer" Target="CanadianFIU_ReportingDealer" DataType="String" />
        <Column Assignment="135" Source="CanadianFIU_ReportingDealerProvince" Target="CanadianFIU_ReportingDealerProvince" DataType="String" />
        <Column Assignment="136" Source="CanadianFIU_MasterAgreement" Target="CanadianFIU_MasterAgreement" DataType="String" />
        <Column Assignment="137" Source="CanadianFIU_ReportingPartyRules" Target="CanadianFIU_ReportingPartyRules" DataType="String" />
        <Column Assignment="138" Source="CanadianFIU_ClearingExemption" Target="CanadianFIU_ClearingExemption" DataType="String" />
        <Column Assignment="139" Source="CanadianFIU_ConsentToDisclosure" Target="CanadianFIU_ConsentToDisclosure" DataType="String" />
        <Column Assignment="140" Source="CanadianFIU_ConsentToAllRequirements" Target="CanadianFIU_ConsentToAllRequirements" DataType="String" />
        <Column Assignment="141" Source="CanadianFIU_PCAPrincipalType" Target="CanadianFIU_PCAPrincipalType" DataType="String" />
        <Column Assignment="142" Source="CanadianFIU_MultiagreementDealers" Target="CanadianFIU_MultiagreementDealers" DataType="String" />
        <Column Assignment="143" Source="CanadianFIU_Descope" Target="CanadianFIU_Descope" DataType="String" />
        <Column Assignment="144" Source="ClientConsentToTradeReporting" Target="ClientConsentToTradeReporting" DataType="String" />
        <Column Assignment="145" Source="MifidII_LegalEntityType" Target="MifidII_LegalEntityType" DataType="String" />
        <Column Assignment="146" Source="MifidII_IsEntityCondEligibleBuss" Target="MifidII_IsEntityCondEligibleBuss" DataType="String" />
        <Column Assignment="147" Source="MifidII_DoesClientPossessKnowl" Target="MifidII_DoesClientPossessKnowl" DataType="String" />
        <Column Assignment="148" Source="MifidII_BalanceSheetTotal" Target="MifidII_BalanceSheetTotal" DataType="String" />
        <Column Assignment="149" Source="MifidII_NetTurnover" Target="MifidII_NetTurnover" DataType="String" />
        <Column Assignment="150" Source="MifidII_OwnFunds" Target="MifidII_OwnFunds" DataType="String" />
        <Column Assignment="151" Source="MifidII_ClassificationRecommended" Target="MifidII_ClassificationRecommended" DataType="String" />
        <Column Assignment="152" Source="MifidII_ProductSpecificClassification" Target="MifidII_ProductSpecificClassification" DataType="String" />
        <Column Assignment="153" Source="MifidII_Notes" Target="MifidII_Notes" DataType="String" />
        <Column Assignment="154" Source="MifidII_RequiredClientConsentObtained" Target="MifidII_RequiredClientConsentObtained" DataType="String" />
        <Column Assignment="155" Source="MifidII_QualitAtiveTestQ1" Target="MifidII_QualitAtiveTestQ1" DataType="String" />
        <Column Assignment="156" Source="MifidII_QualitAtiveTestQ2" Target="MifidII_QualitAtiveTestQ2" DataType="String" />
        <Column Assignment="157" Source="MifidII_QuantitativeTestQ1" Target="MifidII_QuantitativeTestQ1" DataType="String" />
        <Column Assignment="158" Source="MifidII_HasWrittenProtections" Target="MifidII_HasWrittenProtections" DataType="String" />
        <Column Assignment="159" Source="MifidII_HasClientLoosingProtections" Target="MifidII_HasClientLoosingProtections" DataType="String" />
        <Column Assignment="160" Source="MifidII_ExpressInformationTreated" Target="MifidII_ExpressInformationTreated" DataType="String" />
        <Column Assignment="161" Source="Gleif_LegalName" Target="Gleif_LegalName" DataType="String" />
        <Column Assignment="162" Source="Gleif_LegalJurisdiction" Target="Gleif_LegalJurisdiction" DataType="String" />
        <Column Assignment="163" Source="Gleif_LegalForm" Target="Gleif_LegalForm" DataType="String" />
        <Column Assignment="164" Source="Gleif_EntityStatus" Target="Gleif_EntityStatus" DataType="String" />
        <Column Assignment="165" Source="Gleif_LeiValidatedAgainst" Target="Gleif_LeiValidatedAgainst" DataType="String" />
        <Column Assignment="166" Source="MifidII_ClientContact" Target="MifidII_ClientContact" DataType="String" />
        <Column Assignment="167" Source="MifidII_Comments" Target="MifidII_Comments" DataType="String" />
        <Column Assignment="168" Source="MifidII_HasDDAssessmentCond" Target="MifidII_HasDDAssessmentCond" DataType="String" />
        <Column Assignment="169" Source="MifidII_HasProperAssessmentPerf" Target="MifidII_HasProperAssessmentPerf" DataType="String" />
        <Column Assignment="170" Source="MifidII_HasPresetTradAgreed" Target="MifidII_HasPresetTradAgreed" DataType="String" />
        <Column Assignment="171" Source="MifidII_ThresholdAmount" Target="MifidII_ThresholdAmount" DataType="String" />
        <Column Assignment="172" Source="MifidII_DeaStatusReviewDate" Target="MifidII_DeaStatusReviewDate" DataType="String" />
        <Column Assignment="173" Source="MifidII_IsAgreementInplace" Target="MifidII_IsAgreementInplace" DataType="String" />
        <Column Assignment="174" Source="MifidII_EEACountry" Target="MifidII_EEACountry" DataType="String" />
        <Column Assignment="175" Source="MifidII_InvestmentPortfoilioProvided" Target="MifidII_InvestmentPortfoilioProvided" DataType="String" />
        <Column Assignment="176" Source="MifidII_InvestmentCovered" Target="MifidII_InvestmentCovered" DataType="String" />
        <Column Assignment="177" Source="MifidII_SubjectEstablished" Target="MifidII_SubjectEstablished" DataType="String" />
        <Column Assignment="178" Source="MifidII_SecuritiesIndicator" Target="MifidII_SecuritiesIndicator" DataType="String" />
        <Column Assignment="179" Source="MifidII_InstrumentClassification" Target="MifidII_InstrumentClassification" DataType="String" />
        <Column Assignment="180" Source="MifidII_ClientHasPowerOfAttorneyOrRepresentation" Target="MifidII_ClientHasPowerOfAttorneyOrRepresentation" DataType="String" />
        <Column Assignment="181" Source="MifidII_NameOfAttorney" Target="MifidII_NameOfAttorney" DataType="String" />
        <Column Assignment="182" Source="MifidII_JointAccount" Target="MifidII_JointAccount" DataType="String" />
        <Column Assignment="183" Source="MifidII_KnowledgeInformation" Target="MifidII_KnowledgeInformation" DataType="String" />
        <Column Assignment="184" Source="MifidII_SuitabilityIssued" Target="MifidII_SuitabilityIssued" DataType="String" />
        <Column Assignment="185" Source="MifidII_SuitabilityPeriod" Target="MifidII_SuitabilityPeriod" DataType="String" />
        <Column Assignment="186" Source="MifidII_InvestmentInformation" Target="MifidII_InvestmentInformation" DataType="String" />
        <Column Assignment="187" Source="MifidII_AssessmentDate" Target="MifidII_AssessmentDate" DataType="String" />
        <Column Assignment="188" Source="MifidII_ClientProcessDetermine" Target="MifidII_ClientProcessDetermine" DataType="String" />
        <Column Assignment="189" Source="MifidII_ESCBMember" Target="MifidII_ESCBMember" DataType="String" />
        <Column Assignment="190" Source="MifidII_InvestmentSchemeStatus" Target="MifidII_InvestmentSchemeStatus" DataType="String" />
        <Column Assignment="191" Source="MifidII_ConsentToExecuteOrders" Target="MifidII_ConsentToExecuteOrders" DataType="String" />
        <Column Assignment="192" Source="MifidII_ConsentToReceiveEvidence" Target="MifidII_ConsentToReceiveEvidence" DataType="String" />
        <Column Assignment="193" Source="MifidII_ConsentForNonPublication" Target="MifidII_ConsentForNonPublication" DataType="String" />
        <Column Assignment="194" Source="MifidII_PositionHolderCategory" Target="MifidII_PositionHolderCategory" DataType="String" />
        <Column Assignment="195" Source="MifidII_UltimateParentLei" Target="MifidII_UltimateParentLei" DataType="String" />
        <Column Assignment="196" Source="MifidII_UltimateParentName" Target="MifidII_UltimateParentName" DataType="String" />
        <Column Assignment="197" Source="MifidII_PositionHolderEmail" Target="MifidII_PositionHolderEmail" DataType="String" />
        <Column Assignment="198" Source="MifidII_UltimateParentEntityEmail" Target="MifidII_UltimateParentEntityEmail" DataType="String" />
        <Column Assignment="199" Source="MifidII_CollectiveInvestUndertaking" Target="MifidII_CollectiveInvestUndertaking" DataType="String" />
        <Column Assignment="200" Source="LastUpdateTimestamp" Target="LastUpdateTimestamp" DataType="String" />
        <Column Assignment="201" Source="ActiveFlag" Target="ActiveFlag" DataType="String" />
        <Column Assignment="202" Source="IncludeFilterProductStatus" Target="IncludeFilterProductStatus" DataType="String" />
        <Column Assignment="203" Source="IncludeFilterProductCategory" Target="IncludeFilterProductCategory" DataType="String" />
        <Column Assignment="204" Source="IncludeInExtractFilter" Target="IncludeInExtractFilter" DataType="String" />
        <Column Assignment="205" Source="FeedDate" Target="FeedDate" DataType="String" />
        <Column Assignment="206" Source="DoddFrank_PrincipalBusiness" Target="DoddFrank_PrincipalBusiness" DataType="String" />
        <Column Assignment="207" Source="DoddFrank_PreTradeDailyMark" Target="DoddFrank_PreTradeDailyMark" DataType="String" />
        <Column Assignment="208" Source="DoddFrank_ConvForexTrans" Target="DoddFrank_ConvForexTrans" DataType="String" />
        <Column Assignment="209" Source="DoddFrank_ConvDerivTrans" Target="DoddFrank_ConvDerivTrans" DataType="String" />
        <Column Assignment="210" Source="DoddFrank_PreTradeMarkTransaction" Target="DoddFrank_PreTradeMarkTransaction" DataType="String" />
    </RecordTemplate>
</ExtractConfig>
```

assets/templates/Fenergo_RegCentral_EUEMIRExtract.xml:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<!-- Source=Target deliberately identical for now - real Target renames come later,
     once transform is actually needed (see docs/decisions.md). -->
<ExtractConfig ExtractType="CSV" DateFormat="M/d/yyyy h:mm:ss tt" MaxRetry="5">
    <RecordTemplate>
        <Column Assignment="1" Source="FID" Target="FID" DataType="String" />
        <Column Assignment="2" Source="Full Legal Name of the Named Entity" Target="Full Legal Name of the Named Entity" DataType="String" />
        <Column Assignment="3" Source="LEI of the Named Entity" Target="LEI of the Named Entity" DataType="String" />
        <Column Assignment="4" Source="Third Country Entity" Target="Third Country Entity" DataType="String" />
        <Column Assignment="5" Source="EU branches" Target="EU branches" DataType="String" />
        <Column Assignment="6" Source="DSF Guarantee(s)" Target="DSF Guarantee(s)" DataType="String" />
        <Column Assignment="7" Source="Fully or partially out of scope for EMIR" Target="Fully or partially out of scope for EMIR" DataType="String" />
        <Column Assignment="8" Source="Entity type that is fully or partially out of scope" Target="Entity type that is fully or partially out of scope" DataType="String" />
        <Column Assignment="9" Source="Reporting Obligation" Target="Reporting Obligation" DataType="String" />
        <Column Assignment="10" Source="EMIR Entity Type" Target="EMIR Entity Type" DataType="String" />
        <Column Assignment="11" Source="FC Corporate Sector" Target="FC Corporate Sector" DataType="String" />
        <Column Assignment="12" Source="Small FC" Target="Small FC" DataType="String" />
        <Column Assignment="13" Source="FC Clearing Start Date" Target="FC Clearing Start Date" DataType="String" />
        <Column Assignment="14" Source="FC Clearing Start Date - Other" Target="FC Clearing Start Date - Other" DataType="String" />
        <Column Assignment="15" Source="Is the entity a Pension Scheme Arrangement (PSA)?" Target="Is the entity a Pension Scheme Arrangement (PSA)?" DataType="String" />
        <Column Assignment="16" Source="Type of Pension Scheme Arrangement" Target="Type of Pension Scheme Arrangement" DataType="String" />
        <Column Assignment="17" Source="Use of the Pension Scheme Arrangement Exemption" Target="Use of the Pension Scheme Arrangement Exemption" DataType="String" />
        <Column Assignment="18" Source="Institution" Target="Institution" DataType="String" />
        <Column Assignment="19" Source="NFC Corporate Sector" Target="NFC Corporate Sector" DataType="String" />
        <Column Assignment="20" Source="Clearing Threshold" Target="Clearing Threshold" DataType="String" />
        <Column Assignment="21" Source="OTC Credit Derivatives Contracts" Target="OTC Credit Derivatives Contracts" DataType="String" />
        <Column Assignment="22" Source="Clearing date for OTC Credit Derivatives Contracts" Target="Clearing date for OTC Credit Derivatives Contracts" DataType="String" />
        <Column Assignment="23" Source="OTC Interest Rate Derivative Contracts" Target="OTC Interest Rate Derivative Contracts" DataType="String" />
        <Column Assignment="24" Source="Clearing Date for OTC Interest Rate Derivative Contracts" Target="Clearing Date for OTC Interest Rate Derivative Contracts" DataType="String" />
        <Column Assignment="25" Source="Is the Named Entity a member of an AANA Group?" Target="Is the Named Entity a member of an AANA Group?" DataType="String" />
        <Column Assignment="26" Source="Ultimate Parent of such AANA Group" Target="Ultimate Parent of such AANA Group" DataType="String" />
        <Column Assignment="27" Source="AANA Threshold Estimate" Target="AANA Threshold Estimate" DataType="String" />
        <Column Assignment="28" Source="Adherents portfolio reconciliation process status" Target="Adherents portfolio reconciliation process status" DataType="String" />
        <Column Assignment="29" Source="Adherents Local Business Days" Target="Adherents Local Business Days" DataType="String" />
        <Column Assignment="30" Source="Adherents contact details for Portfolio Data" Target="Adherents contact details for Portfolio Data" DataType="String" />
        <Column Assignment="31" Source="Notice of a discrepancy" Target="Notice of a discrepancy" DataType="String" />
        <Column Assignment="32" Source="Dispute Notice" Target="Dispute Notice" DataType="String" />
        <Column Assignment="33" Source="Mandatory Reporting" Target="Mandatory Reporting" DataType="String" />
        <Column Assignment="34" Source="Delegated Reporting" Target="Delegated Reporting" DataType="String" />
        <Column Assignment="35" Source="Delegated Reporting Effective Date" Target="Delegated Reporting Effective Date" DataType="String" />
        <Column Assignment="36" Source="Applicable Reporting Regime(s) for Client or Fund" Target="Applicable Reporting Regime(s) for Client or Fund" DataType="String" />
        <Column Assignment="37" Source="Mandatory Reporting Opt-Out" Target="Mandatory Reporting Opt-Out" DataType="String" />
        <Column Assignment="38" Source="Reporting Party Affiliate" Target="Reporting Party Affiliate" DataType="String" />
        <Column Assignment="39" Source="Relevant Trade Repository" Target="Relevant Trade Repository" DataType="String" />
        <Column Assignment="40" Source="Contact Information" Target="Contact Information" DataType="String" />
        <Column Assignment="41" Source="EU Legal Entity" Target="EU Legal Entity" DataType="String" />
        <Column Assignment="42" Source="EMIR Onboarding Requirements Met" Target="EMIR Onboarding Requirements Met" DataType="String" />
        <Column Assignment="43" Source="Country of Incorporation / Establishment" Target="Country of Incorporation / Establishment" DataType="String" />
        <Column Assignment="44" Source="ISDA Status" Target="ISDA Status" DataType="String" />
        <Column Assignment="45" Source="Portfolio Reconciliation" Target="Portfolio Reconciliation" DataType="String" />
        <Column Assignment="46" Source="Exempt from Clearing" Target="Exempt from Clearing" DataType="String" />
        <Column Assignment="47" Source="Master Agreement Type" Target="Master Agreement Type" DataType="String" />
        <Column Assignment="48" Source="Alternative Investment Fund" Target="Alternative Investment Fund" DataType="String" />
        <Column Assignment="49" Source="Associated Asset Manager" Target="Associated Asset Manager" DataType="String" />
        <Column Assignment="50" Source="Data Source" Target="Data Source" DataType="String" />
        <Column Assignment="51" Source="Clearing date for OTC credit derivative contracts other" Target="Clearing date for OTC credit derivative contracts other" DataType="String" />
        <Column Assignment="52" Source="Clearing date for OTC interest rate derivative contracts other" Target="Clearing date for OTC interest rate derivative contracts other" DataType="String" />
        <Column Assignment="53" Source="Ultimate Parent LEI" Target="Ultimate Parent LEI" DataType="String" />
        <Column Assignment="54" Source="LEI of EU AIFM" Target="LEI of EU AIFM" DataType="String" />
        <Column Assignment="55" Source="Execution Agent Name" Target="Execution Agent Name" DataType="String" />
        <Column Assignment="56" Source="LEI of Execution Agent Name" Target="LEI of Execution Agent Name" DataType="String" />
    </RecordTemplate>
</ExtractConfig>

```

assets/templates/Fenergo_RegCentral_UKEMIRExtract.xml:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<!-- Source=Target deliberately identical for now - real Target renames come later,
     once transform is actually needed (see docs/decisions.md). -->
<ExtractConfig ExtractType="CSV" DateFormat="M/d/yyyy h:mm:ss tt" MaxRetry="5">
    <RecordTemplate>
        <Column Assignment="1" Source="FID" Target="FID" DataType="String" />
        <Column Assignment="2" Source="Legal Entity Name" Target="Legal Entity Name" DataType="String" />
        <Column Assignment="3" Source="LEI of the Named Entity" Target="LEI of the Named Entity" DataType="String" />
        <Column Assignment="4" Source="Third Country Entity" Target="Third Country Entity" DataType="String" />
        <Column Assignment="5" Source="UK branches" Target="UK branches" DataType="String" />
        <Column Assignment="6" Source="DSF Guarantee(s)" Target="DSF Guarantee(s)" DataType="String" />
        <Column Assignment="7" Source="Fully or partially out of scope for EMIR" Target="Fully or partially out of scope for EMIR" DataType="String" />
        <Column Assignment="8" Source="Entity type that is fully or partially out of scope" Target="Entity type that is fully or partially out of scope" DataType="String" />
        <Column Assignment="9" Source="Reporting Obligation" Target="Reporting Obligation" DataType="String" />
        <Column Assignment="10" Source="EMIR Entity Type" Target="EMIR Entity Type" DataType="String" />
        <Column Assignment="11" Source="FC Corporate Sector" Target="FC Corporate Sector" DataType="String" />
        <Column Assignment="12" Source="Small FC" Target="Small FC" DataType="String" />
        <Column Assignment="13" Source="FC Clearing Start Date" Target="FC Clearing Start Date" DataType="String" />
        <Column Assignment="14" Source="FC Clearing Start Date - Other" Target="FC Clearing Start Date - Other" DataType="String" />
        <Column Assignment="15" Source="Is the entity a Pension Scheme Arrangement (PSA)?" Target="Is the entity a Pension Scheme Arrangement (PSA)?" DataType="String" />
        <Column Assignment="16" Source="Type of Pension Scheme Arrangement" Target="Type of Pension Scheme Arrangement" DataType="String" />
        <Column Assignment="17" Source="Use of the Pension Scheme Arrangement Exemption" Target="Use of the Pension Scheme Arrangement Exemption" DataType="String" />
        <Column Assignment="18" Source="Institution" Target="Institution" DataType="String" />
        <Column Assignment="19" Source="NFC Corporate Sector" Target="NFC Corporate Sector" DataType="String" />
        <Column Assignment="20" Source="Clearing Threshold" Target="Clearing Threshold" DataType="String" />
        <Column Assignment="21" Source="OTC Credit Derivatives Contracts" Target="OTC Credit Derivatives Contracts" DataType="String" />
        <Column Assignment="22" Source="Clearing date for OTC Credit Derivatives Contracts" Target="Clearing date for OTC Credit Derivatives Contracts" DataType="String" />
        <Column Assignment="23" Source="OTC Interest Rate Derivative Contracts" Target="OTC Interest Rate Derivative Contracts" DataType="String" />
        <Column Assignment="24" Source="Clearing Date for OTC Interest Rate Derivative Contracts" Target="Clearing Date for OTC Interest Rate Derivative Contracts" DataType="String" />
        <Column Assignment="25" Source="Is the Named Entity a member of an AANA Group?" Target="Is the Named Entity a member of an AANA Group?" DataType="String" />
        <Column Assignment="26" Source="Ultimate Parent of such AANA Group" Target="Ultimate Parent of such AANA Group" DataType="String" />
        <Column Assignment="27" Source="AANA Threshold Estimate" Target="AANA Threshold Estimate" DataType="String" />
        <Column Assignment="28" Source="Adherents portfolio reconciliation process status" Target="Adherents portfolio reconciliation process status" DataType="String" />
        <Column Assignment="29" Source="Adherents Local Business Days" Target="Adherents Local Business Days" DataType="String" />
        <Column Assignment="30" Source="Adherents contact details for Portfolio Data" Target="Adherents contact details for Portfolio Data" DataType="String" />
        <Column Assignment="31" Source="Notice of a discrepancy" Target="Notice of a discrepancy" DataType="String" />
        <Column Assignment="32" Source="Dispute Notice" Target="Dispute Notice" DataType="String" />
        <Column Assignment="33" Source="Mandatory Reporting" Target="Mandatory Reporting" DataType="String" />
        <Column Assignment="34" Source="Delegated Reporting" Target="Delegated Reporting" DataType="String" />
        <Column Assignment="35" Source="Delegated Reporting Effective Date" Target="Delegated Reporting Effective Date" DataType="String" />
        <Column Assignment="36" Source="Applicable Reporting Regime(s) for Client or Fund" Target="Applicable Reporting Regime(s) for Client or Fund" DataType="String" />
        <Column Assignment="37" Source="Mandatory Reporting Opt-Out" Target="Mandatory Reporting Opt-Out" DataType="String" />
        <Column Assignment="38" Source="Reporting Party Affiliate" Target="Reporting Party Affiliate" DataType="String" />
        <Column Assignment="39" Source="Relevant Trade Repository" Target="Relevant Trade Repository" DataType="String" />
        <Column Assignment="40" Source="Contact Information" Target="Contact Information" DataType="String" />
        <Column Assignment="41" Source="UK Legal Entity" Target="UK Legal Entity" DataType="String" />
        <Column Assignment="42" Source="EMIR Onboarding Requirements Met" Target="EMIR Onboarding Requirements Met" DataType="String" />
        <Column Assignment="43" Source="Country of Incorporation / Establishment" Target="Country of Incorporation / Establishment" DataType="String" />
        <Column Assignment="44" Source="ISDA Status" Target="ISDA Status" DataType="String" />
        <Column Assignment="45" Source="Exempt from Clearing" Target="Exempt from Clearing" DataType="String" />
        <Column Assignment="46" Source="Master Agreement Type" Target="Master Agreement Type" DataType="String" />
        <Column Assignment="47" Source="Alternative Investment Fund" Target="Alternative Investment Fund" DataType="String" />
        <Column Assignment="48" Source="Associated Asset Manager" Target="Associated Asset Manager" DataType="String" />
        <Column Assignment="49" Source="Data Source" Target="Data Source" DataType="String" />
        <Column Assignment="50" Source="Clearing date for OTC credit derivative contracts other" Target="Clearing date for OTC credit derivative contracts other" DataType="String" />
        <Column Assignment="51" Source="Clearing date for OTC interest rate derivative contracts other" Target="Clearing date for OTC interest rate derivative contracts other" DataType="String" />
        <Column Assignment="52" Source="Ultimate Parent LEI" Target="Ultimate Parent LEI" DataType="String" />
        <Column Assignment="53" Source="LEI of UK AIFM" Target="LEI of UK AIFM" DataType="String" />
        <Column Assignment="54" Source="Execution Agent Name" Target="Execution Agent Name" DataType="String" />
        <Column Assignment="55" Source="LEI of Execution Agent Name" Target="LEI of Execution Agent Name" DataType="String" />
    </RecordTemplate>
</ExtractConfig>

```

assets/templates/Fenergo_RegCentral.xml:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<!-- Source=Target deliberately identical for now - real Target renames come later,
     once transform is actually needed (see docs/decisions.md). -->
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
    </RecordTemplate>
</ExtractConfig>

```

assets/templates/RegCentral_MiFID.xml:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<!-- Source=Target deliberately identical for now - real Target renames come later,
     once transform is actually needed (see docs/decisions.md). -->
<ExtractConfig ExtractType="CSV" DateFormat="M/d/yyyy h:mm:ss tt" MaxRetry="5">
    <RecordTemplate>
        <Column Assignment="1" Source="fenergoid" Target="fenergoid" DataType="String" />
        <Column Assignment="2" Source="legalEntityName" Target="legalEntityName" DataType="String" />
        <Column Assignment="3" Source="legalEntityId" Target="legalEntityId" DataType="String" />
        <Column Assignment="4" Source="legalEntityType" Target="legalEntityType" DataType="String" />
        <Column Assignment="5" Source="countryOfIncorporation" Target="countryOfIncorporation" DataType="String" />
        <Column Assignment="6" Source="principalPlaceOfBusiness" Target="principalPlaceOfBusiness" DataType="String" />
        <Column Assignment="7" Source="client" Target="client" DataType="String" />
        <Column Assignment="8" Source="esmaBranchLocation" Target="esmaBranchLocation" DataType="String" />
        <Column Assignment="9" Source="esmaDesignatedPublishingEntity" Target="esmaDesignatedPublishingEntity" DataType="String" />
        <Column Assignment="10" Source="esmaDPEProducts" Target="esmaDPEProducts" DataType="String" />
        <Column Assignment="11" Source="esmaInvestmentFirm" Target="esmaInvestmentFirm" DataType="String" />
        <Column Assignment="12" Source="registeredIn" Target="registeredIn" DataType="String" />
        <Column Assignment="13" Source="fcaBranchLocation" Target="fcaBranchLocation" DataType="String" />
        <Column Assignment="14" Source="fcaDesignatedReporter" Target="fcaDesignatedReporter" DataType="String" />
        <Column Assignment="15" Source="fcaInvestmentFirm" Target="fcaInvestmentFirm" DataType="String" />
        <Column Assignment="16" Source="fcaThirdCountryInvestmentFirm" Target="fcaThirdCountryInvestmentFirm" DataType="String" />
        <Column Assignment="17" Source="fcaEntityType" Target="fcaEntityType" DataType="String" />
        <Column Assignment="18" Source="fcaSmallFC" Target="fcaSmallFC" DataType="String" />
        <Column Assignment="19" Source="fcaClearingThreshold" Target="fcaClearingThreshold" DataType="String" />
    </RecordTemplate>
</ExtractConfig>

```

## Python changes

report_definitions/ccd_email_report.py

```python
REPORT_NAME = "CCD_Email"
SQL_FILE = "CCD_Email.sql"
TEMPLATE_FILE = "CCD_Email.xml"
ARCHIVE_PATH = "EmailFenergoCCD"
# SFTP_CONNECTION intentionally unset - see ccd_report.py, same reasoning.
```

report_definitions/ccd_report.py:

```python
REPORT_NAME = "CCD"
SQL_FILE = "CCD.sql"
TEMPLATE_FILE = "CCD.xml"
ARCHIVE_PATH = "CCD"
# SFTP_CONNECTION intentionally unset - a new, dedicated destination is coming
# later (not RegCentral/ClientCentralData). Unset falls back to the legacy
# global SFTP_* settings, which raise a clear DeliveryConfigError if
# unconfigured rather than silently delivering to the wrong place.

```

report_definitions/fenergo_regcentral_euemirextract_report.py:

```python
REPORT_NAME = "Fenergo_RegCentral_EUEMIRExtract"
SQL_FILE = "Fenergo_RegCentral_EUEMIRExtract.sql"
TEMPLATE_FILE = "Fenergo_RegCentral_EUEMIRExtract.xml"
ARCHIVE_PATH = "RegCentral_EUEMIRTracker"
SFTP_CONNECTION = "RegCentral"
```

report_definitions/fenergo_regcentral_report.py:

```python
REPORT_NAME = "Fenergo_RegCentral"
SQL_FILE = "Fenergo_RegCentral.sql"
TEMPLATE_FILE = "Fenergo_RegCentral.xml"
ARCHIVE_PATH = "RegCentral"
SFTP_CONNECTION = "RegCentral"

```

report_definitions/fenergo_regcentral_ukemirextract_report.py:

```python
REPORT_NAME = "Fenergo_RegCentral_UKEMIRExtract"
SQL_FILE = "Fenergo_RegCentral_UKEMIRExtract.sql"
TEMPLATE_FILE = "Fenergo_RegCentral_UKEMIRExtract.xml"
ARCHIVE_PATH = "RegCentral_UKEMIRTracker"
SFTP_CONNECTION = "RegCentral"

```

report_definitions/regcentral_mifid_report.py:

```python
REPORT_NAME = "RegCentral_MiFID"
SQL_FILE = "RegCentral_MiFID.sql"
TEMPLATE_FILE = "RegCentral_MiFID.xml"
ARCHIVE_PATH = "RegCentral_MiFID"
SFTP_CONNECTION = "RegCentral"

```



