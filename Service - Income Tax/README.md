![IRD logo](../Images/IRlogo.gif)
![Software Dev](../Images/SoftwareDev.png)

# Income Tax and Donation Tax Credit through Gateway Services

#### Annual Return 2020+

[Archived 2019 Income Tax - XSD](./archive/2019/xsd/)	

## SUMMARY OF ANNUAL CHANGES 

2019—2020  
 
The following key changes have been made to the Income Tax Return Service build pack 
to accommodate annual changes for 2020: 
 
*  ‘Shareholder AIM tax paid’ will be returned from a ‘Prepop’ request when 
applicable. 
 
*  Non-resident foreign sourced income is no longer applicable for tax year 2020 
and onward. An error message will be returned if it is inadvertently submitted via 
gateway services. It has been REMOVED from form IR215. 
 
*  The following fields have been ADDED to a number of IR forms for 2020 returns: 
 
|Field | IR forms |
| --- | --- | 
|Shareholder AIM tax paid | IR3, IR4S |
|Residential income indicator  |IR3, IR3NR, IR4, IR6, IR7, IR8, IR9 |
|Total residential income  |IR3, IR3NR, IR4, IR6, IR7, IR7L/IR7P, IR8, IR9 |
|Residential rental deductions  |IR3, IR3NR, IR4, IR6, IR7, IR7L/IR7P, IR8, IR9 |
|Excess residential rental deductions brought forward |IR3, IR3NR, IR4, IR6, IR8, IR9 |
|Residential rental deductions claimed this year |IR3, IR3NR, IR4, IR6, IR8, IR9 |
|Net residential income | IR3, IR3NR, IR4, IR6, IR8, IR9 |
|Excess residential rental deductions carried forward |IR3, IR3NR, IR4, IR6, IR8, IR9 |
|Current year R&D non-refundable tax incentive credits to use or carry forward |IR3, IR3NR, IR4, IR6, IR8, IR9, IR44 |
|R&D tax incentive credits to be refunded |IR4 |
|Profit/loss from sale of property | IR8, IR9, IR44 | 
 
*  The following schemas have also changed for 2020: 
 
	*  ReturnIR3.v1.xsd  
	*  ReturnIR3NR.v1.xsd  
	*  ReturnIR4.v1.xsd  
	*  ReturnIR6.v1.xsd  
	*  ReturnIR7.v1.xsd  
	*  ReturnIR8.v1.xsd  
	*  ReturnIR9.v1.xsd  
	*  ReturnIR44.v1.xsd  
	*  IncomeReturnCommon.v1.xsd 

---

Income Tax reporting through gateway services enables organisations to:
* file detailed Income Tax information to Inland Revenue,
* additionally, if required they can 
	* amend a previously filed return
	* retrieve a return status or return data.
	


Return Service ― Income Tax	
* [Income Tax Software Development Kit (SDK)](IncomeTax.md)  
* [Donation Tax Credit Software Development Kit (SDK)](DonationTaxCredit.md)  


* Returns Service 
	* Download and view the [Return Service Income Tax build pack](Gateway%20Services%20Build%20Pack%20-%20Return%20Service%20-%20INC.pdf) to view data definitions of each operation and response status code definitions

Find out about: 
* the key changes for [income tax for individuals on the IR website](https://www.ird.govt.nz/income-tax-for-individuals)
* the key changes for [income tax for business and organisations on the IR website](https://www.ird.govt.nz/income-tax-for-business)
* [Explore our products and services](https://www.ird.govt.nz/software-providers/explore-products-contents/)

## Supporting Services:

* Service: Identity and Access – view [How to integrate, OAuth requests and responses message sample and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Identity%20and%20Access) 
* Service: Intermediation – view [Schemas, WSDLs, and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Service%20-%20Intermediation)
* Service: Return Status Push Notification - view [Schemas and build pack](https://github.com/InlandRevenue/Gateway_Services-Access/tree/master/Service%20-%20Software%20Intermediation)
