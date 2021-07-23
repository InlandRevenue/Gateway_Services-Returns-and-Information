![IRD logo](../Images/IRlogo.gif)
![Software Dev](../Images/SoftwareDev.png)

# AIM Returns Software Development Kit (SDK)

#### Release version 2.0

#### Archive

* [Release version 1.0](./archive/v1/)

## About the service

* Accounting income method (AIM) is a provisional tax option that uses accounting software to work out how much provisional tax small businesses will have to pay throughout the year.
* The gateway service used for AIM is the Return service which enables
	* checking if a customer is eligible to use AIM
	* filing statements of activity
	* query losses and residual taxes
	* query period balances
	* retrieve statements of activity already filed

## New features in release Version 2.0

* Changed to meet new legislation around mid-year entry. 
* File/prepop now 
	* allows for mid-year entry.
	* returns penalties or interest applied to the customer period. 
* File has 3 new elements to declare:
	* If the company is now earning over $5M 
	* If the company is deciding to enter AIM mid-year 
	* Declare any shareholders that the AIM company is paying provisional tax for.
	
## Key documentation

- Business use cases and worked examples
	- [Download and view](AIM-business-use-cases-worked-examples.pdf)
	
- Schemas and WSDLs
	- View and download the [common v2 xsd](../Common%20XSD/Common.v2.xsd)
	- View and download the [return service common v2 xsd](../Common%20XSD/ReturnCommon.v2.xsd)
	- View and download the AIM return [XSD](ReturnAIM.v2.xsd) and [WSDL](ReturnsAIMDevWsdl.v2.wsdl) from this current directory
	
- Build pack
	- [Download the Return service AIM v2.0 build pack](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20AIM%20-%20V2.0.pdf) to view data definitions of each operation and response status code definitions

- Message samples
    - [View message samples for requests and positive responses](#message-samples)		
	
## Environment information

- [Mock environment information - emulated services, mindmap and test data](#mock-environment-information)
	
- [Test environment information - Test scenarios report template, mindmap and URL endpoints](#test-environment-information)

- [Production environment information - URL endpoints](#Production-Environment-Information)	
	
## Supporting services

* Service: Identity and Access – view [how to integrate, OAuth requests, message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access) 
* Service: Intermediation – view [schemas, WSDLs, and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Service%20-%20Intermediation)

## Message samples:
-----------------

- Simulating AIM returns operations:
    - PrePop
        - Positive response
            - [request sample](sample%20messages/body-aim-returnprepop-request.xml)
            - [response sample](sample%20messages/body-aim-returnprepop-response.xml)
    - File
        - Positive response
            - [request sample](sample%20messages/body-aim-returnfile-request.xml)
            - [response sample](sample%20messages/body-aim-returnfile-response.xml)
    - RetrieveStatus
        - Positive response
            - [request sample](sample%20messages/body-aim-returnstatus-request.xml)
            - [response sample](sample%20messages/body-aim-returnstatus-response.xml)
    - RetrieveFilingObligations
        - Positive response
            - [request sample](sample%20messages/body-aim-filingobligation-request.xml)
            - [response sample](sample%20messages/body-aim-filingobligation-response.xml)
    - RetrieveReturn
        - Positive response
            - [request sample](sample%20messages/body-aim-retrievereturn-request.xml)
            - [response sample](sample%20messages/body-aim-retrievereturn-response.xml)

## Mock environment information:
-----------------

* Mock emulated services URL
	* https://aim.test.services.ird.govt.nz/

- AIM mock scenarios mindmap
	- [View larger image](images/AIM_Mock_Scenarios_Mindmap.png)
	![Mock Scenarios](images/AIM_Mock_Scenarios_Mindmap.png) 

- Test data
	- The following test data can be tested in our Mock Services environment when submitting requests to the service operations
	- This table shows which scenarios (as per their numbers in the mindmap) require specific data to trigger the expected responses. 
	- Text in italics represents the name of the XML node in the request.
	-
	
	Operation | Scenario ID | Data
	--- | --- | ---
	File | EMS_AIM0183 | Customer IRD (*identifier*): 123090918
	RetrieveFilingObligations | EMS_AIM042 | Customer IRD (*identifier*): 123064887 
	Prepop | EMS_AIM054 | Customer IRD (*identifier*): abcdefgh 
	Prepop | EMS_AIM063 | Customer IRD (*identifier*): 123064887 
	Prepop | EMS_AIM059 | Customer IRD (*identifier*): 123066081 
	RetrieveReturn | EMS_AIM028 | Customer IRD (*identifier*): 123081420 
	RetrieveStatus | EMS_AIM065 | Customer IRD (*identifier*): 123090918 
	 | | | *periodEndDate*: 2019-12-31 
	RetrieveStatus | EMS_AIM066 | Customer IRD (*identifier*): 123090918
	 | | | *periodEndDate*: 2017-12-31 
	RetrieveStatus | EMS_AIM034 | Customer IRD (*identifier*): 123090918 (two-monthly even filer)
	 | | | *periodEndDate*: 2017-11-30 

## Test environment information:
-----------------

* Test scenarios
	- [Download test scenarios report template](AIM%20-%20Return%20Sevice%20-%20Test%20Report%20Template.docx)
	- AIM Test Scenarios Mindmap - [view larger image](images/AIM_v2_Test_Scenarios_Mindmap.png)
	![Test Scenarios](images/AIM_v2_Test_Scenarios_Mindmap.png)

* Test URL endpoints
	* Cloud gateway service: https://test5.services.ird.govt.nz:4046/gateway/gws/returns/
	* Native desktop gateway service: https://test5.services.ird.govt.nz/gateway2/gws/returns/
	* Cloud SOAP WSDL: https://test5.services.ird.govt.nz:4046/gateway/gws/returns/?wsdl
	* Native desktop SOAP WSDL: https://test5.services.ird.govt.nz/gateway2/gws/returns/?wsdl	

## Production environment information:
-----------------

* Production URL endpoints

	- Cloud gateway service: https://services.ird.govt.nz:4046/gateway/gws/returns/
	- Native desktop gateway service: https://services.ird.govt.nz/gateway2/gws/returns/
	- (Cloud) SOAP WSDL: https://services.ird.govt.nz:4046/gateway/gws/returns/?wsdl
	- (Native desktop) SOAP WSDL: https://services.ird.govt.nz/gateway2/gws/returns/?wsdl