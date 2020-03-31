![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Interest pay as you earn (IPS) Software Development Kit (SDK) for Investment Income Reporting

#### Release version 1.0

## Key documentation

- Business use cases
	- [Download and view](III%20-%20IPS%20-%20GWS%20business%20use%20cases.pdf)
	
- Schemas and WSDLs
	- View and download the [common v2 xsd](../../Schema%20-%20Common/Common.v2.xsd)
	- View and download the [return service common v2 xsd](../../Service%20-%20Return/Latest/ReturnCommon.v2.xsd)
	- View and download the IPS return [XSD](ReturnIPS.v1.xsd) and [WSDL](IPSDevWsdl.wsdl) from this current directory
	
- Build Pack
	- [Download the Return service - Investment Income Reporting build pack](../Service%20-%20Return%20III/Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20III.pdf) to view data definitions of each operation and response status code definitions
	
- Message samples
    - [View message samples for requests and positive responses](#message-samples)

## Environment information

- Mock environment information
	- [Mindmap and test data](../Test%20Details%20-%20IIR/README.md#mock-environment-information)
	- [Mock URL endpoints](../Test%20Details%20-%20IIR/README.md#mock-environment)

- Test environment information
	- [Test scenarios report template and mindmap](../Test%20Details%20-%20IIR/README.md#test-environment-information)
	- [Test URL endpoints](../Test%20Details%20-%20IIR/README.md#test-environment-information)

- Production environment information
	- [Production URL endpoints](../Test%20Details%20-%20IIR/README.md#production-environment-information)	 

## Supporting services

* Service: Identity and Access – view [how to integrate, OAuth requests, message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

## Message samples
-----------------

- File
    - [request sample](sample%20messages/IPSFileRequest.xml)
    - [positive response sample](sample%20messages/IPSFileResponse.xml)
- File Amendment
    - [request sample as single filer](sample%20messages/IPSFileRequestUpdate_SingleFiler.xml)
    - [request sample as multi filer](sample%20messages/IPSFileRequestUpdate_MultiFiler.xml)
    - [positive response sample](sample%20messages/IPSFileResponse.xml)
- RetrieveStatus
    - [request sample by period end date](sample%20messages/IPSRetrieveStatusRequest_PeriodEndDate.xml)
    - [request sample by submission key](sample%20messages/IPSRetrieveStatusRequest_SubmissionKey.xml)
    - [positive response sample](sample%20messages/IPSRetriveStatusResponse.xml)
- RetrieveReturn
    - [request sample as single filer](sample%20messages/IPSRetrieveReturnRequest_SingleFiler.xml)
    - [request sample as multi filer](sample%20messages/IPSRetrieveReturnRequest_MultiFiler.xml)
    - [positive response sample](sample%20messages/IPSRetrieveReturnResponse.xml)
