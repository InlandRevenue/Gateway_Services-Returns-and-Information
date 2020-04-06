![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Employment Information (EI) Software Development Kit (SDK)

Employees can file Employment information (EI) to us each pay cycle using the Return service.

### Latest Release V 2.0 - [view details](#V-2.0-update-details)

### Archive 
* [Employment Information V 1](../Archive/V1/Employment%20Information)

## Key documentation

- Business use cases
	- [view on IR website](../Payday%20filing%20-%20ED%20and%20EI%20GWS%20business%20use%20cases.pdf)
	
- Schemas and WSDLs
- View and download the [Common v1 XSD](../../Common%20XSD/Common.v2.xsd)
	- View and download the [Return Common v1 XSD](../../Common%20XSD/ReturnCommon.v2.xsd)
	- View and download the Employment Income (EI) return [XSD](ReturnEI.v2.xsd) and [WSDL](ReturnsEIDevWsdl.v2.wsdl) from this current directory
	
- Returns Service 
	- [Download the build pack](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20EI%20v2.pdf) to view data definitions of each operation and response status code definitions

- Find out about 
	- [Employee Details SDK](../Employee%20Details)
	- the defined tax rates and thresholds, tax types business rules, and calculations required for specific tax codes [on the IR website](https://www.ird.govt.nz/digital-service-providers/services-catalogue/returns-and-information/payday-filing/payroll-calculations-and-business-rules)
	- how to make employee deduction payments [on the IR website](https://www.ird.govt.nz/payroll-employers/returns-payments/payday-filing/)

## Environment information

- [Mock environment information - emulated services](#mock-environment-information)

- [Mock Environment Information - Emulated Services](#mock-environment-information)

- [Production environment information - URL endpoints](#Production-Environment-Information)	

## Supporting services

* [Service: Identity and Access](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access) – view how to integrate, OAuth requests and responses message samples and build pack
* [Service: Intermediation](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Service%20-%20Intermediation)

* Service: Identity and Access – view [How to integrate, OAuth requests and responses message sample and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access) 
* Service: Intermediation [Service - Intermediation](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Service%20-%20Intermediation)	

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
            - [response sample](sample%20messages/body-ei-retrievereturn-response.xml)

## Mock environment information
-----------------

- Mock URL endpoint
    - https://mock-ei.ird.digitalpartner.services/ 

- Test scenarios
	- Employment Information test scenarios mind map
	
	![Test Scenarios](images/Employment_Information_Test_Scenarios_Mind_Map.png)

- Test data
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


## Test environment information
-----------------

* Test scenarios
	- [Download test scenarios report template](Payday%20Filing%20EI%20-%20Test%20Report%20Template.docx)

* Test URL endpoints
	- Cloud gateway service: https://test3.services.ird.govt.nz:4046/gateway/gws/returns/
	- Native desktop gateway service: https://test3.services.ird.govt.nz/gateway2/gws/returns/
	- Cloud SOAP WSDL: https://test3.services.ird.govt.nz:4046/gateway/gws/returns/?wsdl
	- Native desktop SOAP WSDL: https://test3.services.ird.govt.nz/gateway2/gws/returns/?wsdl
            
## Production environment information
-----------------

* Production URL endpoint
	- Cloud gateway service: https://services.ird.govt.nz:4046/gateway/gws/returns/
	- Native desktop gateway service: https://services.ird.govt.nz/gateway2/gws/returns/
	- Cloud SOAP WSDL: https://services.ird.govt.nz:4046/gateway/gws/returns/?wsdl
	- Native desktop SOAP WSDL https://services.ird.govt.nz/gateway2/gws/returns/?wsdl