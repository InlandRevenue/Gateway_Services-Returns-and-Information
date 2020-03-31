![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Non-Resident Withholding Tax (NRT) Software Development Kit (SDK) for Investment Income Reporting

#### Release version 1.0

## Key documentation

- Business use cases
	- [Download and view](III%20-%20NRT%20-%20GWS%20business%20use%20cases.pdf)
	
- Schemas and WSDLs
	- View and download the [common v2 xsd](../../Schema%20-%20Common/Common.v2.xsd)
	- View and download the [Return Service common v2 xsd](../Service%20-%20Return%20III/Latest/)
	- View and download the NRT return [XSD](ReturnNRT.v1.xsd) and [WSDL](NRTDevWsdl.wsdl) from this current directory

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
	- Request
		- [NRT on Interest](sample%20messages/File_Request_NRT_NRINT.xml) (NRINT)
		- [NRT on Dividends](sample%20messages/File_Request_NRT_NRDIV.xml) (NRDIV)
		- [NRT on Copyright](sample%20messages/File_Request_NRT_COPYRT.xml) (COPYRT)
		- [NRT other royalties](sample%20messages/File_Request_NRT_ROYALT.xml) (ROYALT)
	- Response
		- [NRT positive response sample](sample%20messages/File_Response_Generic.xml)
	
- File (Amendments)
	- Request
		- [Submission Key Method](sample%20messages/ile_Request_NRT_NRINT_amendment_with_submission_key.xml) (NRINT)
	    - [Submission Key Reverse Replace](sample%20messages/File_Request_NRT_NRINT_amendment_ReverseReplace.xml)
    - Response		
		- [NRT positive response sample](sample%20messages/File_Response_Generic.xml)
	
- RetrieveReturn
	- [Request](sample%20messages/RetreveReturn_Request_NRT.xml)  (Casual Supplemental)
	- [Response](sample%20messages/RetreveReturn_Response_NRT.xml)  (NRINT, NRDIV & ROYALT)

- RetrieveStatus
	- With Submission Key
		- [Request](sample%20messages/RetrieveStatus_Request_with_submission_key.xml) 
		- [Response](sample%20messages/RetrieveStatus_Response_with_submission_key.xml) 
	- Without Submission Key
		- [Request](sample%20messages/RetrieveStatus_Request_without_submission_key.xml) 
		- [Response](sample%20messages/RetrieveStatus_Response_without_submission_key.xml) 	
