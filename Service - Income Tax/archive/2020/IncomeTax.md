![IRD logo](../../../Images/IRlogo.gif)
![Software Dev](../../../Images/SoftwareDev.png)


# Income Tax Software Development Kit (SDK)

#### Archives
* [V1.0 Annual Return 2019](../../archive/2019/)

### Latest Release: V1.0  - Annual Return 2020
	
Income Tax reporting through gateway services enables organisations to: 

* submit new or amended income tax returns and supplementary forms 
* request income tax information held by us for a customer 
* query the processing status of a previously filed income tax return 
* request a copy of a previously filed income tax return 
* request the due date of the next expected income tax return. 	
	
## New Features: Annual Return 2020   

The following key changes have been made to the Income Tax Return Service build pack 
to accommodate annual changes for 2020: 
 
*  ‘Shareholder AIM tax paid’ will be returned from a ‘Prepop’ request when 
applicable. 
 
*  Non-resident foreign sourced income is no longer applicable for tax year 2020 
and onward. An error message will be returned if it is inadvertently submitted via 
gateway services. It has been REMOVED from form IR215. 
 
*  The following fields have been ADDED to a number of IR forms for 2020 returns: 
 
|Field | IR forms |
| --- | --- | 
|Shareholder AIM tax paid | IR3, IR4S |
|Residential income indicator  |IR3, IR3NR, IR4, IR6, IR7, IR8, IR9 |
|Total residential income  |IR3, IR3NR, IR4, IR6, IR7, IR7L/IR7P, IR8, IR9 |
|Residential rental deductions  |IR3, IR3NR, IR4, IR6, IR7, IR7L/IR7P, IR8, IR9 |
|Excess residential rental deductions brought forward |IR3, IR3NR, IR4, IR6, IR8, IR9 |
|Residential rental deductions claimed this year |IR3, IR3NR, IR4, IR6, IR8, IR9 |
|Net residential income | IR3, IR3NR, IR4, IR6, IR8, IR9 |
|Excess residential rental deductions carried forward |IR3, IR3NR, IR4, IR6, IR8, IR9 |
|Current year R&D non-refundable tax incentive credits to use or carry forward |IR3, IR3NR, IR4, IR6, IR8, IR9, IR44 |
|R&D tax incentive credits to be refunded |IR4 |
|Profit/loss from sale of property | IR8, IR9, IR44 | 
 
The following schemas have also changed for 2020: 
 
	*  ReturnIR3.v1.xsd  
	*  ReturnIR3NR.v1.xsd  
	*  ReturnIR4.v1.xsd  
	*  ReturnIR6.v1.xsd  
	*  ReturnIR7.v1.xsd  
	*  ReturnIR8.v1.xsd  
	*  ReturnIR9.v1.xsd  
	*  ReturnIR44.v1.xsd  
	*  IncomeReturnCommon.v1.xsd 
	
## Key Documentation:

* Test scenarios
	* [Download test scenarios report template **2020**](INC%202020%20changes%20-%20Return%20Service%20-%20Test%20Report%20Template.docx)
	* [Download test scenarios report template **2019**](Income%20Tax%20Return%20Gateway%20Service%202019%20-%20Test%20Report%20Template%20.docx)

* XSD Schemas 
    * View and download the [Income Return Common XSD](xsd/IncomeReturnCommon.v1.xsd) from this [XSD](xsd/) directory	
    * View the Income Tax XSD schema files from the [XSD](xsd/) directory
    * View and download the [Common and Return Common XSD](../../../Common%20XSD/)
	

* Build Pack
	* Download the [Return Service Income Tax build pack](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Income%20Tax%20TY-2020.pdf) to view data definitions of each operation and response status code definitions
		* Supporting information on IR website
	* Download the [Additional Information pack](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Additional%20Information%202021%20V1.0.pdf)
		* Income tax assessments (auto calc)

* Income Tax Form Types
	* [Primary income tax return forms](#Primary-income-tax-return-forms) 
	* [Attachment income tax return forms](#Attachment-income-tax-return) 

* [Sample request and responses](#Sample-request-and-responses)

* Supporting information on IR website 
	* [Income Tax and Auto calc Business use cases](https://www.ird.govt.nz/digital-service-providers/services-catalogue/returns-and-information/income-tax)
	* [Income tax assessments (auto calc)](https://www.ird.govt.nz/income-tax/income-tax-for-individuals/what-happens-at-the-end-of-the-tax-year/income-tax-assessments)

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
    - [IR3NR File request](sample%20messages/file_request_ir3nr_standalone.xml)
    - [IR4 File request (with all applicable attachments)](sample%20messages/file_request_ir4_all_attachments.xml)
	- [IR4J File request](sample%20messages/file_request_ir4j_standalone.xml)
    - [IR6 File request](sample%20messages/file_request_ir6_standalone.xml)
    - [IR7L File request](sample%20messages/file_request_ir7l_standalone.xml)
    - [IR7P File request](sample%20messages/file_request_ir7p_standalone.xml)
    - [IR8 File request](sample%20messages/file_request_ir8_standalone.xml)
    - [IR8J File request](sample%20messages/file_request_ir8j_standalone.xml)
    - [IR9 File request](sample%20messages/file_request_ir9_standalone.xml)
    - [IR44 File request](sample%20messages/file_request_ir44_standalone.xml)
    - [File Response](sample%20messages/file_response.xml)
- RetrieveReturn
    - [RetrieveReturn request](sample%20messages/retrievereturn_request.xml)
    - [IR3 RetrieveReturn response](sample%20messages/retrievereturn_response_ir3.xml)
    - [IR3NR RetrieveReturn response](sample%20messages/retrievereturn_response_ir3nr.xml)
    - [IR4 RetrieveReturn response](sample%20messages/retrievereturn_response_ir4.xml)
    - [IR4J RetrieveReturn response](sample%20messages/retrievereturn_response_ir4j.xml)
    - [IR6 RetrieveReturn response](sample%20messages/retrievereturn_response_ir6.xml)
    - [IR7L RetrieveReturn response](sample%20messages/retrievereturn_response_ir7l.xml)
    - [IR7P RetrieveReturn response](sample%20messages/retrievereturn_response_ir7p.xml)
    - [IR8 RetrieveReturn response](sample%20messages/retrievereturn_response_ir8.xml)
    - [IR8J RetrieveReturn response](sample%20messages/retrievereturn_response_ir8j.xml)
    - [IR9 RetrieveReturn response](sample%20messages/retrievereturn_response_ir9.xml)
    - [IR44 RetrieveReturn response](sample%20messages/retrievereturn_response_ir44.xml)
- RetrieveReturn
    - [RetrieveStatus request](sample%20messages/retrievestatus_request.xml)
    - [RetrieveStatus response](sample%20messages/retrievestatus_response.xml)
- Prepop
    - [Prepop request](sample%20messages/prepop_request.xml)
    - [Prepop response (Individual customer)](sample%20messages/prepop_response_individual.xml)
    - [Prepop response (Non-Individual customer)](sample%20messages/prepop_response_nonindividual.xml)
- RetrieveFilingObligations
    - [RetrieveFilingObligations request](sample%20messages/retrievefilingobligations_request.xml)
    - [RetrieveFilingObligations response](sample%20messages/retrievefilingobligations_response.xml)
	