![IRD logo](../Images/IRlogo.gif)
![Software Dev](../Images/SoftwareDev.png)

# Common XSDs

The common XSD is used across a range of IR service types that all use the Return service

| XSDs | Version | Service Types | 
| --- | --- | --- |
| * [Common.v1.xsd](Common.v1.xsd) <br/> * [ReturnCommon.v1.xsd](ReturnCommon.v1.xsd) | v1 | * Payday Filing v1 <br/> * GST | 
| * [Common.v2.xsd](Common.v2.xsd) <br/> * [ReturnCommon.v2.xsd](ReturnCommon.v2.xsd) | v2 | * Payday Filing v2 <br/> * AIM v2 <br/> * Income Tax <br/> * Investment Income Reporting |


# Release Notes

<table>
    <thead>
        <th>Date</th> 
        <th>Schema</th> 
        <th>Description</th>
    </thead>
    <tbody>
        <tr>
            <td>13/05/2020</td>
            <td>Common.v1.xsd &amp; Common.v2.xsd </td>
            <td>  EmailAddressType regex updated to allow printable chars <code> ! # $ % &#x26; &#x27; * + - / = ? ^ _ &#x60; { | } ~ ; </code> as specificed by RFC 5322 </td>
        </tr>
    </tbody>
</table>

