<table>
<tr>
<th>Operation</th>
<th>CoAP Method</th>
<th>Path</th>
<th>Success</th>
<th>Failure</th>
</tr>

<tr>
<td>Read</td>
<td>GET Accept: Content Format ID (see section 6.4)</td>
<td>/{Object ID}/{Object Instance ID}/{Resource ID}</td>
<td>2.05 Content</td>
<td>4.00 Bad Request, 4.01 Unauthorized, 4.04 Not Found, 4.05 Method Not Allowed, 4.06 Not Acceptable</td>
</tr>

<tr>
<td>Discover</td>
<td>GET Accept: application/link-format</td>
<td>/{Object ID}/{Object Instance ID}/{Resource ID}</td>
<td>2.05 Content</td>
<td>4.00 Bad Request, 4.04 Not Found, 4.01 Unauthorized, 4.05 Method Not Allowed</td>
</tr>

<tr>
<td rowspan="2">Write</td>
<td>PUT Content Format:</td>
<td>/{Object ID}/{Object Instance ID}/{Resource ID}</td>
<td rowspan="2">2.04 Changed,<br /><br />2.31* Continue</td>
<td rowspan="2">4.00 Bad Request, 4.04 Not Found, 4.01 Unauthorized, 4.05 Method Not Allowed, 4.06 Not Acceptable,<br /><br />4.08* Request Entity Incomplete, 4.13* Request entity too large</td>
</tr> 

<tr>
<td>POST Content Format:</td>
<td>/{Object ID}/{Object Instance ID}</td>
</tr>

<tr>
<td>Write-Attributes</td>
<td>PUT</td>
<td>/{Object ID}/{Object Instance ID}/{Resource ID}?pmin={minimum period}&pmax={maximum period}&#38gt={greater than}&#38lt={less than}&st={step}</td>
<td>2.04 Changed</td>
<td>4.00 Bad Request, 4.04 Not Found, 4.01 Unauthorized, 4.05 Method Not Allowed</td>
</tr>

<tr>
<td>Execute</td>
<td>POST</td>
<td>/{Object ID}/{Object Instance ID}/{Resource ID}</td>
<td>2.04 Changed</td>
<td>4.00 Bad Request, 4.01 Unauthorized, 4.04 Not Found, 4.05 Method Not Allowed</td>
</tr>

<tr>
<td>Create</td>
<td>POST Content Format:</td>
<td>/{Object ID}</td>
<td>2.01 Created</td>
<td>4.00 Bad Request, 4.01 Unauthorized, 4.04 Not Found, 4.05 Method Not Allowed, 4.06 Not Acceptable</td>
</tr>

<tr>
<td>Delete</td>
<td>DELETE</td>
<td>/{Object ID}/{Object Instance ID}</td>
<td>2.02 Deleted</td>
<td>4.00 Bad Request, 4.01 Unauthorized, 4.04 Not Found, 4.05 Method Not Allowed</td>
</tr>

</table>
```
Table 3: Operation to Method and URI Mapping (Device Management & Service Enablement Interface)
```
