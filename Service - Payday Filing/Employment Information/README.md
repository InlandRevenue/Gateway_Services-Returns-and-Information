![IRD logo](../../Images/IRlogo.gif)<br/>
![Software Dev](../../Images/SoftwareDev.png)

# Employment Information (EI) Software Development Kit (SDK)

Employees can file Employment information (EI) to us each pay cycle using the Return service.

### Latest Release V 2.0 - [view details](#V-2.0-update-details)

### Archive 
* [Employment Information V 1](../Archive/V1/Employment%20Information)

## Key documentation

- Business use cases
	- [Download and view](../Payday%20filing%20-%20Employee%20details%20and%20employment%20information%20-%20GWS%20business%20use%20cases.pdf)
	
- Schemas and WSDLs
	- View and download the [Common v2 XSD](../../Common%20XSD/Common.v2.xsd)
	- View and download the [Return Service Common v2 XSD](../../Common%20XSD/ReturnCommon.v2.xsd)
	- View and download the Employment Income (EI) return [v2 XSD](ReturnEI.v2.xsd) and [v2 WSDL](ReturnsEIDevWsdl.v2.wsdl) from this directory
	
- Build pack 
	- [Download and view the Return Service - EI build pack](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20EI%20v2.pdf) to view data definitions of each operation and response status code definitions

- Message samples
    - [View message samples for requests and positive responses](#message-samples)

- Find out about 
	- [Employee Details SDK](../Employee%20Details)
	- the defined tax rates and thresholds, tax types business rules, and calculations required for specific tax codes [on the IR website](https://www.ird.govt.nz/digital-service-providers/services-catalogue/returns-and-information/payday-filing/payroll-calculations-and-business-rules)
	- how to make employee deduction payments [on the IR website](https://www.ird.govt.nz/payroll-employers/returns-payments/payday-filing/)

## Environment information

- [Mock environment information - emulated services](#mock-environment-information)

- [Test environment information - test scenarios, mind map and URL endpoints](#test-environment-information)

- [Production environment information - URL endpoints](#Production-Environment-Information)	

## Supporting services

* [Service: Identity and Access](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access) – view how to integrate, OAuth requests and responses message samples and build pack
* [Service: Intermediation](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Service%20-%20Intermediation)

## V 2.0 update details
-----------------

The following key changes have been made to the Employment Information Return Service for the update to V2.0.

* Operations
	* Updated schema to use ReturnEI.V2.xsd, Common.v2.xsd, and ReturnCommon.v2.xsd
* File 	
	* Added new optional field ‘hoursPaid’(EI line item)
	* Added two new optional fields ‘priorPeriodGrossAdjustment’and ‘priorPeriodPAYEAdjustment’(EI line items)
	* Added two new optional fields ‘totalPriorPeriodGrossAdjustment’ and ‘totalPriorPeriodPAYEAdjustment’
	* the employeePayFrequency field has changed from optional to required
	* Added three new optional fields ‘essEarnings’, ‘slcirDeductions’ and ‘slborDeductions’(EI line items)
	* Updated employeeName to allow 255 characters, previously this was 20
	* Removed values from TaxCode table: 'ESS', 'SLCIR' and 'SLBOR'
	* Added three new optional fields:  'totalESSEarnings',  'totalSLCIRDeductions' and  'totalSLBORDeductions'.
	* Added note to clarify use of childSupportCode
	* There is a behaviour change between EI v1 and EI v2. In EI v1, a return can be filed and then immediately amended after receiving a successful response. An EI v2, a return must be processed in order to be amended. Returns will process within 5 minutes. 
* Retrieve Return
	* New optional fields above will also be included in the Retrieve Return response
	* Added note to Retrieve Return to clarify that it will return all existing fields on the return
* Prepop
	* Updated employeeName to allow 255 characters, previously this was 20
* Retrieve Status
	* Responses now include minorFormType
	* SubmissionKey is now optional in the request body
	* Now supports multiple return statuses(repeating elements)	
* Employment Information-specific response codes
	* Added new response code 170: 'The provided tax code is invalid'. Used to detect when tax code supplied is either ESS, SLCIR or SLBOR. 
	* Added response code 144: Return being submitted
	* Removed response code 166: EI temporarily locked for processing, not needed in V2	

## Amendment scenarios—differences between EI v1 and v2

Due to the introduction of Employment Information(EI) Gateway Service version 2, there are specific rules that service providers must adhere to when submitting amendments for an existing EI return on a period. These rules apply both to EI returns submitted through Gateway Service version 2, as well as returns that are submitted through EI Gateway Service version 1. In order to support amending prior EI returns, both EI v1 and EI v2 must be supported by service providers. 

The EI version can be identified in the standard header’s majorFormType field:
* EI version 1 = “EI”
* EI version 2 = “EI2”

| Original Return | Amended Return (via Gateway) | Result | Action |
| --- | --- | --- | --- |
| EI v1 | EI v1 | Success | |
| | EI v2 | Failure –EI v2 Response Code 169: Submitted incorrect EI version (please refer to EI v2 build pack for more information on this response code).| This action is not allowed. Returns submitted through EI v1 must be amended with EI v1. |
| EI v2 | EI v1 | Failure –EI v1 Response Code 169: Submitted incorrect EI version (please refer to EI v1 build pack for more information on this response code).  | This action is not allowed. Returns submitted through EI v2 must be amended with EI v2. |
| | EI v2| Success | | 
	

## Message samples
-----------------

- Simulating EI returns operations:
    - PrePop
        - Positive response
            - [request sample](sample%20messages/body-ei-returnprepop-request.xml)
            - [response sample](sample%20messages/body-ei-returnprepop-response.xml)
    - File
        - Positive response
            - [request sample](sample%20messages/body-ei-returnfile-request.xml)
			- [response sample](sample%20messages/body-ei-returnfile-response.xml)
    - RetrieveStatus
        - Positive response
            - [request sample](sample%20messages/body-ei-returnstatus-request.xml)
            - [response sample](sample%20messages/body-ei-returnstatus-response.xml)
    - RetrieveFilingObligations
        - Positive response
            - [request sample](sample%20messages/body-ei-filingobligation-request.xml)
            - [response sample](sample%20messages/body-ei-filingobligation-response.xml)
    - RetrieveReturn
        - Positive response
            - [request sample](sample%20messages/body-ei-retrievereturn-request.xml)
			- [request sample](sample%20messages/body-eiv2-retrieve-return-ACC-Identifer-request.xml) ACC-Identifer
            - [response sample](sample%20messages/body-ei-retrievereturn-response.xml)

## Mock environment information
-----------------

- Mock URL endpoint
    -  https://empinfo.test.services.ird.govt.nz/ 

- Test scenarios
	- Employment Information test scenarios mind map
	
	![Test Scenarios](images/Employment%20Information%20Mock%20MindMap.png)

- Test data
	- The following test data can be tested in our Mock Services environment when submitting requests to the service operations
	- This table shows which scenarios (as per their numbers in the mindmap) require specific data to trigger the expected responses. 
	- Text in italics represents the name of the XML node in the request.
	
	
| Operation      | Scenario ID | Data                                 |
|----------------|-------------|--------------------------------------|
| Prepop         | ES-PP-1     | Employer IRD (_identifier_): 123041607 |
|                |             | _periodEndDate_: 2018-04-30            |
|                |             | _payDayDate_: 2018-04-10               |
| Prepop         | ES-PP-2     | Employer IRD (_identifier_): 123094018 |
|                |             | _periodEndDate_: 2018-12-31            |
|                |             | _payDayDate_: 2018-12-10               |
| RetrieveReturn | ES-RR-1     | Employer IRD (_identifier_): 123041607 |
|                |             | _payDayDate_: 2018-04-10               |
|                |             | _submissionKey_: 987654321             |
| RetrieveReturn | ES-RR-9     | Employer IRD (_identifier_): 123094018 |
|                |             | _payDayDate_: 2021-07-31               |
|                |             | _submissionKey_: 987654321             |


## Test environment information
-----------------

* Test scenarios
	- [Download test scenarios report template (Including Tax Code scenarios)](Payday%20Filing%20EIv2%20%28Including%20Tax%20Code%20scenarios%29%20-%20Test%20Report%20Template.docx)
	

* Test URL endpoints
	- Cloud gateway service: https://test5.services.ird.govt.nz:4046/gateway/gws/returns/
	- Native desktop gateway service: https://test5.services.ird.govt.nz/gateway2/gws/returns/
	- Cloud SOAP WSDL: https://test5.services.ird.govt.nz:4046/gateway/gws/returns/?wsdl
	- Native desktop SOAP WSDL: https://test5.services.ird.govt.nz/gateway2/gws/returns/?wsdl
            
## Production environment information
-----------------

* Production URL endpoint
	- Cloud gateway service: https://services.ird.govt.nz:4046/gateway/gws/returns/
	- Native desktop gateway service: https://services.ird.govt.nz/gateway2/gws/returns/
	- Cloud SOAP WSDL: https://services.ird.govt.nz:4046/gateway/gws/returns/?wsdl
	- Native desktop SOAP WSDL https://services.ird.govt.nz/gateway2/gws/returns/?wsdl
	