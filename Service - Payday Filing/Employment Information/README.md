![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Employment Information (EI) Returns Software Development Kit (SDK)

## Key Documentation:

- Business use cases
	- [view on IR website](https://www.classic.ird.govt.nz/resources/9/5/95275fd7-967a-4b87-877f-a8968807e45e/Payday+filing+-+Employment+Information+business+use+cases.pdf)
	
- Schemas and WSDLs
	- View and download the [Common v2 and Return Common v2 XSD](../../Common%20XSD/)
	- View and download the Employment Income (EI) return [XSD](ReturnEI.v2.xsd) and [WSDL](ReturnsEIDevWsdl.wsdl) from this current directory
	
- Returns Service 
	- [Download the build pack](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20EI.pdf) to view data definitions of each operation and response status code definitions

- Message Samples
    - [View Message samples for requests and positive responses](#message-samples)

- Find out about [Employee Details SDK, Payday Filing business rules and calculations](../)

## V2.0 Service Update:

The following key changes have been made to the Employment Information Return Service V2.0.

* Operations
	* Updated schema to use ReturnEI.V2.xsd, Common.v2.xsd, and ReturnCommon.v2.xsd
* File 	
	* Added new optional field‘hoursPaid’(EI line item)
	* Added two new optional fields ‘priorPeriodGrossAdjustment’and ‘priorPeriodPAYEAdjustment’(EI line items)
	* Added two new optional fields ‘totalPriorPeriodGrossAdjustment’ and ‘totalPriorPeriodPAYEAdjustment’
	* Added three new optional fields ‘essEarnings’, ‘slcirDeductions’, ‘slborDeductions’(EI line items)
	* Updated employeeName to allow 255 characters, previously this was 20
	* Removed values from TaxCode table: ESS,SLCIR,SLBOR
	* Added three new optional fields:ototalESSEarningsototalSLCIRDeductionsototalSLBORDeductions.
	* Added note to clarify use of childSupportCode
	* There is a behaviour change between EI v1 and EI v2. In EI v1, a return can be filed and then immediately amended after receiving a successful response. AnEI v2, a return must be processed in order to be amended. It can take up to one day for a return to be processed. 
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

Due to the introduction of Employment Information(EI) Gateway Service version 2, there are specific rules that service providers must adhere to when submitting amendments for an existing EI return on a period. These rules apply both to EI returns submitted through Gateway Service version 2, as well as returns that are submitted through EI Gateway Service version 1.In order to support amending prior EI returns, both EI v1 and EI v2 must be supported by service providers. 

The EI version can be identified in the standard header’s majorFormType field:
* EI version 1 = “EI”
* EI version 2 = “EI2”

| Original Return | Amended Return (via Gateway) | Result | Action |
| --- | --- | --- | ---|
| EI v1 | EI v1 | Success | |
| | EI v2 | Failure –EI v2 Response Code 169: Submitted incorrect EI version (please refer to EI v2 build pack for more information on this response code).| This action is not allowed. Returns submitted through EI v1 must be amended with EI v1. |
| EI v2 | EI v1 | Failure –EI v1 Response Code 169: Submitted incorrect EI version (please refer to EI v1 build pack for more information on this response code).  | This action is not allowed. Returns submitted through EI v2 must be amended with EI v2. |
| | EI v2| Success | | 

## Environment Information: 

- [Mock Environment Information - Emulated Services](#mock-environment-information)

- [Test Environment Information - Test Scenarios, mindmap and URL Endpoints](#test-environment-information)

- [Production Environment Information - URL Endpoints](#Production-Environment-Information)	

## Supporting Services:

* Service: Identity and Access – view [How to integrate, OAuth requests and responses message sample and build pack](../../Service%20-%20Identity%20and%20Access/Latest/) 
* Service: Intermediation [Service - Intermediation](../Service%20-%20Intermediation)	

## Message samples:
-----------------

- Simulating EI Returns Operations:
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
            - [response sample](sample%20messages/body-ei-retrievereturn-response.xml)

## Mock Environment Information:
-----------------

- Mock URL Endpoint
    - https://mock-ei.ird.digitalpartner.services/ 

- Test Scenarios
	- Employment Information Test Scenarios Mindmap
	
	![Test Scenarios](images/Employment_Information_Test_Scenarios_Mind_Map.png)

- Test Data
	- The following test data can be tested in our Mock Services environment when submitting requests to the service operations
	- This table shows which scenarios (as per their numbers in the mindmap) require specific data to trigger the expected responses. 
	- Text in italics represents the name of the XML node in the request.
	
	
	|Operation | Scenario ID | Data|
	|--- | --- | ---|
	|Prepop | EMS_EI001 | Employer IRD (*identifier*): 123041607|
	| | | | *periodEndDate*: 2018-04-30|
	| | | | *payDayDate*: 2018-04-10|
	|Prepop | EMS_EI002 | Employer IRD (*identifier*): 123094018|
	| | | | *periodEndDate*: 2018-12-31|
	| | | | *payDayDate*: 2018-12-10|
	| RetrieveReturn | EMS_EI017 | Employer IRD (*identifier*): 123041607|
	| | | | *periodEndDate*: 2018-04-30|
	| | | | *payDayDate*: 2018-04-10|
	| | | | *submissionKey*: 987654321|
	RetrieveReturn | EMS_EI017 | Employer IRD (*identifier*): 123094018|
	| | | | *periodEndDate*: 2018-12-31|
	| | | | *payDayDate*: 2018-12-10|
	| | | | *submissionKey*: 987654321|


## Test Environment Information:
-----------------

* Test Scenarios
	- [Download test scenarios report template](Payday%20Filing%20–%20Employment%20Information%20-%20Test%20Report%20Template.docx)

* Test URL Endpoints
	- Cloud Gateway Service: https://test3.services.ird.govt.nz:4046/gateway/gws/returns/
	- Native Desktop Gateway Service: https://test3.services.ird.govt.nz/gateway2/gws/returns/
	- Cloud SOAP WSDL: https://test3.services.ird.govt.nz:4046/gateway/gws/returns/?wsdl
	- Native Desktop SOAP WSDL: https://test3.services.ird.govt.nz/gateway2/gws/returns/?wsdl
            
## Production Environment Information:
-----------------

* Production URL Endpoints
	- Cloud Gateway Service: https://services.ird.govt.nz:4046/gateway/gws/returns/
	- Native Desktop Gateway Service: https://services.ird.govt.nz/gateway2/gws/returns/
	- Cloud SOAP WSDL: https://services.ird.govt.nz:4046/gateway/gws/returns/?wsdl
	- Native Desktop SOAP WSDL https://services.ird.govt.nz/gateway2/gws/returns/?wsdl