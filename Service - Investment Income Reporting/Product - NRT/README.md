![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Non-Resident Withholding Tax (NRT) Software Development Kit (SDK) for Investment Income Reporting

#### Latest Release V1.0 - 28 February 2020

## Summary of changes

* Description of interestZeroRated modified
* Description of deductedAmount modified
* Description of grossAmount modified
* The following error codes have been removed: 978, 977, 985, 983, 995.

Schema updates

* ReturnNRT.v1.xsd
* ReturnCommon.v2.xsd

## Key documentation

- Business use cases
	- [Download and view](III%20-%20NRT%20-%20GWS%20business%20use%20cases.pdf)
	
- Schemas and WSDLs
	- View and download the [common v2 xsd](../../Common%20XSD/Common.v2.xsd)
	- View and download the [return service common v2 xsd](../../Common%20XSD/ReturnCommon.v2.xsd)
	- View and download the NRT return [XSD](ReturnNRT.v1.xsd) and [WSDL](NRTDevWsdl.wsdl) from this current directory

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

- File  
	- Request
		- [NRT on Interest](sample%20messages/File_Request_NRT_NRINT.xml) (NRINT)
	- Response
		- [NRT positive response sample](sample%20messages/File_Response_Generic.xml)
	
- File (Amendments)
	- Request
		- [Submission Key Method](sample%20messages/File_Request_NRT_NRINT_amendment_with_submission_key.xml) (NRINT)
    - Response		
		- [NRT positive response sample](sample%20messages/File_Response_Generic.xml)
	
- RetrieveReturn
	- [Request](sample%20messages/RetreveReturn_Request_NRT.xml)  (Casual Supplemental)
	- [Response](sample%20messages/RetreveReturn_Response_NRT.xml)  

- RetrieveStatus
	- With Submission Key
		- [Request](sample%20messages/RetrieveStatus_Request_with_submission_key.xml) 
		- [Response](sample%20messages/RetrieveStatus_Response_with_submission_key.xml) 
	- Without Submission Key
		- [Request](sample%20messages/RetrieveStatus_Request_without_submission_key.xml) 
		- [Response](sample%20messages/RetrieveStatus_Response_without_submission_key.xml) 	
