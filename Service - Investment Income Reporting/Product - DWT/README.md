![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Dividend withholding tax (DWT) Software Development Kit (SDK) for Investment Income Reporting

#### Latest Release V1.0 - 28 February 2020

## Summary of changes

* Description of interestZeroRated modified
* Description of deductedAmount modified
* Description of grossAmount modified
* The following error codes have been removed: 978, 977, 985, 983, 995.

Schema updates

* ReturnDWT.v1.xsd
* ReturnCommon.v2.xsd

## Key documentation

* Business use cases
	* [Download and view](III%20-%20DWT%20-%20GWS%20business%20use%20cases.pdf)
	
* Schemas and WSDLs
	- View and download the [common v2 xsd](../../Common%20XSD/Common.v2.xsd)
	- View and download the [return service common v2 xsd](../../Common%20XSD/ReturnCommon.v2.xsd)
	- View and download the DWT return [XSD](ReturnDWT.v1.xsd) and [WSDL](DWTDevWsdl.wsdl) from this current directory
	
- Build Pack
	- [Download the Return service - Investment Income Reporting build pack](../Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20III.pdf) to view data definitions of each operation and response status code definitions
	
- Message samples
    - [View message samples for requests and positive responses](#message-samples)
	
## Environment information

- Mock environment information - [mindmap and test data](../Test%20Details%20-%20IIR/README.md#mock-environment-information), [Mock URL endpoints](../Test%20Details%20-%20IIR/README.md#mock-environment) 
	
- Test environment information - [test scenarios report template and mindmap](../Test%20Details%20-%20IIR/README.md#test-environment-information) and [URL endpoints](../Test%20Details%20-%20IIR/README.md#test-environment-information)

- Production environment information - [URL endpoints](../Test%20Details%20-%20IIR/README.md#production-environment-information)

## Supporting services

* Service: Identity and Access – view [how to integrate, OAuth requests, message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

-----------------

## Message samples

- Simulating DWT returns operations:
    - File
		- [request sample](sample%20messages/DWTFileRequest.xml)
        - [positive response sample](sample%20messages/DWTFileResponse.xml)
	- File Amendment
		- [request sample by submission key](sample%20messages/DWTFileRequestUpdate_SubmissionKey.xml)
        - [positive response sample](sample%20messages/DWTFileResponse.xml)
    - RetrieveStatus
	    - [request sample by period end date](sample%20messages/DWTRetrieveStatusRequest_PeriodEndDate.xml)
		- [request sample by submission key](sample%20messages/DWTRetrieveStatusRequest_SubmissionKey.xml)
        - [positive response sample](sample%20messages/DWTRetriveStatusResponse.xml)
    - RetrieveReturn
		- [request sample by submission key](sample%20messages/DWTRetrieveReturnRequest_SubmissionKey.xml)
        - [positive response sample](sample%20messages/DWTRetrieveReturnResponse.xml)
