![IRD logo](../Images/IRlogo.gif)
![Software Dev](../Images/SoftwareDev.png)

# Income Tax Software Development Kit (SDK)

#### Archives
* [V1.0 Annual Return 2020](./archive/2020)
* [V1.0 Annual Return 2019](./archive/2019)


### Latest Release: V1.0  - Annual Return 2021

	
Income Tax reporting through gateway services enables organisations to: 

* submit new or amended income tax returns and supplementary forms 
* request income tax information held by us for a customer 
* query the processing status of a previously filed income tax return 
* request a copy of a previously filed income tax return 
* request the due date of the next expected income tax return. 	
	
## New Features: Annual Return 2020-2021   

The following key changes have been made to the Income Tax Return Service build pack 
to accommodate annual changes for 2021: 
 
*  The following fields have been ADDED to a number of IR forms for 2021 returns: 
	 
	| Field | IR forms |
	| --- | --- | 
	| `pieDebit` <br/> `pieCredit` <br/> `pieIncome` <br/> ➢ `correctRate` <br/> ➢ `correctRateUsedAllYear` | IR3, CALC `(ReturnAUTO.v1.xsd)` |
	| `lossCarriedBackPriorYear` | IR3, IR3NR, IR4, IR6, IR8, IR9, IR44 |
	| `researchAndDevelopment` <br/> ➢ `creditBroughtForward` <br/> ➢ `nonrefundableCredit` <br/> ➢ `refundableCredit` | IR3, IR3NR, IR6, IR8, IR9, IR44 |
	| `researchAndDevelopment` <br/> ➢ `creditBroughtForward` | IR4 |
	| `governmentSubsidies` | IR3, IR3NR |
	| `residentialRentalIncome` <br/> ➢ `indicator` <br/> ➢ `totalIncome` <br/> ➢ `residentialRentalDeductions` <br/> ➢ `excessDeductionsBroughtForward` <br/> ➢ `deductionsClaimedThisYear` <br/>➢ `netIncome` <br/> ➢ `excessDeductionsCarriedForward` | IR44 | 
	 
* The following **schemas** have also changed for 2021: 
	*  ReturnAUTO.v1.xsd (Auto-Calc, CALC) 
	*  ReturnIR3.v1.xsd  
	*  ReturnIR3NR.v1.xsd  
	*  ReturnIR4.v1.xsd  
	*  ReturnIR6.v1.xsd  
	*  ReturnIR8.v1.xsd  
	*  ReturnIR9.v1.xsd  
	*  ReturnIR44.v1.xsd 
	*  ReturnIR1215.v1.xsd ***(added 21/04/2021)***
	*  IncomeReturnCommon.v1.xsd 

* The following changes have been made to Income Tax-specific **ERROR CODES**:

	| Error code | Status  Description  IR forms affected |
	|-- | --|
	|2011 | Changed `pieIncome` `totalTaxCredits` cannot be greater than `taxOnTaxableIncome` less `amountOfIETCClaimed` <br/> **NOTE:** This error code will only be returned for periods up to 2020 | IR3, Auto-Calc |
	|2228 | Added `lossCarriedBackPriorYear` must be 0 when there is no LCB indicator on the previous income tax period |IR3, IR3NR, IR4, IR6, IR8, IR9, IR44 |
	|2230 | Added `incomeFromPIE` is not used for the IR215 starting 2021 onwards IR215 |
	|2330 | The value of totalGeneralInsurancePremiums must match the sum of paymentsToGeneralInsurers `grossPremiums`   |
	|2331 | The value of `totalGuarantorFees` must match the sum of guarantors grossFees   |
	|2332 | The value of `totalGrossPremiumsFees` must match the sum of `totalGeneralInsurancePremiums`, `totalLifeInsurancePremiums`, `totalGuarantorFees`  |
	|2333 | The value of `totalSwissGrossPremiums` must match the sum of `paymentsToSwissInsurers` `swissGrossPremiums`  |
	|2334 | generalPayment `taxResidenceCountry`: non-resident insurer cannot be a New Zealand tax resident   |
	|2335 | generalPayment `taxResidenceCountry`: non-resident insurer cannot be a New Zealand tax resident   |
	|2335 |  generalPayment `taxResidenceCountry`: payments to insurers resident in Switzerland are not taxable and should be recorded in `paymentsToSwissInsurers`    |
	|2336 | guarantor `taxResidenceCountry`: non-resident guarantors cannot be New Zealand tax resident   |

	
## Key Documentation:

* Test scenarios
	* [Download test scenarios report template](Income%20Tax%20-%20Return%20Service%20-%20Test%20Report%20Template.docx)

* XSD Schemas 
    * View and download the [Income Return Common XSD](xsd/IncomeReturnCommon.v1.xsd) from this [XSD](xsd/) directory	
    * View the Income Tax XSD schema files from the [XSD](xsd/) directory
    * View and download the [Common and Return Common XSD](../Common%20XSD/)
	

* Build Pack

	* Download the [Return Service Income Tax build pack FY 2021](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Income%20Tax%20TY-2021.pdf) to view data definitions of each operation and response status code definitions
	* Download the [Return Service Income Tax build pack FY 2020](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Income%20Tax%20TY-2020.pdf) to view data definitions of each operation and response status code definitions
		* Supporting information on IR website
	* Download the [Additional Information pack](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Additional%20Information%202021%20V1.1.pdf)
		* Income tax assessments (Auto-Calc)

* Income Tax Form Types
	* [Primary income tax return forms](#Primary-income-tax-return-forms) 
	* [Attachment income tax return forms](#Attachment-income-tax-return) 

* [Sample request and responses](#Sample-request-and-responses)

* Supporting information on IR website 
	* [Income Tax and Auto-Calc Business use cases](https://www.ird.govt.nz/digital-service-providers/services-catalogue/returns-and-information/income-tax)
	* [Income tax assessments (Auto-Calc)](https://www.ird.govt.nz/income-tax/income-tax-for-individuals/what-happens-at-the-end-of-the-tax-year/income-tax-assessments)

## Environment Information: 
- [Mock Environment Information - Emulated Services, Mindmap and Test data](test%20details/TestingInfomation.md#mock-environment-information)
- [Test Environment Information - Test Scenarios Report Template, Mindmap and URL Endpoints](test%20details/TestingInfomation.md#test-environment-information)
- [Production Environment Information - URL Endpoints](test%20details/TestingInfomation.md#Production-Environment-Information)	

---

## Primary income tax return forms

* IR3 - Resident Individual Income Tax Return
	* IR10 - Financial statements summary 
	* IR833 - Property sale information  
	* IR3F - arming income 
	* IR3B - Schedule of business income
	* IR3R - Rental income schedule
	* IR3K - Sale or disposal of financial arrangements
	* IR307 - Schedule of beneficiary’s estate or trust income
	* IR308 - Branch equivalent tax account return
	* IR215 - Adjust your income 
	* CFC - Controlled foreign investment
	
* IR3NR – Non-Resident Individual Income Tax Return
	* IR10 - Financial statements summary 
	* IR833 - Property sale information  
	* IR3F - arming income 
	* IR3B - Schedule of business income
	* IR3R - Rental income schedule
	* IR3K - Sale or disposal of financial arrangements
	
* IR4/S - Companies Income Tax Return  
	* IR10 - Financial statements summary
	* IR833 - Property sale information  
	* IR44E - Group investment fund return 
	* IR4J - Annual imputation return  
	* CFC - Controlled foreign investment  

* IR6 - Estate or Trust Income Tax Return
	* IR10 - Financial statements summary  
	* IR833 - Property sale information  
	* IR3F - Farming income 
	* IR3B - Schedule of business income 
	* IR3R - Rental income schedule 
	* IR44E - Group investment fund return 
	* IR308 - Branch equivalent tax account return 
	* CFC - Controlled foreign investment
	
* IR7 - Partnership and LTCs income tax return 
	* IR10 - Financial statements summary
	* IR833 - Property sale information 
	* IR3F - Farming income 
	* IR3B - Schedule of business income 
	* IR3R - Rental income schedule
	* IR44E - Group investment fund return
	* CFC - Controlled foreign investment
	
* IR8 - Māori authorities income tax return 
	* IR10 - Financial statements summary 
	* IR833 - Property sale information  
	* IR3B - Schedule of business income
	* IR3R - Rental income schedule
	* IR8J - Property sale information 
	* CFC - Controlled foreign investment 
	
* IR8J - Māori authorities credit account return 
	* IR10 - Financial statements summary  
	* IR833 - Property sale information  
	* IR3B - Schedule of business income 
	* IR3R - Rental income schedule 
	* IR8J - Property sale information  
	* CFC - Controlled foreign investment 

* IR9 - Clubs or societies income tax return 
	* IR10 - Financial statements summary  
	* IR833 - Property sale information  
	* CFC - Controlled foreign investment 
	
* IR44 - Superannuation funds income tax return
	* IR10 - Financial statements summary
	* IR833 - Property sale information 
	* CFC  - Controlled foreign investment
	
* IR1215 - As agent income tax return	
	
* IR215 - Adjust your income 
	* Does not support attachments	
	
## Attachment income tax return

* IR3F - Farming income
* IR3B - Schedule of business income
* IR3R - Rental income schedule
* IR3K - Sale or disposal of financial arrangements 
* IR4J - Annual imputation return 
* IR44E - Group investment fund return
* IR10 - Financial statements summary 
* IR215 - Adjust your income
* IR307 - Schedule of beneficiary’s estate or trust income
* IR833 - Property sale information
* IR308 - Branch equivalent tax account return  
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
- Error codes _(New for Annual Changes 2021)_
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



	
	
	