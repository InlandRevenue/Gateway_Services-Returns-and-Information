![IRD logo](../../Images/IRlogo.gif)
![Software Dev](../../Images/SoftwareDev.png)

# Resident withholding tax (RWT) Software Development Kit (SDK) for Investment Income Reporting

#### Release version 1.0

### Latest Release V1.0 - 28 February 2020
## Summary of changes

• Description of interestZeroRated modified
• Description of deductedAmount modified
• Description of grossAmount modified
• The following error codes have been removed: 978, 977, 985, 983, 995.

Schema updates

• ReturnRWT.v1.xsd
• ReturnCommon.v2.xsd

## Key Documentation:

- Business use cases
	- [Download and view](III%20-%20RWT%20-%20GWS%20business%20use%20cases.pdf)
	
- Schemas and WSDLs
	- View and download the [common v2 xsd](../../Common%20XSD/Common.v2.xsd)
	- View and download the [Return Service common v2 xsd](../../Common%20XSD/ReturnCommon.v2.xsd)
	- View and download the RWT return [XSD](ReturnRWT.v1.xsd) and [WSDL](RWTDevWsdl.wsdl) from this current directory
	
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

* File
	* Income Type DIVINT
		* [Request](sample%20messages/RWT_File_Request_incomeType_DIVINT.xml)   
		* [Response](sample%20messages/RWT_File_Response_incomeType_DIVINT.xml)
		
	* Income Type MAORI
		* [Request](sample%20messages/RWT_File_Request_incomeType_MAORI.xml)
		* [Response](sample%20messages/RWT_File_Response_incomeType_MAORI.xml)		
	
	* Multiple Income Information
		* [Request](sample%20messages/RWT_File_Request_with_multiple_income_information.xml)
		* [Response](sample%20messages/RWT_File_Response_with_multiple_income_information.xml)	
		
	* Multiple Joint Account Holders
		* [Request](sample%20messages/RWT_File_Request_with_multiple_joint_account_holders.xml)
		* [Response](sample%20messages/RWT_File_Response_with_multiple_joint_account_holders.xml)	
	
* File Amendment
	* [File Amendment](sample%20messages/RWT_File_Request_amendment.xml)
	
	* Request Amendment by Reference Id
		* [Request](sample%20messages/RWT_File_Request_amendment_by_referenceId.xml)
		* [Response](sample%20messages/RWT_File_Response_amendment_by_referenceId.xml)
		
* RetrieveReturn
	* Retrieve Return with submission 	
		* [Request](sample%20messages/RWT_RetrieveReturn_Request_with_submission_key.xml)
		* [Response](sample%20messages/RWT_RetrieveReturn_Response_with_submission_key.xml)
	* Retrieve Return without submission 	
		* [Request](sample%20messages/RWT_RetrieveReturn_Request_without_submission_key.xml)
		* [Response](sample%20messages/RWT_RetrieveReturn_Response_without_submission_key.xml)
		
* ReturnSatus	
	* With submission Key
		* [Request](sample%20messages/RWT_ReturnSatus_Request_without_submission_key.xml)
		* [Response](sample%20messages/RWT_ReturnSatus_Request_with_submission_key.xml)
	* Without submission Key
		* [Request](sample%20messages/RWT_ReturnSatus_Response_without_submission_key.xml)
		* [Response](sample%20messages/RWT_ReturnSatus_Response_with_submission_key.xml)
