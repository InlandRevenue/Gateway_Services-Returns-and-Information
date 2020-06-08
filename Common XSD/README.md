![IRD logo](../Images/IRlogo.gif)
![Software Dev](../Images/SoftwareDev.png)

# Common XSDs

The common XSD is used across a range of IR service types that all use the Return service

| Version| XSDs   | Service Types | 
| --- | --- | --- |
| v1| <ul> <li> [Common.v1.xsd](Common.v1.xsd) </li>  <li> [ReturnCommon.v1.xsd](ReturnCommon.v1.xsd) </li> </ul>|  <ul> <li> Payday Filing v1 </li> <li> GST </li> </ul> | 
| v2 | <ul> <li>  [Common.v2.xsd](Common.v2.xsd) <br/> <li>  [ReturnCommon.v2.xsd](ReturnCommon.v2.xsd) </li>  </ul>| <ul> <li> Payday Filing v2 </li> <li> AIM v2 </li> <li> Income Tax </li> <li> Investment Income Reporting </li> </ul> |


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

