![IRD logo](../Images/IRlogo.gif)
![Software Dev](../Images/SoftwareDev.png)

# Income Tax Software Development Kit (SDK)

#### Archives
* [V1.0 Annual Return 2021](./archive/2021)
* [V1.0 Annual Return 2020](./archive/2020)
* [V1.0 Annual Return 2019](./archive/2019)

### Latest Release: V1.0  - Annual Return 2022

Income Tax reporting through gateway services enables organisations to: 

* submit new or amended income tax returns and supplementary forms 
* request income tax information held by us for a customer 
* query the processing status of a previously filed income tax return 
* request a copy of a previously filed income tax return 
* request the due date of the next expected income tax return. 	

## New Features: Annual Return 2022-2023   

The following key changes have been made to the Income Tax Return Service build pack to accommodate annual changes for 2022: 

*  The following fields have been ADDED to a number of IR forms for 2022 returns: 

	| Field | IR forms |
	| --- | --- | 
	| propertyInterestLimitation<br/> ➢ totalInterest <br/> ➢ interestExpenseClaimed <br/> ➢ interestExpenseClaimedReason <br/> interestExpenseClaimedReason <br/> ➢ notResidentialOrMaoriExempt <br/> ➢ propertyNotInNz <br/> ➢ loansDrawnDown <br/> ➢ newBuildExemption <br/> ➢ developmentExemption <br/> ➢ emergencyTransitionalSocialCouncil | IR3, IR3NR, IR3R, IR4¸ IR44, IR6, IR7, IR8, IR9 |
    |lossContinuity | IR4|
	| governmentSubsidies | CALC |
	| netProfitLossBeforeTax <br/> taxAdjustments <br/> unTaxedRealisedGainsAndReceipts| IR6 |
	| settlementDetails <br/> ➢ settlement <br/> settlement <br/> ➢ settlorFullName <br/> ➢ noSettlementThisYear <br/> ➢ settlorCommence <br/> ➢ taxJurisdiction <br/> ➢ settlorIrdNumber <br/> ➢ taxIdNumber <br/> ➢ noJurisdictionTin <br/> ➢ tinNotRequired <br/> ➢ cash <br/> ➢ financialArrangements <br/> ➢ land <br/> ➢ buildings <br/> ➢ shares <br/> ➢ services <br/> ➢ other <br/> ➢ otherDescription <br/> ➢ settlementZeroValue | IR6 |
	| beneficiary <br/> ➢ taxIdNumber <br/> ➢ taxJurisdiction <br/> ➢ noJurisdictionTin <br/> ➢ tinNotRequired <br/> ➢ openingBalance <br/> ➢ accountingIncomeAllocated <br/> ➢ corpus <br/> ➢ capital <br/> ➢ useOfTrustProperty <br/> ➢ distributionTrustAssets <br/> ➢ forgivenessOfDebt <br/> ➢ withdrawnFromTrust <br/> ➢ closingBalance | IR6 | 
    | exemptFromCompliance <br/> netProfitLossBeforeTax <br/> taxAdjustments <br/> unTaxedRealisedGainsAndReceipts <br/> financialArrangements  <br/> assetsLand <br/> assetsLandValuation assetsBuildings <br/>  assetsBuildingsValuation <br/> assetsShares <br/> assetsSharesValuation <br/> assetsTotal <br/> financialArrangementsLiable <br/> liabilitiesTotal <br/> equityOwners <br/> equityDrawings <br/> equityYearEndBalances| IR6 |  	
	| propertySaleDetails <br/> ➢ propertySale| Prepop values for IR833 form |
	| propertySale <br/> ➢ propertyTitle <br/> ➢ propertyAddress1  <br/> ➢ propertyAddress2 <br/> ➢ propertySuburb <br/> ➢ propertyCity <br/> ➢ propertyPostCode <br/> ➢ dateOfPurchase <br/> ➢ dateOfSale <br/> ➢ salePrice <br/> ➢ purchasePrice| Prepop values for IR833 form |
	| income <br/> ➢ subsidyType| Prepop values for IR833 form |
	
* The following **schemas** have also changed for 2022: 
	*  ReturnAUTO.v1.xsd (Auto-Calc, CALC) 
	* ReturnIR3.v1.xsd
	* ReturnIR3NR.v1.xsd
	* ReturnIR3R.v1.xsd
	* ReturnIR4.v1.xsd
	* ReturnIR6.v1.xsd
	* ReturnIR7.v1.xsd
	* ReturnIR8.v1.xsd
	* ReturnIR9.v1.xsd
	* ReturnIR44.v1.xsd
	* ReturnIR833.v1.xsd	
	* IncomeReturnCommon.v1.xsd 
	* Common.v2.xsd 
	
> The removal of 000-000-000 IRD number only applies to the IR6B and IR6S from 2022  onwards. You can still submit 000-000-000 IRD number for IR6B for 2021 and prior. There are no changes to the IR4S so 000-000-000 can still be submitted in 2022.	
	
* The following changes have been made to Income Tax-specific **ERROR CODES**:

	| Error code | Status  Description | IR forms affected |
	|-- | --| -- |
	| 2346 | interestExpenseClaimed has non-nil value, but no interestExpenseClaimedReason is provided | IR3, IR3NR,IR3R, IR4, IR6, IR7, IR8, IR9 and IR44 |
	| 2337 | returned when no value is provided for lossContinuity, but lossesBroughtForward is not nil | IR4 | 
	| 2354 | no value provided for assetsLandValuation | IR6 |
	| 2355 | no value provided for assetsBuildingsValuation || 
	| 2356 | no value provided for assetsSharesValuation ||
	| 2347 | no value provided for beneficiaryName  |IR6B|
	| 2348 | no value provided for beneficiaryDOB || 
	| 2349 | invalid or no value provided for taxJurisdiction ||
	|2350 | invalid value provided for noJurisdictionTin ||
	| 2351 | no value provided for beneficiaryIrdNumber || 
	| 2352 | invalid value provided for beneficiaryIrdNumber ||
	| 2353 | no value provided for taxIdNumber ||
	|2339 | settlorCommence cannot be in the future IR6S| IR6S |
	| 2340 | taxJurisdiction has invalid/unrecognised ISO-2A country code value ||
	| 2341 | settlorIrdNumber is provided, but failed IRD number check ||
	| 2342 | settlorIrdNumber not provided when it is required ||
	| 2343 | taxIdNumber not provided when it is required || 
	| 2344 | noJurisdictionTin has invalid value (true when taxJurisdiction is New Zealand) ||
	| 2345 | otherDescription not provided when other has non-nil value ||
	| 2357 | no value provided for settlorCommence ||
	| 2358 | no value provided for taxJurisdiction || 
	| 2359 | value of at least one of the following fields must be non-zero: cash, financialArrangements, land, buildings, shares, services, othe ||
	
	
	

	
## Key Documentation:

* Test scenarios
	* [Download test scenarios report template](Income%20Tax%20-%20Return%20Service%20-%20Test%20Report%20Template.docx)

* XSD Schemas 
    * View and download the [Income Return Common XSD](xsd/IncomeReturnCommon.v1.xsd) from this [XSD](xsd/) directory	
    * View the Income Tax XSD schema files from the [XSD](xsd/) directory
    * View and download the [Common and Return Common XSD](../Common%20XSD/)
	

* Build Pack

	* Download the [Return Service Income Tax build pack FY 2022](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Income%20Tax%20TY-2022.pdf) to view data definitions of each operation and response status code definitions
	* Download the [Return Service Income Tax build pack FY 2021](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Income%20Tax%20TY-2021.pdf) to view data definitions of each operation and response status code definitions
		* Supporting information on IR website
	* Download the [Additional Information pack 2022](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Additional%20Information%202022%20V1.3.pdf)	
	* Download the [Additional Information pack 2021](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Additional%20Information%202021%20V1.1.pdf)
		* Income tax assessments (Auto-Calc)

* Income Tax Form Types
	* [Primary income tax return forms](#Primary-income-tax-return-forms) 
	* [Attachment income tax return forms](#Attachment-income-tax-return) 

* [Sample request and responses](#Sample-request-and-responses)

* Supporting information on IR website 
	* [Income Tax and Auto-Calc Business use cases](https://www.ird.govt.nz/digital-service-providers/services-catalogue/returns-and-information/income-tax)
	* [Income tax assessments (Auto-Calc)](https://www.ird.govt.nz/income-tax/income-tax-for-individuals/what-happens-at-the-end-of-the-tax-year/income-tax-assessments)

## Environment Information: 
- [Mock Environment Information - Emulated Services, Mindmap and Test data](test%20details/README.md#mock-environment-information)
- [Test Environment Information - Test Scenarios Report Template, Mindmap and URL Endpoints](test%20details/README.md#test-environment-information)
- [Production Environment Information - URL Endpoints](test%20details/README.md#Production-Environment-Information)	

---

## Primary income tax return forms and accociated attachments

* IR10 - Financial statements summary
	* _Does not support attachments_
* IR1215 - As agent income tax return
	* _Does not support attachments_
* IR1261 - ***NEW*** 
	* _Does not support attachments_
* IR 215 - Adjust your income
	* _Does not support attachments_

* IR3 - Resident Individual Income Tax Return
    * CFC - Controlled foreign investment
    * IR10 - Financial statements summary 
    * 1261  - ***NEW*** 
    * IR215 - Adjust your income 
	* IR307 - Schedule of beneficiary’s estate or trust income
    * IR308 - Branch equivalent tax account return
    * IR3B - Schedule of business income
    * IR3F - arming income 
    * IR3K - Sale or disposal of financial arrangements
    * IR3NR – Non-Resident Individual Income Tax Return
    * IR3R - Rental income schedule
    * IR44E - Group investment fund return 
	* IR4J - Annual imputation return	
	* IR833 - Property sale information
	* IR8J - Māori authorities credit account return 
	
* IR307 - Schedule of beneficiary’s estate or trust income
	* _Does not support attachments_
* IR308 - Branch equivalent tax account return
	* _Does not support attachments_
* IR3B - Schedule of business income
	* _Does not support attachments_
* IR3F - arming income
	* _Does not support attachments_
* IR3K - Sale or disposal of financial arrangements
	* _Does not support attachments_

* IR3NR – Non-Resident Individual Income Tax Return
    * CFC - Controlled foreign investment
    * IR10 - Financial statements summary 
    * IR215 - Adjust your income 
	* IR307 - Schedule of beneficiary’s estate or trust income
    * IR308 - Branch equivalent tax account return
    * IR3B - Schedule of business income
    * IR3F - arming income 
    * IR3K - Sale or disposal of financial arrangements
    * IR3R - Rental income schedule
    * IR44E - Group investment fund return 
	* IR4J - Annual imputation return	
	* IR833 - Property sale information
	* IR8J - Māori authorities credit account return 

* IR3R - Rental income schedule
	* _Does not support attachments_

* IR4 - Companies Income Tax Return  
    * CFC - Controlled foreign investment
    * IR10 - Financial statements summary 
    * IR215 - Adjust your income 
	* IR307 - Schedule of beneficiary’s estate or trust income
    * IR308 - Branch equivalent tax account return
    * IR3B - Schedule of business income
    * IR3F - arming income 
    * IR3K - Sale or disposal of financial arrangements
	* IR3R - Rental income schedule
    * IR44E - Group investment fund return 
	* IR4J - Annual imputation return	
	* IR833 - Property sale information
	* IR8J - Māori authorities credit account return  

* IR44E - Group investment fund return

* IR44 - Superannuation funds income tax return
    * CFC - Controlled foreign investment
    * IR10 - Financial statements summary 
    * IR215 - Adjust your income 
	* IR307 - Schedule of beneficiary’s estate or trust income
    * IR308 - Branch equivalent tax account return
    * IR3B - Schedule of business income
    * IR3F - arming income 
    * IR3K - Sale or disposal of financial arrangements
	* IR3R - Rental income schedule
    * IR44E - Group investment fund return 
	* IR4J - Annual imputation return	
	* IR833 - Property sale information
	* IR8J - Māori authorities credit account return  

* IR6 - Estate or Trust Income Tax Return
    * CFC - Controlled foreign investment
    * IR10 - Financial statements summary 
    * IR215 - Adjust your income 
	* IR307 - Schedule of beneficiary’s estate or trust income
    * IR308 - Branch equivalent tax account return
    * IR3B - Schedule of business income
    * IR3F - arming income 
    * IR3K - Sale or disposal of financial arrangements
	* IR3R - Rental income schedule
    * IR44E - Group investment fund return 
	* IR4J - Annual imputation return	
	* IR833 - Property sale information
	* IR8J - Māori authorities credit account return  
	
* IR7 - Partnership and LTCs income tax return 
    * CFC - Controlled foreign investment
    * IR10 - Financial statements summary 
    * IR215 - Adjust your income 
	* IR307 - Schedule of beneficiary’s estate or trust income
    * IR308 - Branch equivalent tax account return
    * IR3B - Schedule of business income
    * IR3F - arming income 
    * IR3K - Sale or disposal of financial arrangements
	* IR3R - Rental income schedule
    * IR44E - Group investment fund return 
	* IR4J - Annual imputation return	
	* IR833 - Property sale information
	* IR8J - Māori authorities credit account return
	
* IR8 - Māori authorities income tax return 
    * CFC - Controlled foreign investment
    * IR10 - Financial statements summary 
    * IR215 - Adjust your income 
	* IR307 - Schedule of beneficiary’s estate or trust income
    * IR308 - Branch equivalent tax account return
    * IR3B - Schedule of business income
    * IR3F - arming income 
    * IR3K - Sale or disposal of financial arrangements
	* IR3R - Rental income schedule
    * IR44E - Group investment fund return 
	* IR4J - Annual imputation return	
	* IR833 - Property sale information
	* IR8J - Māori authorities credit account return
	
* IR833 - Property sale information

* IR8J - Māori authorities credit account return 
    * CFC - Controlled foreign investment
    * IR10 - Financial statements summary 
    * IR215 - Adjust your income 
	* IR307 - Schedule of beneficiary’s estate or trust income
    * IR308 - Branch equivalent tax account return
    * IR3B - Schedule of business income
    * IR3F - arming income 
    * IR3K - Sale or disposal of financial arrangements
	* IR3R - Rental income schedule
    * IR44E - Group investment fund return 
	* IR4J - Annual imputation return	
	* IR833 - Property sale information
	

* IR9 - Clubs or societies income tax return 
    * CFC - Controlled foreign investment
    * IR10 - Financial statements summary 
    * IR215 - Adjust your income 
	* IR307 - Schedule of beneficiary’s estate or trust income
    * IR308 - Branch equivalent tax account return
    * IR3B - Schedule of business income
    * IR3F - arming income 
    * IR3K - Sale or disposal of financial arrangements
	* IR3R - Rental income schedule
    * IR44E - Group investment fund return 
	* IR4J - Annual imputation return	
	* IR833 - Property sale information
	* IR8J - Māori authorities credit account return
	
* AUTO/CALC
    * CFC - Controlled foreign investment
    * IR10 - Financial statements summary 
    * IR215 - Adjust your income 
	* IR307 - Schedule of beneficiary’s estate or trust income
    * IR308 - Branch equivalent tax account return
    * IR3B - Schedule of business income
    * IR3F - arming income 
    * IR3K - Sale or disposal of financial arrangements
	* IR3NR - Non-Resident Individual Income Tax Return
	* IR3R - Rental income schedule
    * IR44E - Group investment fund return 
	* IR4J - Annual imputation return	
	* IR833 - Property sale information
	* IR8J - Māori authorities credit account return	

* CFC - Controlled foreign investment
* PTS - Individual income tax return	

> Note: PTS Individual income tax return RetrieveReturn and RetrieveStatus for income years prior to 2019 

## Sample request and responses

- File
    - [IR3 File request (with all applicable attachments)](sample%20messages/file_request_ir3_all_attachments.xml)
	- [IR3 File request](sample%20messages/file_request_ir3_standalone.xml) _(inc. Annual Changes 2021)_
    - [IR3NR File request](sample%20messages/file_request_ir3nr_standalone.xml) _(inc. Annual Changes 2021)_
    - [IR4 File request (with all applicable attachments)](sample%20messages/file_request_ir4_all_attachments.xml)
	- [IR4 File request](sample%20messages/file_request_ir4_standalone.xml) _(inc. Annual Changes 2021)_
    - [IR4J File request](sample%20messages/file_request_ir4j_standalone.xml)
    - [IR6 File request](sample%20messages/file_request_ir6_standalone.xml) _(inc. Annual Changes 2021)_
    - [IR7L File request](sample%20messages/file_request_ir7l_standalone.xml)
    - [IR7P File request](sample%20messages/file_request_ir7p_standalone.xml)
    - [IR8 File request](sample%20messages/file_request_ir8_standalone.xml) _(inc. Annual Changes 2021)_
    - [IR8J File request](sample%20messages/file_request_ir8j_standalone.xml)
    - [IR9 File request](sample%20messages/file_request_ir9_standalone.xml) _(inc. Annual Changes 2021)_
    - [IR44 File request](sample%20messages/file_request_ir44_standalone.xml) _(inc. Annual Changes 2021)_
	- [IR1215 File request](sample%20messages/file_request_ir215.xml)
    - [File Response](sample%20messages/file_response.xml) 
- RetrieveReturn
    - [RetrieveReturn request](sample%20messages/retrievereturn_request.xml)
    - [IR3 RetrieveReturn request](sample%20messages/file_request_ir3_Retrieve_Return_ACC_Identifier.xml) ACC_Identifier  
	- [IR3 RetrieveReturn response](sample%20messages/retrievereturn_response_ir3.xml) _(inc. Annual Changes 2021)_
	- [IR3NR RetrieveReturn response](sample%20messages/retrievereturn_response_ir3nr.xml) _(inc. Annual Changes 2021)_
    - [IR4 RetrieveReturn response](sample%20messages/retrievereturn_response_ir4.xml) _(inc. Annual Changes 2021)_
    - [IR4J RetrieveReturn response](sample%20messages/retrievereturn_response_ir4j.xml)
    - [IR6 RetrieveReturn response](sample%20messages/retrievereturn_response_ir6.xml) _(inc. Annual Changes 2021)_
    - [IR7L RetrieveReturn response](sample%20messages/retrievereturn_response_ir7l.xml)
    - [IR7P RetrieveReturn response](sample%20messages/retrievereturn_response_ir7p.xml)
    - [IR8 RetrieveReturn response](sample%20messages/retrievereturn_response_ir8.xml) _(inc. Annual Changes 2021)_
    - [IR8J RetrieveReturn response](sample%20messages/retrievereturn_response_ir8j.xml)
    - [IR9 RetrieveReturn response](sample%20messages/retrievereturn_response_ir9.xml) _(inc. Annual Changes 2021)_
    - [IR44 RetrieveReturn response](sample%20messages/retrievereturn_response_ir44.xml) _(inc. Annual Changes 2021)_
	- [IR1215 RetrieveReturn response](sample%20messages/retrievereturn_response_ir1215.xml) 
	
	
- RetrieveStatus
    - [RetrieveStatus request](sample%20messages/retrievestatus_request.xml)
    - [RetrieveStatus response](sample%20messages/retrievestatus_response.xml)
	- [RetrieveStatus response](sample%20messages/retrievestatus_response.xml)
- Prepop
    - [Prepop request](sample%20messages/prepop_request.xml)
    - [Prepop response (Individual customer)](sample%20messages/prepop_response_individual.xml)
    - [Prepop response (Non-Individual customer)](sample%20messages/prepop_response_nonindividual.xml)
- RetrieveFilingObligations
    - [RetrieveFilingObligations request](sample%20messages/retrievefilingobligations_request.xml)
    - [RetrieveFilingObligations response](sample%20messages/retrievefilingobligations_response.xml)
- Error codes 
    - [Error Code 2011](sample%20messages/ErrorCode2011.txt)
	- [Error Code 2227](sample%20messages/ErrorCode2227.txt)
	- [Error Code 2228](sample%20messages/ErrorCode2228.txt)
	- [Error Code 2230](sample%20messages/ErrorCode2230.txt)
	- [Error Code 2330](sample%20messages/ErrorCode2330.txt)
	- [Error Code 2331](sample%20messages/ErrorCode2331.txt)
	- [Error Code 2332](sample%20messages/ErrorCode2332.txt)
	- [Error Code 2333](sample%20messages/ErrorCode2333.txt)
	- [Error Code 2334](sample%20messages/ErrorCode2334.txt)
	- [Error Code 2335](sample%20messages/ErrorCode2335.txt)
	- [Error Code 2336](sample%20messages/ErrorCode2336.txt)
- Error codes _(New for Annual Changes 2022)_	
	- [Error Code 2339](sample%20messages/ErrorCode2339.txt)
	- [Error Code 2340](sample%20messages/ErrorCode2340.txt)
	- [Error Code 2341](sample%20messages/ErrorCode2341.txt)
	- [Error Code 2342](sample%20messages/ErrorCode2342.txt)
	- [Error Code 2343](sample%20messages/ErrorCode2343.txt)
	- [Error Code 2344](sample%20messages/ErrorCode2344.txt)
	- [Error Code 2345](sample%20messages/ErrorCode2345.txt)
	- [Error Code 2346](sample%20messages/ErrorCode2346.txt)
	- [Error Code 2347](sample%20messages/ErrorCode2347.txt)
	- [Error Code 2348](sample%20messages/ErrorCode2348.txt)
	- [Error Code 2349](sample%20messages/ErrorCode2349.txt)
	- [Error Code 2350](sample%20messages/ErrorCode2350.txt)
	- [Error Code 2351](sample%20messages/ErrorCode2351.txt)
	- [Error Code 2352](sample%20messages/ErrorCode2352.txt)
	- [Error Code 2353](sample%20messages/ErrorCode2353.txt)
	- [Error Code 2354](sample%20messages/ErrorCode2354.txt)
	- [Error Code 2355](sample%20messages/ErrorCode2355.txt)
	- [Error Code 2356](sample%20messages/ErrorCode2356.txt)
	- [Error Code 2336](sample%20messages/ErrorCode2357.txt)
	- [Error Code 2358](sample%20messages/ErrorCode2358.txt)
	- [Error Code 2359](sample%20messages/ErrorCode2359.txt)



	
	
	