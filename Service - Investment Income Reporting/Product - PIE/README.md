![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Portfolio investment entities (PIE) attributed income tax for Investment Income Reporting

#### Latest Release V1.0 - September 2020

## Key Documentation

- Business use cases
	- [Download and view](III%20-%20PIE%20-%20GWS%20business%20use%20cases.pdf)
	
- Schemas and WSDLs
	- View and download the [common v2 xsd](../../Common%20XSD/Common.v2.xsd)
	- View and download the [Return Service common v2 xsd](../../Common%20XSD/ReturnCommon.v2.xsd)
	- View and download the Annual PIE Reconciliation (_ANN_) return [XSD](ReturnPIEa.v1.xsd) and [WSDL](PIEaV1DevWsdl.wsdl) from this current directory
	- View and download the Annual PIE Certificates return (_CER_) [XSD](ReturnPIEc.v1.xsd) and [WSDL](PIEcV1DevWsdl.wsdl) from this current directory
	- View and download the Periodic PIE Return (without reconciliation) (_PRD_) return [XSD](ReturnPIEp.v1.xsd) and [WSDL](PIEpV1DevWsdl.wsdl) from this current directory
	
- Build Pack
	- [Download the Return service - Investment Income Reporting build pack](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20PIE.pdf) to view data definitions of each operation and response status code definitions

- Message samples
    - [View message samples for requests and positive responses](#message-samples)



## Supporting services

* Service: Identity and Access – view [how to integrate, OAuth requests, message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)

---
## Message samples

* File
	* Income Type ANN
		* [Request](sample%20messages/ANNFilePayload.xml)   
		* [Response](sample%20messages/ANNFileSuccessResponse.xml)  
		
	* Income Type CER
		* [Request](sample%20messages/CERFilePayload.xml)
		* [Response](sample%20messages/CERFileSuccessResponse.xml)  
	
	* Income Type PRD
		* [Request](sample%20messages/PRDFilePayload.xml)
		* [Response](sample%20messages/PRDFileSuccessResponse.xml)  
		
* RetrieveReturn
	* Income Type ANN 	
		* [Request](sample%20messages/ANNRetrieveReturnPayload.xml)
		* [Response](sample%20messages/ANNRetrieveReturnResponse.xml)
	* Income Type CER
		* [Request](sample%20messages/CERRetrieveReturnPayload.xml)
		* [Response](sample%20messages/CERRetrieveReturnResponse.xml)
	* Income Type PRD
		* [Request](sample%20messages/PRDRetrieveReturnPayload.xml)
		* [Response](sample%20messages/PRDRetrieveReturnResponse.xml)

		
* ReturnSatus	
	* Income Type ANN 	
		* [Request](sample%20messages/ANNRetrieveStatusPayload.xml)
		* [Response](sample%20messages/ANNRetrieveStatusResponse.xml)
	* Income Type CER
		* [Request](sample%20messages/CERRetrieveStatusPayload.xml)
		* [Response](sample%20messages/CERRetrieveStatusResponse.xml)
	* Income Type PRD
		* [Request](sample%20messages/PRDRetrieveStatusPayload.xml)
		* [Response](sample%20messages/PRDRetrieveStatusResponse.xml)

## Environment information

- Mock environment information - [mindmap and test data](../Test%20Details%20-%20IIR/README.md#mock-environment-information), [Mock URL endpoints](../Test%20Details%20-%20IIR/README.md#mock-environment) 
	
- Test environment information - [test scenarios report template and mindmap](../Test%20Details%20-%20IIR/README.md#test-environment-information) and [URL endpoints](../Test%20Details%20-%20IIR/README.md#test-environment-information)

- Production environment information - [URL endpoints](../Test%20Details%20-%20IIR/README.md#production-environment-information) 

## Supporting services

* Service: Identity and Access – view [how to integrate, OAuth requests, message samples and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access)



