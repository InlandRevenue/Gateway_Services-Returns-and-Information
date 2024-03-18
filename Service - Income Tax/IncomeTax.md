![IRD logo](../Images/IRlogo.gif)
![Software Dev](../Images/SoftwareDev.png)

# Income Tax Software Development Kit (SDK)

#### Archives
* [V1.0 Annual Return 2023](./archive/2023)
* [V1.0 Annual Return 2022](./archive/2022)
* [V1.0 Annual Return 2021](./archive/2021)
* [V1.0 Annual Return 2020](./archive/2020)

## Key Documentation:

* Test scenarios
	* [Download test scenarios report template](Income%20Tax%20-%20Return%20Service%20-%20Test%20Report%20Template.docx)

* XSD Schemas 
    * View and download the [Income Return Common XSD](xsd/IncomeReturnCommon.v1.xsd) from this [XSD](xsd/) directory	
    * View the Income Tax XSD schema files from the [XSD](xsd/) directory
    * View and download the [Common and Return Common XSD](../Common%20XSD/)

* Build Pack

    * Download the [Return Service Income Tax build pack TY 2024](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Income%20Tax%20TY-2024.pdf) to view data definitions of each operation and response status code definitions
	* Download the [Return Service Income Tax build pack TY 2023](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Income%20Tax%20TY-2023.pdf) to view data definitions of each operation and response status code definitions

	
* Supporting information on IR website
    * Download the [Additional Information pack 2024](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Additional%20Information%202024.pdf)		
	* Download the [Additional Information pack 2023](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20Additional%20Information%202023.pdf)		
	
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
	- [IR3 File request](sample%20messages/file_request_ir3_standalone.xml) 
    - [IR3NR File request](sample%20messages/file_request_ir3nr_standalone.xml) 
    - [IR4 File request (with all applicable attachments)](sample%20messages/file_request_ir4_all_attachments.xml)
	- [IR4 File request](sample%20messages/file_request_ir4_standalone.xml) 
    - [IR4J File request](sample%20messages/file_request_ir4j_standalone.xml)
    - [IR6 File request](sample%20messages/file_request_ir6_standalone.xml) 
    - [IR6 v2 File request (with all applicable attachments)](sample%20messages/file_request_ir6_v2_all_attachments.xml)
    - [IR7L File request](sample%20messages/file_request_ir7l_standalone.xml)
    - [IR7P File request](sample%20messages/file_request_ir7p_standalone.xml)
    - [IR8 File request](sample%20messages/file_request_ir8_standalone.xml) 
    - [IR8J File request](sample%20messages/file_request_ir8j_standalone.xml)
    - [IR9 File request](sample%20messages/file_request_ir9_standalone.xml) 
    - [IR44 File request](sample%20messages/file_request_ir44_standalone.xml) 
	- [IR1215 File request](sample%20messages/file_request_ir215.xml)
    - [File Response](sample%20messages/file_response.xml) 
- RetrieveReturn
    - [RetrieveReturn request](sample%20messages/retrievereturn_request.xml)
    - [IR3 RetrieveReturn request](sample%20messages/file_request_ir3_Retrieve_Return_ACC_Identifier.xml) ACC_Identifier  
	- [IR3 RetrieveReturn response](sample%20messages/retrievereturn_response_ir3.xml) 
	- [IR3NR RetrieveReturn response](sample%20messages/retrievereturn_response_ir3nr.xml) 
    - [IR4 RetrieveReturn response](sample%20messages/retrievereturn_response_ir4.xml) 
    - [IR4J RetrieveReturn response](sample%20messages/retrievereturn_response_ir4j.xml)
    - [IR6 RetrieveReturn response](sample%20messages/retrievereturn_response_ir6.xml) 
    - [IR6 v2 RetrieveReturn response](sample%20messages/retrievereturn_response_ir6_v2.xml)
    - [IR7L RetrieveReturn response](sample%20messages/retrievereturn_response_ir7l.xml)
    - [IR7P RetrieveReturn response](sample%20messages/retrievereturn_response_ir7p.xml)
    - [IR8 RetrieveReturn response](sample%20messages/retrievereturn_response_ir8.xml) 
    - [IR8J RetrieveReturn response](sample%20messages/retrievereturn_response_ir8j.xml)
    - [IR9 RetrieveReturn response](sample%20messages/retrievereturn_response_ir9.xml) 
    - [IR44 RetrieveReturn response](sample%20messages/retrievereturn_response_ir44.xml)
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
- Error codes _(New for Annual Changes 2023)_	
	- [Error Code 2360](sample%20messages/ErrorCode2360.txt)
	- [Error Code 2361](sample%20messages/ErrorCode2361.txt)
	- [Error Code 2363](sample%20messages/ErrorCode2363.txt)
	- [Error Code 2366](sample%20messages/ErrorCode2366.txt)
	- [Error Code 2367](sample%20messages/ErrorCode2367.txt)
	- [Error Code 2368](sample%20messages/ErrorCode2368.txt)	
	- [Error Code 2370](sample%20messages/ErrorCode2370.txt)
	- [Error Code 2371](sample%20messages/ErrorCode2371.txt)
- Error codes _(New for Annual Changes 2024)_
	- [Error Code 23](sample%20messages/ErrorCode23.txt)
	- [Error Code 2372](sample%20messages/ErrorCode2372.txt)
	
	