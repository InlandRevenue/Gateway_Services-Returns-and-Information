![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

Employee Details (ED) Software Development Kit (SDK)
=======================================

Key Documentation:
-------------

- Business use cases
	- [Download and view](../Payday%20filing%20-%20ED%20and%20EI%20GWS%20business%20use%20cases.pdf)
	
- Schemas and WSDLs
	- View and download the [Common XSD](../../Common%20XSD/Common.v2.xsd)
	- View and download the [Return Service Common XSD](../../Common%20XSD/ReturnCommon.v2.xsd)
	- View and download the Employee Details (ED) [XSD](Employment.v2.xsd) and [WSDL](EmploymentV2DevWsdl.wsdl) from this current directory
	
- Employment Service 
	- [Download the build pack](Gateway%20Services%20Build%20Pack%20-%20Employment%20Service.pdf) to view data definitions of each operation and response status code definitions
	
- Message Samples
    - [View Message samples for requests and positive responses](#message-samples)

- Find out about [Employee Information SDK, payday filing business rules and calculations](../)

## V2.0 SERVICE UPDATES

The following key changes have been made to the Employment Service Return Service in preparation for the update to V2.0.

* Operations
	* Updated schema references from ‘Employment.xsd’ to ‘Employment.v2.xsd’

* Create
	* Updated ‘KiwiSaverStatus’, changedvalid options to: AK, OK, NK, CT, AE(Removed: OT, NM, CH)
	* Added new field EmployeeExemptIncome
	* Updated employeeNameOnEILine to allow 255 characters, previously this was 20
	* Added tax codes table to show valid tax codes. ESS, SLCIR, and SLBOR are no longer valid tax codes
	* Updated employeeKiwiSaverEligibility to use codes NE, EE, and EA. Add table of codes below fields

* Update
	* Removed ‘KiwiSaverStatus’ field as it is no longer used for the Update operation
	* Added new optional field ‘lateOptOutReason’
	* Added new optional field ‘otherLateOptOutReason’ field
	* Updated employeeNameOnEILinein updateBody and in employeeIdentifierto allow 255 characters, previously this was 20
	* Updated employeeKiwiSaverEligibility to use codes NE, EE, and EA. Add table of codes below fields.	
	
* RetrieveList
	* Updated employeeNameOnEILine to allow 255 characters, previously this was 20

* Response codes
	* Deleted codes 119, 120, 123 as they correspond to web request processing
	* Added code 124: ‘The start and/or stop date overlaps with multiple other records’
	* Added code 130: ‘The provided KiwiSaverStatus is not valid’. This response is returned when KiwiSaver Status is not one of the following values: AK, OK, NK, CT, AE. 
	* Added code 131: ‘The provided Employee Exempt Income type is not valid’. This response is returned when Exempt Income type is not one of the following: BLH, HPT, OES, RTA, TAO, VBS.
	* Added code 132: ‘The provided KiwiSaver Late Opt-Out Reason is invalid’
	* Added code 133: ‘Other Late Opt-Out Reason must be provided’
	* Added code 134: ‘Opt-Out is late, so other reason must be provided’
	* Added code 135: ‘Opt-Out must be set to true as lateOptOutReason has been provided’
	* Added code 136: ‘The provided employeeKiwiSaverEligibility status was invalid’

## Environment Information: 

- [Mock Environment Information - Emulated Services, Mindmap and Test data](#mock-environment-information)
	
- [Test Environment Information - Test Scenarios Report Template, Mindmap and URL Endpoints](#test-environment-information)

- [Production Environment Information - URL Endpoints](#Production-Environment-Information)

## Supporting Services:

* [Service: Identity and Access – view how to integrate, OAuth requests and responses message sample and build pack](https://github.com/InlandRevenue/Gateway_Services-Access) 
* [Service: Intermediation – view schemas, WSDLs, and build pack](../Service%20-%20Intermediation)

Message samples:
-----------------

- Simulating Employment Service Operations:
    - Create
        - Positive response
            - [request sample](sample%20messages/body-employment-create-request.xml)
            - [response sample](sample%20messages/body-employment-create-response.xml)
    - Terminate
        - Positive response
            - [request sample](sample%20messages/body-employment-terminate-request.xml)
            - [response sample](sample%20messages/body-employment-terminate-response.xml)
    - Update
        - Positive response
            - [request sample](sample%20messages/body-employment-update-request.xml)
            - [response sample](sample%20messages/body-employment-update-response.xml)
    - RetrieveList
        - Positive response
            - [request sample](sample%20messages/body-employment-retrievelist-request.xml)
            - [response sample](sample%20messages/body-employment-retrievelist-response.xml)


Mock Environment Information:
-----------------

* Mock URL Endpoint URL
    - https://mock-es.ird.digitalpartner.services/

* Test Scenarios 
	- Employee Details Test Scenarios Mindmap
	
	![Test Scenarios](images/Employee_Details_Test_Scenarios_Mind_Map.png)

*  Test Data
	- The following test data can be tested in our Mock Services environment when submitting requests to the service operations
	- This table shows which scenarios (as per their numbers in the mindmap) require specific data to trigger the expected responses. 
	- Text in italics represents the name of the XML node in the request.
	-

	Operation | Scenario ID | Data
	--- | --- | ---
	RetrieveList | EMS_ES081 | Employee IRD (*identifier*): 123114116
	Update | EMS_ES096 | Employee IRD (*identifier*): 123183711
	Create | EMS_ES095 | Employee IRD (*identifier*): 123183711
	Update | EMS_ES099 | employmentStartDate: today's date


Test Environment Information:
-----------------

* Test Scenarios
	- [Download the test scenarios report template](Payday%20Filing%20–%20Employee%20Details%20-%20Test%20Report%20Template.docx)


* Test URL Endpoint
    - Cloud Gateway Service: https://test3.services.ird.govt.nz:4046/gateway/gws/employment/
    - Native Desktop Gateway Service: https://test3.services.ird.govt.nz/gateway2/gws/employment/
            
Production Environment Information:
-----------------

* Production URL Endpoints

	- Cloud Gateway Service: https://services.ird.govt.nz:4046/gateway/gws/employment/
	- Native Desktop Gateway Service: https://services.ird.govt.nz/gateway2/gws/employment/
	- (Cloud) SOAP WSDL: https://services.ird.govt.nz:4046/gateway/gws/employment/?wsdl
	- (Native Desktop) SOAP WSDL: https://services.ird.govt.nz/gateway2/gws/employment/?wsdl