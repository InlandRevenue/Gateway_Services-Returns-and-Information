![IRD logo](../Images/IRlogo.gif)
![Software Dev](../Images/SoftwareDev.png)

# Donation Tax Credit Software Development Kit (SDK)

#### Release: V1.0   

The donation tax credit gateway service can be used to: 

* submit a new or amended donation tax credit claim form 
* query the processing status of a previously filed donation tax credit claim form 
* request a copy of a previously filed donation tax credit claim form. 

## Key Documentation:

* XSD Schemas 
	* View and download the Tax Credit Donation [XSD schema](xsd/ReturnREB.v1.xsd) 
    * View and download the [Common v2 and Return Common v2 XSD](../Common%20XSD/) common XSD directory
	
* Build pack
	* Download the [Return Service Income Tax build pack](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20INC%20v1.1.pdf) to view data definitions of each operation and response status code definitions		

* [Sample request and responses](#Sample-request-and-responses)

   
## Environment Information: 
- [Mock Environment Information - Emulated Services, Mindmap and Test data](test%20details/TestingInfomation.md#mock-environment-information)
- [Test Environment Information - Test Scenarios Report Template, Mindmap and URL Endpoints](test%20details/TestingInfomation.md#test-environment-information)
- [Production Environment Information - URL Endpoints](test%20details/TestingInfomation.md#Production-Environment-Information)	

---

## Sample request and responses

- File
    - [File request](sample%20messages/file_request_ir526_standalone.xml)
    - [File Response](sample%20messages/file_response.xml)
- RetrieveReturn
    - [RetrieveReturn request](sample%20messages/retrievereturn_request_ir526.xml)
    - [RetrieveReturn response](sample%20messages/retrievereturn_response_ir526.xml) 
- RetrieveReturn
    - [RetrieveStatus request](sample%20messages/retrievestatus_request_ir526.xml)
    - [RetrieveStatus response](sample%20messages/retrievestatus_response_ir526.xml)