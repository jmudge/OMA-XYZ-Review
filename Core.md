|                                                                                     |     |
|-------------------------------------------------------------------------------------|-----|
| <img src="media/image1.jpeg" alt="Description: oma" width="192" height="60" />      |     |
| Lightweight Machine to Machine Technical Specification                              
                                                                                      
 Core                                                                                 |
| Draft Version 1\_1 – 15 Sep 2017                                                    |
| **Open Mobile Alliance**                                                            |
| <span id="header" class="anchor"></span>OMA-TS-LightweightM2M-V1\_1-Core-20170915-D |
|                                                                                     |     |
|                                                                                     |
|                                                                                     |     |

Use of this document is subject to all of the terms and conditions of the Use Agreement located at <http://www.openmobilealliance.org/UseAgreement.html>.

Unless this document is clearly designated as an approved specification, this document is a work in process, is not an approved Open Mobile Alliance™ specification, and is subject to revision or removal without notice.

You may use this document or any part of the document for internal or educational purposes only, provided you do not modify, edit or take out of context the information in this document in any manner. Information contained in this document may be used, at your sole risk, for any purposes. You may not use this document in any other manner without the prior written permission of the Open Mobile Alliance. The Open Mobile Alliance authorizes you to copy this document, provided that you retain all copyright and other proprietary notices contained in the original materials on any copies of the materials and that you comply strictly with these terms. This copyright permission does not constitute an endorsement of the products or services. The Open Mobile Alliance assumes no responsibility for errors or omissions in this document.

Each Open Mobile Alliance member has agreed to use reasonable endeavors to inform the Open Mobile Alliance in a timely manner of Essential IPR as it becomes aware that the Essential IPR is related to the prepared or published specification. However, the members do not have an obligation to conduct IPR searches. The declared Essential IPR is publicly available to members and non-members of the Open Mobile Alliance and may be found on the “OMA IPR Declarations” list at <http://www.openmobilealliance.org/ipr.html>. The Open Mobile Alliance has not conducted an independent IPR review of this document and the information contained herein, and makes no representations or warranties regarding third party IPR, including without limitation patents, copyrights or trade secret rights. This document may contain inventions for which you must obtain licenses from third parties before making, using or selling the inventions. Defined terms above are set forth in the schedule to the Open Mobile Alliance Application Form.

NO REPRESENTATIONS OR WARRANTIES (WHETHER EXPRESS OR IMPLIED) ARE MADE BY THE OPEN MOBILE ALLIANCE OR ANY OPEN MOBILE ALLIANCE MEMBER OR ITS AFFILIATES REGARDING ANY OF THE IPR’S REPRESENTED ON THE “OMA IPR DECLARATIONS” LIST, INCLUDING, BUT NOT LIMITED TO THE ACCURACY, COMPLETENESS, VALIDITY OR RELEVANCE OF THE INFORMATION OR WHETHER OR NOT SUCH RIGHTS ARE ESSENTIAL OR NON-ESSENTIAL.

THE OPEN MOBILE ALLIANCE IS NOT LIABLE FOR AND HEREBY DISCLAIMS ANY DIRECT, INDIRECT, PUNITIVE, SPECIAL, INCIDENTAL, CONSEQUENTIAL, OR EXEMPLARY DAMAGES ARISING OUT OF OR IN CONNECTION WITH THE USE OF DOCUMENTS AND THE INFORMATION CONTAINED IN THE DOCUMENTS.

© 2017 Open Mobile Alliance All Rights Reserved.
Used with the permission of the Open Mobile Alliance under the terms set forth above.

Contents

1. Scope 9

2. References 10

2.1 Normative References 10

2.2 Informative References 11

3. Terminology and Conventions 13

3.1 Conventions 13

3.2 Definitions 13

3.3 Abbreviations 13

4. Introduction 14

4.1 Version 1.0 15

5. Interfaces 16

5.1 Attributes 17

5.1.1 Attributes Definitions and Rules 17

5.1.2 Attributes Classification 18

5.2 Bootstrap Interface 20

5.2.1 LwM2M Bootstrap-Server 21

5.2.2 Bootstrap Information 21

5.2.3 Bootstrap Modes 22

5.2.4 Bootstrap Sequence 24

5.2.5 Bootstrap Security 25

5.2.6 Bootstrap and Configuration Consistency 25

5.2.7 Bootstrap Commands 25

5.3 Client Registration Interface 27

5.3.1 Register 28

5.3.2 Update 31

5.3.3 De-register 33

5.4 Device Management & Service Enablement Interface 33

5.4.1 Read 35

5.4.2 Discover 35

5.4.3 Write 36

5.4.4 Write-Attributes 36

5.4.5 Execute 37

5.4.6 Create 38

5.4.7 Delete 38

5.5 Information Reporting Interface 38

5.5.1 Observe 39

5.5.2 Notify 40

5.5.3 Cancel Observation 41

6. Identifiers and Resources 42

6.1 Resource Model 42

6.2 Object Versioning 43

6.2.1 General Policy 43

6.2.2 Object Version format 44

6.2.3 Object Definition and Object Version Usage 44

6.3 Identifiers 45

6.3.1 Endpoint Client Name 46

6.3.2 Reusable Resources 47

6.4 Data Formats for Transferring Resource Information 48

6.4.1 Plain Text 48

6.4.2 Opaque 48

6.4.3 TLV 48

6.4.4 JSON 56

7.3 Access Control 58

7.3.1 Access Control Object 58

7.3.2 Authorization 61

Appendix A. Change History (Informative) 64

A.1 Approved Version History 64

Appendix B. Static Conformance Requirements (Normative) 65

B.1 SCR for LwM2M Client 65

B.1.1 Bootstrap Interface 65

B.1.2 Client Registration 66

B.1.3 Device Management and Service Enablement Interface 66

B.1.4 Information Reporting 67

B.1.5 Data Format 67

B.1.6 Security 67

B.1.7 Mechanism 68

B.1.8 Objects 68

B.2 SCR for LwM2M Server 68

B.2.1 Bootstrap Interface 68

B.2.2 Client Registration 68

B.2.3 Device Management and Service Enablement Interface 69

B.2.4 Information Reporting 69

B.2.5 Data Format 70

B.2.6 Security 70

B.2.7 Mechanism 70

B.2.8 Objects 70

Appendix C. Data Types (Normative) 71

Appendix D. LwM2M Object Template and Guidelines (Normative) 73

D.1 Object Template 73

D.2 Open Mobile Naming Authority (OMNA) Guidelines 74

D.2.1 Object Registry 74

D.2.2 Resource Registry 75

Appendix E. LwM2M Objects defined by OMA (Normative) 76

E.1 LwM2M Object: LwM2M Security 76

E.1.1 UDP Channel Security: Security Key Resource Format 79

E.1.2 SMS Payload Security: Security Key Resource Format 79

E.1.3 Unbootstrapping 79

E.2 LwM2M Object: LwM2M Server 80

E.3 LwM2M Object: Access Control 81

E.4 LwM2M Object: Device 83

E.5 LwM2M Object: Connectivity Monitoring 87

E.6 LwM2M Object: Firmware Update 89

E.6.1 Firmware Update State Machine 92

E.6.2 Examples 93

E.6.3 Firmware Update Consideration 94

E.7 LwM2M Object: Location 94

E.8 LwM2M Object: Connectivity Statistics 95

Appendix F. Example LwM2M Client (Informative) 96

Appendix G. Storage of LwM2M Bootstrap Information on the Smartcard (Normative) 102

G.1 File structure 102

G.2 Bootstrap Information on UICC (Activated in 3G Mode) 102

G.2.1 Access to the file structure 102

G.2.2 Files Overview 103

G.2.3 Access Method 103

G.2.4 Access Conditions 103

G.2.5 Requirements on the 3G UICC 103

G.3 Files Description 103

G.3.1 Object Directory File, EF ODF 103

G.3.2 Bootstrap Data Object Directory File, EF DODF-bootstrap 104

G.3.3 EF LwM2M\_Bootstrap 105

Appendix H. Secure channel between Smartcard and LwM2M Device Storage for secure Bootstrap Data provisioning (Normative) 107

Appendix I. Media types 109

I.1 Media-Type application/vnd.oma.lwm2m+tlv Registration 109

I.2 Media-Type application/vnd.oma.lwm2m+json Registration 110

Appendix J. LwM2M Schema and Object Definition File (Informative) 111

Appendix K. LwM2M Schema 112

Appendix L. Example of Trigger Message from Server (Informative) 114

Figures

[Figure 1: The overall architecture of the LwM2M Enabler. 13](#_Toc492474242)

[Figure 2: The protocol stack of the LwM2M Enabler. 14](#_Toc492474243)

[Figure 3: Bootstrap 15](#_Toc492474244)

[Figure 4: Client Registration 15](#_Toc492474245)

[Figure 5: Device Management and Service Enablement 16](#_Toc492474246)

[Figure 6: Information Reporting 16](#_Toc492474247)

[Figure 7: Procedure of Client Initiated Bootstrap 22](#_Toc492474248)

[Figure 8: Procedure of Server Initiated Bootstrap 23](#_Toc492474249)

[Figure 9: Client Registration Interface example flows 27](#_Toc492474250)

[Figure 10: Client Registration Update example flows \#1 31](#_Toc492474251)

[Figure 11: Client Registration Update example flows \#2 32](#_Toc492474252)

[Figure 12: Example flows of Device Management & Service Enablement Interface 34](#_Toc492474253)

[Figure 13: Example flow for Information Reporting Interface for the RSSI Resource of the Connectivity Monitoring Object of the example client (Appendix E) 38](#_Toc492474254)

[Figure 14: Example of Minimum and Maximum periods in an Observation 40](#_Toc492474255)

[Figure 15: Relationship between LwM2M Client, Object, and Resources 41](#_Toc492474256)

[Figure 16: Example of Supported operations and Associated Access Control Object Instance 42](#_Toc492474257)

[Figure 17: TLV nesting 49](#_Toc492474258)

[Figure 18: Illustration of the relations between the LwM2M Access Control Object and the other LwM2M Objects 60](#_Toc492474259)

[Figure 28: Object link Resource simple illustration 72](#_Toc492474260)

[Figure 29: Firmware Update Mechanisms 93](#_Toc492474261)

[Figure 30: Example of a LwM2M Server pushing a firmware image to a LwM2M client 93](#_Toc492474262)

[Figure 31: Example of a client fetching a firmware image 93](#_Toc492474263)

[Figure 32: 3G UICC File Structure and Bootstrap data location 103](#_Toc492474264)

[Figure 33: Bootstrap Information transfer from Smartcard to LwM2M Device using Secure channel according to \[GLOBALPLATFORM\] \[GP SCP03\] \[GP AMD\_A\] 108](#_Toc492474265)

Tables

[Table 1: Relationship of operations and interfaces 16](#_Toc492475254)

[Table 2: Attribute Characteristics 17](#_Toc492475255)

[Table 3: &lt;PROPERTIES&gt; Class Attributes 18](#_Toc492475256)

[Table 4: &lt;NOTIFICATION&gt; class Attributes 19](#_Toc492475257)

[Table 5: Bootstrap Information List 20](#_Toc492475258)

[Table 6: Bootstrap Discover parameters 25](#_Toc492475259)

[Table 7: Registration parameters 28](#_Toc492475260)

[Table 8: Behaviour with Current Transport Binding and Mode 30](#_Toc492475261)

[Table 9: Update parameters 30](#_Toc492475262)

[Table 10: Read parameters 34](#_Toc492475263)

[Table 11: Discover parameters 34](#_Toc492475264)

[Table 12: Write parameters 35](#_Toc492475265)

[Table 13: Write-Attributes parameters 36](#_Toc492475266)

[Table 14: Execute parameters 36](#_Toc492475267)

[Table 15: Create parameters 37](#_Toc492475268)

[Table 16: Delete parameters 37](#_Toc492475269)

[Table 17: Observe parameters 39](#_Toc492475270)

[Table 18: Notify parameters 39](#_Toc492475271)

[Table 19: Object Version usage rules 44](#_Toc492475272)

[Table 20: LwM2M Identifiers 45](#_Toc492475273)

[Table 21: TLV format and description 48](#_Toc492475274)

[Table 22: JSON format and description 56](#_Toc492475275)

[Table 28: LwM2M Objects defined by OMA LwM2M 1.0 76](#_Toc492475276)

[Table 29: Object Instances of the example 96](#_Toc492475277)

[Table 30: LwM2M Security Object \[0\] 96](#_Toc492475278)

[Table 31: LwM2M Security Object \[1\] 97](#_Toc492475279)

[Table 32: LwM2M Security Object \[2\] 97](#_Toc492475280)

[Table 33: LwM2M Server Object \[0\] 99](#_Toc492475281)

[Table 34: LwM2M Server Object \[1\] 99](#_Toc492475282)

[Table 35: Access Control Object \[0\] (for the LwM2M Server Object Instance 0) 99](#_Toc492475283)

[Table 36: Access Control Object \[1\] (for the LwM2M Server Object Instance 1) 100](#_Toc492475284)

[Table 37: Access Control Object \[2\] (for the Device Object Instance) 100](#_Toc492475285)

[Table 38: Access Control Object \[3\] (for the Connectivity Monitoring Object Instance) 100](#_Toc492475286)

[Table 39: Access Control Object \[4\] (for the Firmware Update Object) 101](#_Toc492475287)

[Table 40: Device Object Instance 101](#_Toc492475288)

[Table 41: Connectivity Monitoring Object Instance 101](#_Toc492475289)

Scope
=====

<span id="_Toc51149232" class="anchor"></span>This document specifies version 1.0 of the Lightweight Machine-to-Machine (LwM2M) protocol. This Lightweight M2M 1.0 enabler introduces the following features:

-   Simple resource model with the core set of objects and resources defined in this specification. The full list of registered objects can be found at \[OMNA\].

-   Operations for creation, update, deletion, and retrieval of resources.

-   Asynchronous notifications of resource changes.

-   Support for several serialization formats, namely TLV, JSON, Plain Text and binary data formats and the core set of LightweightM2M Objects.

-   UDP and SMS transport support.

-   Communication security based on the DTLS protocol supporting different types of credentials.

-   Queue Mode offers functionality for a LwM2M Client to inform the LwM2M Server that it may be disconnected for an extended period and when it becomes reachable again.

-   Support for use of multiple LwM2M Servers.

-   Provisioning of security credentials and access control lists by a dedicated LwM2M bootstrap-server.

References
==========

Normative References
--------------------

<table>
<tbody>
<tr class="odd">
<td>[3GPP-TS_23.003]</td>
<td>3GPP TS 23.003 “Numbering, addressing and identification”</td>
</tr>
<tr class="even">
<td>[3GPP-TS_23.032]</td>
<td>3GPP TS 23.032 “Universal Geographical Area Description (GAD)”</td>
</tr>
<tr class="odd">
<td>[3GPP-TS_23.038]</td>
<td>3GPP TS 23.038 “Alphabets and language-specific information”</td>
</tr>
<tr class="even">
<td>[3GPP-TS_23.040]</td>
<td>3GPP TS 23.040 “Technical realization of the Short Message Service (SMS)”</td>
</tr>
<tr class="odd">
<td>[3GPP-TS_24.008]</td>
<td>3GPP TS 24.008 “Mobile radio interface Layer 3 specification; Core network protocols; Stage 3”</td>
</tr>
<tr class="even">
<td>[3GPP-TS_25.331]</td>
<td>3GPP TS 25.331 “Radio Resource Control (RRC); Protocol specification”</td>
</tr>
<tr class="odd">
<td>[3GPP-TS_31.111]</td>
<td>3GPP TS 31.111 “Universal Subscriber Identity Module (USIM) Application Toolkit (USAT)”</td>
</tr>
<tr class="even">
<td>[3GPP-TS_31.115]</td>
<td>3GPP TS 31.115 “Remote APDU Structure for (U)SIM Toolkit applications”</td>
</tr>
<tr class="odd">
<td>[CoAP]</td>
<td><p>Shelby, Z., Hartke, K., Bormann, C., and B. Frank, “The Constrained Application Protocol (CoAP)”</p>
<blockquote>
<p>IETF RFC 7252 – June 2014</p>
</blockquote></td>
</tr>
<tr class="even">
<td><strong>[CoAP_Blockwise]</strong></td>
<td>C. Bormann, Z. Shelby, “Block-wise transfers in CoAP”, IETF RFC 7959.</td>
</tr>
<tr class="odd">
<td><strong>[CoAP-EST]</strong></td>
<td>S. Kumar, P. van der Stok, “EST based on DTLS secured CoAP (EST-coaps)”, draft-vanderstok-core-coap-est-00, October, 2016</td>
</tr>
<tr class="even">
<td><strong>[CoRE_Interface]</strong></td>
<td>Z. Shelby, M. Vial, “CoRE Interfaces”, draft-ietf-core-interfaces-01, Nov 2013</td>
</tr>
<tr class="odd">
<td><strong>[</strong><span id="reference_TS102_221" class="anchor"></span><strong>ETSI TS 102.221]</strong></td>
<td>“Smart Cards; UICC-Terminal interface; Physical and logical characteristics”, (ETSI TS 102 221 release 11), <a href="http://www.etsi.org/">URL:http://www.etsi.org/</a></td>
</tr>
<tr class="even">
<td><strong>[ETSI TS 102.223]</strong></td>
<td>“Smart Cards; Card Applications Toolkit (CAT) (Release 11)”<br />
<a href="http://www.etsi.org/">URL:http://www.etsi.org/</a></td>
</tr>
<tr class="odd">
<td>[ETSI TS 102.225]</td>
<td>ETSI TS 102 225 (V11.0.0): “Smart Cards; Secured packet structure for UICC based applications (Release 11)” <a href="http://www.etsi.org/">URL:http://www.etsi.org/</a></td>
</tr>
<tr class="even">
<td><strong>[FLOAT]</strong></td>
<td><blockquote>
<p>IEEE Computer Society (August 29, 2008). IEEE Standard for Floating-Point Arithmetic. IEEE. doi:10.1109/IEEESTD.2008.4610935. ISBN 978-0-7381-5753-5. IEEE Std 754-2008</p>
</blockquote></td>
</tr>
<tr class="odd">
<td><strong>[GLOBALPLATFORM]</strong></td>
<td>GlobalPlatform v2.2.1 - January 2011 -</td>
</tr>
<tr class="even">
<td><strong>[GP SCP03]</strong></td>
<td>GlobalPlatform Secure Channel Protocol 03 (SCP 03) Amendment D v1.1 Sept 2009</td>
</tr>
<tr class="odd">
<td>[IEEE 754-2008]</td>
<td>IEEE Computer Society (August 29, 2008). IEEE Standard for Floating-Point Arithmetic. IEEE. doi:10.1109/IEEESTD.2008.4610935. ISBN 978-0-7381-5753-5. IEEE Std 754-2008</td>
</tr>
<tr class="even">
<td>[IOPPROC]</td>
<td>“OMA Interoperability Policy and Process”, Version 1.13, Open Mobile Alliance™, OMA-IOP-Process-V1_13, <a href="URL:http://www.openmobilealliance.org/" class="uri">URL:http://www.openmobilealliance.org/</a></td>
</tr>
<tr class="odd">
<td>[LwM2M-AD]</td>
<td>“Lightweight Machine to Machine Architecture”, Open Mobile Alliance™, OMA-AD-LightweightM2M-V1_0, <a href="URL:http://www.openmobilealliance.org/" class="uri">URL:http://www.openmobilealliance.org/</a></td>
</tr>
<tr class="even">
<td>[OBSERVE]</td>
<td>Hartke, K. “Observing Resources in CoAP”, IETF RFC 7641.</td>
</tr>
<tr class="odd">
<td><strong>[</strong><span id="reference_PKCS_15" class="anchor"></span><strong>PKCS#15]</strong></td>
<td>“PKCS #15 v1.1: Cryptographic Token Information Syntax Standard”, RSA Laboratories, June 6, 2000. URL:<a href="ftp://ftp.rsasecurity.com/pub/pkcs/pkcs-15/pkcs-15v1_1.pdf" class="uri">ftp://ftp.rsasecurity.com/pub/pkcs/pkcs-15/pkcs-15v1_1.pdf</a></td>
</tr>
<tr class="even">
<td>[RFC2119]</td>
<td>“Key words for use in RFCs to Indicate Requirement Levels”, S. Bradner, March 1997, <a href="URL:http://www.ietf.org/rfc/rfc2119.txt" class="uri">URL:http://www.ietf.org/rfc/rfc2119.txt</a></td>
</tr>
<tr class="odd">
<td>[RFC2234]</td>
<td>“Augmented BNF for Syntax Specifications: ABNF”. D. Crocker, Ed., P. Overell. November 1997, <a href="URL:http://www.ietf.org/rfc/rfc2234.txt" class="uri">URL:http://www.ietf.org/rfc/rfc2234.txt</a></td>
</tr>
<tr class="even">
<td>[RFC4122]</td>
<td>“A Universally Unique Identifier (UUID) URN Namespace”, P. Leach, et al. July 2005, <a href="URL:http://www.ietf.org/rfc/rfc4122.txt" class="uri">URL:http://www.ietf.org/rfc/rfc4122.txt</a></td>
</tr>
<tr class="odd">
<td><strong>[RFC5246]</strong></td>
<td>The Transport Layer Security (TLS) Protocol Version 1.2</td>
</tr>
<tr class="even">
<td><strong>[RFC5280]</strong></td>
<td>D. Cooper, et al., “Internet X.509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile”, RFC 5280, May 2008.</td>
</tr>
<tr class="odd">
<td><strong>[RFC5289]</strong></td>
<td>TLS Elliptic Curve Cipher Suites with SHA-256/384 and AES Galois Counter Mode (GCM)</td>
</tr>
<tr class="even">
<td><strong>[RFC5487]</strong></td>
<td>Pre-Shared Key Cipher Suites for TLS with SHA-256/384 and AES Galois Counter Mode</td>
</tr>
<tr class="odd">
<td>[RFC5958]</td>
<td>S. Turner, “Asymmetric Key Packages”, RFC 5958, August 2010.</td>
</tr>
<tr class="even">
<td>[RFC6347]</td>
<td>Rescorla, E. and N. Modadugu, “Datagram Transport Layer Security Version 1.2”, <a href="http://tools.ietf.org/html/rfc6347">RFC 6347</a>, January 2012.</td>
</tr>
<tr class="odd">
<td>[RFC6655]</td>
<td>McGrew, D. and D. Bailey, “AES-CCM Cipher Suites for TLS”, RFC6655, July 2012.</td>
</tr>
<tr class="even">
<td>[RFC6690]</td>
<td>Shelby, Z. “Constrained RESTful Environments (CoRE) Link Format”, RFC6690, Aug 2012.</td>
</tr>
<tr class="odd">
<td>[RFC7292]</td>
<td>K. Moriarty, et al., “PKCS #12: Personal Information Exchange Syntax v1.1”, RFC 7292, July 2014.</td>
</tr>
<tr class="even">
<td>[SENML]</td>
<td>C. Jennings, Z. Shelby, J. Arkko, “Media Types for Sensor Markup Language (SENML)”, draft-jennings-senml-10 (work in progress), April 2013.</td>
</tr>
<tr class="odd">
<td>[TR-069]</td>
<td>Broadband Forum: “TR-069 CPE WAN Management Protocol” Issue: 1 Amendment 5.<br />
<a href="URL:http://www.broadband-forum.org/technical/download/TR-069_Amendment-5.pdf" class="uri">URL:http://www.broadband-forum.org/technical/download/TR-069_Amendment-5.pdf</a></td>
</tr>
<tr class="even">
<td>[WAP-WDP]</td>
<td>Wireless Application Protocol Forum, “Wireless Datagram Protocol”, June 2001.</td>
</tr>
</tbody>
</table>

Informative References
----------------------

<table>
<tbody>
<tr class="odd">
<td>[3GPP TS 31.116]</td>
<td>3GPP TS 31.116 (V10.2.0): “Remote APDU Structure for (Universal) Subscriber Identity Module (U)SIM Toolkit applications (Release 10)”</td>
</tr>
<tr class="even">
<td>[3GPP2 C.S0078-0]</td>
<td>3GPP2 C.S0078-0 (V1.0): “Secured packet structure for CDMA Card Application Toolkit (CCAT) applications”</td>
</tr>
<tr class="odd">
<td>[3GPP2 C.S0079-0]</td>
<td>3GPP2 C.S0079-0 (V1.0) “Remote APDU Structure for CDMA Card Application Toolkit (CCAT) applications”</td>
</tr>
<tr class="even">
<td>[DMREPPRO]</td>
<td>“OMA Device Management Representation Protocol, Version 1.3”.<br />
Open Mobile Alliance. OMA-TS-DM_RepPro-V1_3. <a href="URL:http://www.openmobilealliance.org" class="uri">URL:http://www.openmobilealliance.org</a></td>
</tr>
<tr class="odd">
<td>[DYNAMIC LINK]</td>
<td>“Dynamic Resource Linking for Constrained RESTful Environments”, Z.Shelby, Z.Vial, M.Koster, C.Groves, Oct 2016, draft-ietf-core-dynlink-01</td>
</tr>
<tr class="even">
<td>[ETSI TS 102 226]</td>
<td>ETSI TS 102 226 (V11.0.0): “Smart cards; Remote APDU structure for UICC based applications (Release 11)”</td>
</tr>
<tr class="odd">
<td>[ISO/IEC18031:2011]</td>
<td>ISO, “ISO/IEC 18031:2011: Information technology -- Security techniques -- Random bit generation”, November 2011, available at <a href="http://www.iso.org/iso/catalogue_detail.htm?csnumber=54945" class="uri">http://www.iso.org/iso/catalogue_detail.htm?csnumber=54945</a></td>
</tr>
<tr class="even">
<td>[OMADICT]</td>
<td>“Dictionary for OMA Specifications”, Open Mobile Alliance™,<br />
OMA-ORG-Dictionary-V2_9, <a href="URL:http://www.openmobilealliance.org/" class="uri">URL:http://www.openmobilealliance.org/</a></td>
</tr>
<tr class="odd">
<td>[OMNA]</td>
<td>“OMNA Lightweight M2M (LwM2M) Object &amp; Resource Registry”, <a href="http://www.openmobilealliance.org/"><em>URL:http://www.openmobilealliance.org/</em></a></td>
</tr>
<tr class="even">
<td>[RESOURCE DIRECTORY]</td>
<td>“CoRE Resource Directory”, Z.Shelby, M.Koster, C.Bormann, P.Van Der Stok Oct 2016, draft-ietf-core-resource-directory-09</td>
</tr>
<tr class="odd">
<td>[RFC3986]</td>
<td>T. Berners-Lee, R. Fielding, L. Masinter, “Uniform Resource Identifier (URI): Generic Syntax”, RFC 3986, January 2005.</td>
</tr>
<tr class="even">
<td>[RFC4086]</td>
<td>D. Eastlake, J. Schiller, S. Crocker, “Randomness Requirements for Security”, RFC 4086, June 2005.</td>
</tr>
<tr class="odd">
<td>[RFC6698]</td>
<td>P. Hoffman, J. Schlyter, “The DNS-Based Authentication of Named Entities (DANE) Transport Layer Security (TLS) Protocol: TLSA”, RFC 6698, August 2012.</td>
</tr>
<tr class="even">
<td>[RFC7459]</td>
<td>“Representation of Uncertainty and Confidence in the Presence Information Data Format Location Object (PIDF-LO)”, M. Thomson, J. Winterbootom, February 2015. <a href="URL:https://tools.ietf.org/html/rfc7459" class="uri">URL:https://tools.ietf.org/html/rfc7459</a></td>
</tr>
<tr class="odd">
<td>[SMS-DTLS]</td>
<td>“Transport Layer Security (TLS) / Datagram Transport Layer Security (DTLS) Profiles for the Internet of Things”, H. Tschofenig, T. Fossati, July 2016, <a href="http://www.ietf.org/rfc/rfc7925.txt">URL:http://www.ietf.org/rfc/rfc7925.txt</a></td>
</tr>
<tr class="even">
<td>[SP800-90A]</td>
<td>Elaine Barker, John Kelsey, “Recommendation for Random Number Generation Using Deterministic Random Bit Generators, NIST Special Publication 800-90A”, Revision 1, June 2015, available at <a href="http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-90Ar1.pdf" class="uri">http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-90Ar1.pdf</a></td>
</tr>
</tbody>
</table>

1.  Terminology and Conventions
    ===========================

    1.  Conventions
        -----------

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in \[RFC2119\].

All sections and appendixes, except “Scope” and “Introduction”, are normative, unless they are explicitly indicated to be informative.

Definitions
-----------

|                                                                        |                                                                                                                 |
|------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| LwM2M Bootstrap-Server Account                                         | LwM2M Security Object Instance with Bootstrap-Server Resource true                                              |
| LwM2M Server Account                                                   | LwM2M Security Object Instance with Bootstrap-Server Resource false and associated LwM2M Server Object Instance |
| Kindly consult \[OMADICT\] for more definitions used in this document. |

Abbreviations
-------------

Introduction
============

This enabler defines the application layer communication protocol between a LwM2M Server and a LwM2M Client, which is located in a LwM2M Device. The OMA Lightweight M2M enabler includes device management and service enablement for LwM2M Devices. The target LwM2M Devices for this enabler are mainly resource constrained devices. Therefore, this enabler makes use of a light and compact protocol as well as an efficient resource data model.

A Client-Server architecture is introduced for the LwM2M Enabler, where the LwM2M Device acts as a LwM2M Client and the M2M service, platform or application acts as the LwM2M Server. The LwM2M Enabler has two components, LwM2M Server and LwM2M Client. Four interfaces are designed between these two components as shown below:

-   Bootstrap

-   Client Registration

-   Device management and service enablement

-   Information Reporting

This architecture is shown in Figure 1. The LwM2M Enabler uses the Constrained Application Protocol (CoAP) with UDP and/or SMS bindings. Datagram Transport Layer Security (DTLS) provides security for UDP transport layer. The LwM2M Enabler protocol stack is shown in Figure 2.

<span id="_Ref403552316" class="anchor"><span id="_Toc492474242" class="anchor"></span></span>Figure 1: The overall architecture of the LwM2M Enabler.

<span id="_Ref403552330" class="anchor"><span id="_Toc492474243" class="anchor"></span></span>Figure 2: The protocol stack of the LwM2M Enabler.

Version 1.0
-----------

Version 1.0 of LwM2M brings in basic enablers needed, the following are the list of object enablers defined as part of core TS.

0. Security Object

1. Server Object

2. Access Control Object

3. Device Object

4. Connectivity Monitoring Object

5. Firmware Update Object

6. Location Object

7. Connectivity Statistics Object

Interfaces
==========

According to the architecture diagram \[LwM2M-AD\], there are four interfaces: 1) Bootstrap, 2) Client Registration, 3) Device Management and Service Enablement, and 4) Information Reporting. The operations for the four interfaces can be classified as uplink operations and downlink operations. The operations of each interface are defined in this section, and then mapped to protocol mechanisms in Section 8 Transport Layer Bindings and Encodings.

Figure 3 shows the operation model for interface “Bootstrap”. For this interface, the operations are an uplink operation named “Bootstrap-Request” and downlink operations named “Discover”, “Write”, “Delete” and “Bootstrap-Finish”. These operations are used to initialize the needed Object(s) for the LwM2M Client to register with one or more LwM2M Servers. With the “Write” operation on this interface, the LwM2M Client MUST write the value included in the payload regardless of an existence of the targeting Object Instance(s) or Resource(s) and access rights. In the mode where the Server is addressing the Bootstrap Information to the LwM2M Client, the Server MUST inform the LwM2M Client when this transfer is over by sending a “Bootstrap-Finish” command.

Bootstrapping is also defined using Factory Bootstrap (e.g., storage in Flash) or Bootstrap from Smartcard (storage in a Smartcard).

<span id="_Ref474353843" class="anchor"><span id="_Toc492474244" class="anchor"></span></span>Figure 3: Bootstrap

Figure 4 shows the operation model for the interface “Client Registration”. For this interface, the operations are uplink operations named “Registration”, “Update” and “De-register”.

<span id="_Ref474353940" class="anchor"><span id="_Toc492474245" class="anchor"></span></span>Figure 4: Client Registration

Figure 5 shows the logical operation model for interface “Device Management and Service Enablement”. For this interface, the operations are downlink operations named “Read”, “Create”, “Delete”, “Write”, “Execute”, “Write-Attributes”, and “Discover”. These operations are used to interact with the Resources, Resource Instances, Objects, Object Instances and/or their attributes exposed by the LwM2M Client. The “Read” operation is used to read the current values; the “Discover” operation is used to discover attributes and to discover which Resources are implemented in a certain Object; the “Write” operation is used to update the values; the “Write-Attributes” operation is used to change attribute values and the “Execute” operation is used to initiate an action. The “Create” and “Delete” operations are used to create or delete Instances.

<span id="_Toc492474246" class="anchor"></span>Figure 5: Device Management and Service Enablement

Figure 6 shows the operation model for interface “Information Reporting”. For this interface, the operations are downlink operations “Observe” or “Cancel Observation” and an uplink operation “Notify”. This interface is used to send the LwM2M Server a new value related to a Resource on the LwM2M Client.

<span id="_Toc492474247" class="anchor"></span>Figure 6: Information Reporting

The relationship between operations and interfaces is listed in the following Table 1.

| **Interface**                            | **Direction** | **Operation**                                                    |
|------------------------------------------|---------------|------------------------------------------------------------------|
| Bootstrap                                | Uplink        | Bootstrap-Request                                                |
| Bootstrap                                | Downlink      | Write, Discover, Delete, Bootstrap-Finish                        |
| Client Registration                      | Uplink        | Register, Update, De-register                                    |
| Device Management and Service Enablement | Downlink      | Create, Read, Write, Delete, Execute, Write-Attributes, Discover |
| Information Reporting                    | Downlink      | Observe, Cancel Observation                                      |
| Information Reporting                    | Uplink        | Notify                                                           |

<span id="_Ref474359085" class="anchor"><span id="_Ref368262857" class="anchor"><span id="_Toc492475254" class="anchor"></span></span></span>Table 1: Relationship of operations and interfaces

1.  Attributes
    ----------

    1.  ### Attributes Definitions and Rules

Attributes are metadata which can be attached to an Object, an Object Instance or a Resource. The value of an Attribute is LwM2M Server specific. These attributes can fulfil various roles: from just carrying information (e.g., Discover), up to containing parameters for Notification for example.

Attributes attached to Object, Object Instance, Resource, are respectively named O-Attribute, OI-Attribute, R-Attribute.

These Attributes MAY be carried in the message payload of Registration and Discover operations; they also MAY be updated - when writable - through the “Write-Attributes” operation.

Regardless to the LwM2M entity a given Attribute is attached to, the value of such an Attribute can be set at various levels: Object, Object Instance, Resource levels. Additionally, precedence rules apply when the same Attribute receives a value at different levels.

Several rules govern usage of LwM2M Attributes

-   The value of an O-Attribute MAY only be set at the Object level.

-   The value of an OI-Attribute MAY be set at the Object Instance level, and at the Object level.

> precedence rules:

-   Rule 1: When set at both levels, the value of the OI-Attribute set at Object Instance level will prevail.

-   Rule 2: When the Attribute value is set at the Object level, the scope of the OI-Attribute value extends to all the Instances of that Object, as long as the Rule 1 is respected.

<!-- -->

-   An R-Attribute MAY be set at 3 different levels: the Resource level, the Object Instance level and the Object level.

> precedence rules:

-   Rule 3: When set at the Resource level, the value of an R-Attribute prevails for that Resource whatever a value for this R-Attribute is also specified at an upper level (Object or Object Instance level).

-   Rule 4: When set at the Object Instance level, the scope of an R-Attribute value extends to all the Resources of that Object Instance as long as the Rule 3 is respected.

-   Rule 5: When set at the Object level, the scope of an R-Attribute value extends to all the resources of any Instance of that Object, as long as the Rule 4 is respected.

An attribute is fully determined by several characteristics which are listed in the table below:

| **Attribute characteristics** | **Description**                                                                                |
|-------------------------------|------------------------------------------------------------------------------------------------|
| Name                          | Attribute Name used to reference a specific Attribute in that Enabler (e.g., “Minimum Period”) |
| CoRE Link Param               | the string used when this Attribute is transferred to CoAP as a CoRE link parameter (ex pmin)  |
| Attachment                    | The Object, Object Instance or Resource, to which an Attribute applies                         |
| Assignation Level             | The Level (Object, Object Instance, Resource) where the value of the Attribute MAY be set.     |
| Class                         | Attributes are organized according to their purpose;                                           
                                                                                                  
  2 Class of Attributes are supported in LwM2M TS 1.0                                             
                                                                                                  
  &lt;NOTIFICATION&gt; gather Attributes regarding Notify operations parameters                   
                                                                                                  
  &lt;PROPERTIES&gt; gather Attributes regarding general information                              |
| Access Mode                   | R, W, RW: operation allowed by the LwM2M Server.                                               |
| Applicability                 | Condition to fulfil for allowing to attach such an Attribute                                   |
| Default Value                 | &lt;value&gt; or “-” or “ ”                                                                    |
| Value Type                    | Data Type (Refer Appendix C)                                                                   |
| Value                         | The Value carried by this Attribute : its data type must be of “Value Type”                    |

<span id="_Toc492475255" class="anchor"></span>Table 2: Attribute Characteristics

Some Attributes MAY be exposed to the LwM2M Server in the payload response to a “Discover” command (Section 5.4.2).

The value of some Attributes MAY be changed by the LwM2M Server in using the “Write-Attributes” command (Section 5.4.4); which Attribute are concerned are marked as “W” (writable) in the table of the next Section.

Note: A payload response to a “Discover” command is a list of application/link-format CoRE Links \[RFC6690\] which will include the LwM2M Attributes.

### Attributes Classification

&lt;PROPERTIES&gt; Class Attributes

The role of these Attributes is to provide metadata which may communicate helpful information to LwM2M Server for example easing data management.

Except when specifically mentioned as required, the LwM2M Server and LwM2M Client SHOULD support &lt;PROPERTIES&gt; Class Attributes listed Table 3.

| **Attribute**  
                 
 **Name**        | **CoRE Link param** | **Attachment** | **Assignation Level** | **Support Required**                                          | **Access Mode** | **Value Type** | **Default Value**     | **Applicability** | **Notes**                                                                                                                                |
|----------------|---------------------|----------------|-----------------------|---------------------------------------------------------------|-----------------|----------------|-----------------------|-------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Dimension      | dim                 | Resource       | Resource              | YES (Client)                                                  | R               | Integer        
                       
       \[0:255\]       | -                     | Multiple Resource | Number of Instantiations for a Multiple Resource                                                                                         |
| Object Version | ver                 | Object         | Object                | YES (Server)                                                  
                                                                    
     YES (Client) when able to support Objects in version &gt; 1.0  | R               | String         | 1.0 (Initial Version) |                   | Provide the version of the associated Object. The rules governing the usage of this parameter are specified in Section 6.2 and Table 19. |

<span id="_Ref461092563" class="anchor"><span id="Table_3" class="anchor"><span id="_Toc492475256" class="anchor"></span></span></span>Table 3: &lt;PROPERTIES&gt; Class Attributes

&lt;NOTIFICATION&gt; Class Attributes

The role of these R-Attributes is to provide parameters to the “Notify” operation; any readable Resource can have such R-attributes.

In the message sent by a LwM2M Client in response to an “Observe” operation, the current Resource value is reported; this event can be considered as the initial notification.

Each time a Resource notification is sent, the “Minimum Period” and “Maximum Period” timers associated to this Resource are restarted.

The notification of a Resource value will be sent when the combination of a change value condition (“Greater Than”, “Less Than”, OR “Step”) AND the “Minimum Period” timing conditions are both fulfilled for that Resource.

The LwM2M Server MUST support and LwM2M Client SHOULD support all the &lt;NOTIFICATION&gt; Class Attributes listed Table 4.

|                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                     |                |                       |              |                 |                |                   |                              |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|----------------|-----------------------|--------------|-----------------|----------------|-------------------|------------------------------|
| **Attribute**                                                                                                                                                                                                                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                                                                                                                                                                                                         
 **Name **                                                                                                                                                                                                                                                                                                                                                                                                                                               | **CoRE Link param** | **Attachment** | **Assignation Level** | **Required** | **Access Mode** | **Value Type** | **Default Value** | **Apply**                    
                                       
         **Condition**                 |
| Minimum Period                                                                                                                                                                                                                                                                                                                                                                                                                                         | pmin                | Resource       | Resource              
                           
    Object Instance        
                           
    Object                 | No           | RW              | Integer        | 0 (sec)           | Readable Resource            |
| *Notes:* The Minimum Period Attribute indicates the minimum time in seconds the LwM2M Client MUST wait between two notifications. If a Resource value has to be notified during the specified quiet period, the notification MUST be sent as soon as this period expires. In the absence of this parameter, the Minimum Period is defined by the Default Minimum Period set in the LwM2M Server Account.                                               |
| Maximum Period                                                                                                                                                                                                                                                                                                                                                                                                                                         | pmax                | Resource       | Resource              
                           
    Object Instance        
                           
    Object                 | No           | RW              | Integer        | -                 | Readable Resource            |
| *Notes:* The Maximum Period Attribute indicates the maximum time in seconds the LwM2M Client MAY wait between two notifications. When this “Maximum Period” expires after the last notification, a new notification MUST be sent. In the absence of this parameter, the “Maximum Period” is defined by the Default Maximum Period set in the LwM2M Server Account. The maximum period parameter MUST be not smaller than the minimum period parameter. |
| Greater Than                                                                                                                                                                                                                                                                                                                                                                                                                                           | gt                  | Resource       | Resource              | No           | RW              | Float          | -                 | Numerical                    
                                       
         &Readable Resource            |
| *Notes:* This “gt” Attribute defines a threshold high value. When this Attributes is present, the LwM2M Client MUST notify the Server each time the Observed Resource value crosses this threshold with respect to pmin parameter.                                                                                                                                                                                                                     |
| Less Than                                                                                                                                                                                                                                                                                                                                                                                                                                              | lt                  | Resource       | Resource              | No           | RW              | Float          | -                 | Numerical &Readable Resource |
| *Notes:* This “lt” Attribute defines a threshold low value. When this Attributes is present, the LwM2M Client MUST notify the Server each time the Observed Resource value crosses this threshold with respect to pmin parameter.                                                                                                                                                                                                                      |
| Step                                                                                                                                                                                                                                                                                                                                                                                                                                                   | st                  | Resource       | Resource              | No           | RW              | Float          | -                 | Numerical &Readable Resource |
| *Notes:* This “Step” Attribute defines a minimum change value between two notifications. When this Attribute is present, the change value condition will occur when the value variation since the last notification of the Observed Resource, is greater or equal to the “Step” Attribute value.                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                                                                                                                         
 When the “Step” change value condition occurs, the LwM2M Client MUST notify the Server with respect to “Period Minimum” rule.                                                                                                                                                                                                                                                                                                                           |

Note: the following rules MUST be respected:

-   **(“lt” value &lt; “gt” value)**

-   **(“lt” value + 2\*“st” values &lt;“gt” value)**

<span id="_Ref461092608" class="anchor"><span id="Table_4" class="anchor"><span id="_Toc492475257" class="anchor"></span></span></span>Table 4: &lt;NOTIFICATION&gt; class Attributes

Examples illustrating Attributes setting are provided in Section 8.2.5 (Device Management & Service Enablement Interface).

Bootstrap Interface
-------------------

The Bootstrap Interface is used to provision essential information into the LwM2M Client to enable the LwM2M Client to perform the operation “Register” with one or more LwM2M Servers.

During the Bootstrap Phase, the Client MAY ignore requests and flush all pending responses not related to the Bootstrap sequence. There are four bootstrap modes supported by the LwM2M Enabler:

-   Factory Bootstrap

-   Bootstrap from Smartcard

-   Client Initiated Bootstrap

-   Server Initiated Bootstrap

The last two Bootstrap modes require the help of a LwM2M Bootstrap-Server to achieve the ultimate goal to connect a LwM2M Client to their LwM2M Server(s).

The LwM2M Client MUST support at least one bootstrap mode specified in the Bootstrap Interface.

The LwM2M Bootstrap-Server MUST support Client Initiated Bootstrap and Server Initiated Bootstrap modes specified in the Bootstrap Interface.

This section describes what information is conveyed across the Bootstrap Interface, where the LwM2M Client puts that information and how to provision the Bootstrap Information for each of these bootstrap modes.<span id="_Ref339619648" class="anchor"></span>

1.  <span id="_Ref368312526" class="anchor"><span id="_Ref368312533" class="anchor"><span id="_Ref368312539" class="anchor"><span id="_Toc370916048" class="anchor"><span id="_Toc370922870" class="anchor"></span></span></span></span></span>

2.  1.  ### LwM2M Bootstrap-Server 

The LwM2M Bootstrap-Server is used to provision the LwM2M Client with the information required to contact the LwM2M Server(s).

In order for the LwM2M Client and the LwM2M Bootstrap-Server to establish a connection on the Bootstrap Interface, either in Client Initiated Bootstrap mode or in Server Initiated Bootstrap mode, the LwM2M Client MUST have a LwM2M Bootstrap-Server Account pre-provisioned in it.

### Bootstrap Information

This section specifies the information that needs to be configured in LwM2M Client for connecting to the LwM2M Server(s) or the LwM2M Bootstrap-Server. This Bootstrap Information can be available before performing the Bootstrap Sequence described in Section 5.2.4 or obtained as a result of the Bootstrap Sequence.

Bootstrap Information can be categorized into two types:

-   LwM2M Server Bootstrap Information

-   LwM2M Bootstrap-Server Bootstrap Information

The LwM2M Client MUST have the LwM2M Server Bootstrap Information after the Bootstrap Sequence specified in Section 5.2.4.

The LwM2M Client SHOULD have the LwM2M Bootstrap-Server Bootstrap Information.

The LwM2M Server Bootstrap Information is used by the LwM2M Client to register and connect to the LwM2M Server.

The LwM2M Server Bootstrap Information MUST contain at least a LwM2M Server Account.

Note that according to the LwM2M Server Account definition, a usual LwM2M Server Account is composed of a Security Object Instance and a Server Object Instance which are paired by sharing (respectively in Resource 10 and Resource 0 of that Objects) the same Short Server ID; a Short Server ID being unique in the LwM2M Client.

The LwM2M Server Bootstrap Information MAY additionally contain further Object Instances (e.g., Access Control, Connectivity Monitoring Object).

The LwM2M Client MAY be configured to use one or more LwM2M Server Account(s).

The LwM2M Client MUST have at most one LwM2M Bootstrap-Server Account.

The LwM2M Bootstrap-Server Bootstrap Information is used by the LwM2M Client to contact the LwM2M Bootstrap-Server to get the LwM2M Server Bootstrap Information.

The LwM2M Bootstrap-Server Bootstrap Information MUST be a LwM2M Bootstrap-Server Account.

|                                                  |                                                                                    |              |
|--------------------------------------------------|------------------------------------------------------------------------------------|--------------|
| **Bootstrap Information Type**                   | **Entity**                                                                         | **Required** |
| The LwM2M Server Bootstrap Information           | LwM2M Server Account                                                               | Yes\*        |
|                                                  | Additional Object Instances (e.g., Access Control, Connectivity Monitoring Object) | No           |
| The LwM2M Bootstrap-Server Bootstrap Information | LwM2M Bootstrap-Server Account                                                     
                                                                                      
  (Security Object instance)                                                          | No           |

<span id="_Toc492475258" class="anchor"></span>Table 5: Bootstrap Information List

\*the LwM2M Client MUST have at least one LwM2M Server Account after completion of Bootstrap Sequence specified in 5.2.4.

Please note that the LwM2M Client MUST accept Bootstrap Information sent via Bootstrap Interface without applying access control as specified in Section 7.3.2 Authorization.

### Bootstrap Modes

This section of the specification provides description and further information for each of the following Bootstrap Modes:

-   Factory Bootstrap

-   Bootstrap from Smartcard

-   Client Initiated Bootstrap

-   Server Initiated Bootstrap

    1.  #### Factory Bootstrap

In this mode, the LwM2M Client has been configured with the necessary Bootstrap Information prior to deployment of the device.

#### Bootstrap from Smartcard

When the Device supports a Smartcard, the LwM2M Client MUST retrieve and process the bootstrap data contained in the Smartcard as described in Appendix G. When the bootstrap data retrieval is successful, the LwM2M Client MUST process the bootstrap data from the Smartcard and SHOULD apply the Bootstrap Information to its configuration to enhance security benefits.

Due to the sensible nature of the Bootstrap Information, a secure channel SHOULD be established between the Smartcard and the LwM2M Device.

When such a secure channel is established between the Smartcard and the LwM2M Device, this secure channel MUST be based on \[GLOBALPLATFORM\] procedure, mainly described in Appendix H.

In this Bootstrap mode, the LwM2M Client MUST also ensure that the bootstrap data previously retrieved from the Smartcard is unchanged within the Smartcard. If bootstrap data is changed, and if the previous Bootstrap Information was applied from Smartcard, this previous Bootstrap Information MUST be disabled in the LwM2M Client and the LwM2M Client SHOULD apply the new Bootstrap Information from Smartcard to its configuration.

If the Smartcard is disabled (e.g., removing the Smartcard) then the Bootstrap Information created from the bootstrap data of the previous Smartcard MUST be deleted.

Checking for Smartcard change and disabling MUST be performed by LwM2M Client, each time a “Register” or “Update” operation take place, with a LwM2M Server provisioned from Smartcard. As usual, the Bootstrap security rules (5.2.5) then apply.

NOTE: Bootstrap Information in Smartcard can be updated by using Smartcard OTA protocol as specified in ETSI TS 102 225 \[ETSI TS 102.225\] / TS 102 226 \[ETSI TS 102 226\] and extensions such as 3GPP TS 31.115 \[3GPP TS 31.115\] / TS 31.116 \[3GPP TS 31.116\] and 3GPP2 C.S0078-0 \[3GPP2 C.S0078-0\] / C.S0079-0 \[3GPP2 C.S0079-0\].

#### Client Initiated Bootstrap

As defined in Section 5.2.4 Bootstrap Sequence, scenarios exist when the LwM2M Server is not configured within the LwM2M Client or attempts to perform the “Register” operation with LwM2M Servers have failed.

When these conditions occur, the Client Initiated Bootstrap mode provides a mechanism for the LwM2M Client to retrieve the Bootstrap Information from a LwM2M Bootstrap-Server.

The Client Initiated Bootstrap mode requires a LwM2M Bootstrap-Server Account preloaded in the LwM2M Client.

The minimum information that needs to be preloaded, is the security credentials required for a secure DTLS connection to the LwM2M Bootstrap-Server.

The figure below depicts the Client Initiated Bootstrap flow.

<span id="_Toc492474248" class="anchor"></span>Figure 7: Procedure of Client Initiated Bootstrap

Step \#0: Bootstrap-Request to bootstrap URI

The LwM2M Client sends a “Bootstrap-Request” operation to LwM2M Bootstrap-Server URI which has been pre-provisioned. When requesting the bootstrap, the LwM2M Client sends the LwM2M Client’s “Endpoint Client Name” as a parameter to allow the LwM2M Bootstrap-Server to provision the proper Bootstrap Information for the LwM2M Client.

Step \#1: Configure Bootstrap Information

The LwM2M Bootstrap-Server configures the LwM2M Client with the Bootstrap Information using the “Write” and/or “Delete” operation.

This Bootstrap mode MAY be used to configure some Resources of the Bootstrap Information in the LwM2M Client after initial bootstrap to update Bootstrap Information. In this case, all the Bootstrap Information is OPTIONAL.

Step \#2: Bootstrap-Finish Indication

When the LwM2M Server has finished to send all the Bootstrap Information to the LwM2M Client, the Server MUST send a Finish Bootstrap Indication to the Client to properly end this phase.

In case the LwM2M Client didn’t receive such a Finish Bootstrap Indication in a certain period (EXCHANGE\_LIFETIME) after the last received Bootstrap-Server command, the LwM2M Client MUST consider the Bootstrap procedure is failed.

EXCHANGE\_LIFETIME is defined in RFC 7252 \[CoAP\].

Step \#3: Clean-up after successful Bootstrapping

Successful Bootstrapping means that the Bootstrap-Finish command has been received by the LwM2M Client, AND the loaded Configuration is considered consistent by the LwM2M Client, i.e. the Bootstrap-Finish response code sent to the Bootstrap-Server is 2.04 (Changed); if these two conditions are not met, it is an unsuccessful Bootstrapping, and in that case the Bootstrap-Server Account MUST retain the values it had before the unsuccessful Bootstrapping sequence starts; consequently the following specification of this step\#3 doesn’t apply.

If the Bootstrap-Server Account Timeout Resource is instantiated in the Security Object Instance of the Bootstrap-Server, the LwM2M Client MUST purge the LwM2M Bootstrap-Server Account after the expiration time provided by the value of this Resource. If this Resource is not instantiated or its value is set to 0, the Bootstrap-Server Account lifetime is infinite (Section E.1 Security Object).

High entropy keys that are unique per device SHOULD be used for the LwM2M Bootstrap-Server Account. In that case the LwM2M Bootstrap-Server Account SHOULD be kept after bootstrapping i.e. the Bootstrap-Server Account Timeout Resource may be set to 0, or may stay not instantiated.

In case the Bootstrap-Server Account has to be replaced, the replacement and the purge of the previous Bootstrap-Server Account MUST properly take place before the Client sends the Bootstrap-Finish response message back to the Bootstrap-Server; otherwise a “4.06 Not Acceptable” Response code MUST be returned, and the previous Bootstrap-Server Account is still the only one active.

Note: If the original LwM2M Bootstrap-Server Account is purged from the device, and a new LwM2M Bootstrap-Server Account has NOT been created, further adding or removing of LwM2M Server Accounts will no longer be possible. Furthermore, updating security credentials e.g., X.509 certificates will also no longer be possible.

#### Server Initiated Bootstrap

In this mode, the LwM2M Bootstrap-Server configures the Bootstrap Information in the LwM2M Client without the LwM2M Client sending a Bootstrap-Request to the LwM2M Bootstrap-Server.

As the LwM2M Client does not initiate the “Bootstrap-Request” operation to the LwM2M Bootstrap-Server, the LwM2M Bootstrap-Server needs to know if a LwM2M Device is ready for bootstrapping before the LwM2M Client can be configured by the LwM2M Bootstrap-Server. The mechanism that a LwM2M Bootstrap-Server gains this knowledge is implementation specific. A common scenario is that elements in the Network Provider’s network informs the LwM2M Bootstrap-Server of the LwM2M Device when the LwM2M Device connects to the Network Provider’s network.

The Server Initiated Bootstrap mode requires a LwM2M Bootstrap-Server Account preloaded in the LwM2M Client. The minimum information that needs to be preloaded, is the security credentials required for a secure DTLS connection to the LwM2M Bootstrap-Server.

Once the LwM2M Bootstrap-Server has been notified that the LwM2M Device is ready to receive the Bootstrap Information, the LwM2M Bootstrap-Server configures the LwM2M Client with the Bootstrap Information by strictly replicating the procedures of the step\#1 step\#2 and step\#3 specified in the LwM2M Client Initiated Bootstrap mode.

The figure below depicts the Server Initiated Bootstrap flow.

<span id="_Toc492474249" class="anchor"></span>Figure 8: Procedure of Server Initiated Bootstrap

### Bootstrap Sequence

The LwM2M Client MUST respect step by step the procedural sequence specified below when attempting to bootstrap a LwM2M Device:

1.  If the LwM2M Device has Smartcard, the LwM2M Client tries to obtain Bootstrap Information from the Smartcard using the Bootstrap from Smartcard mode.
    Any Server Initiated Bootstrap attempt MUST be ignored by the LwM2M Client until it has tried to bootstrap via Smartcard or Factory Bootstrap mode.

2.  If the LwM2M Client is not configured using the Bootstrap from Smartcard mode, the LwM2M Client tries to obtain the Bootstrap Information by using Factory Bootstrap mode.
    Any Server Initiated Bootstrap attempt MUST be ignored by the LwM2M Client until it has tried to bootstrap via Smartcard or Factory Bootstrap mode.

3.  If the LwM2M Client has any LwM2M Server Object Instances from the previous steps, the LwM2M Client tries to register to the LwM2M Server(s) configured in the LwM2M Server Object Instance(s).

4.  If LwM2M Client fails to register to all the LwM2M Servers or the Client doesn’t have any LwM2M Server Object Instances, and the LwM2M Client hasn’t received a Server Initiated Bootstrap within the ClientHoldOffTime, the LwM2M Client performs the Client Initiated Bootstrap.<span id="_Toc355616250" class="anchor"><span id="_Toc355616817" class="anchor"><span id="_Toc355617116" class="anchor"><span id="_Toc355617312" class="anchor"><span id="_Toc355675043" class="anchor"><span id="_Toc355687972" class="anchor"><span id="_Toc355876289" class="anchor"><span id="_Toc357001259" class="anchor"><span id="_Toc355616251" class="anchor"><span id="_Toc355616818" class="anchor"><span id="_Toc355617117" class="anchor"><span id="_Toc355617313" class="anchor"><span id="_Toc355675044" class="anchor"><span id="_Toc355687973" class="anchor"><span id="_Toc355876290" class="anchor"><span id="_Toc357001260" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

5.  A Server Initiated Bootstrap attempt (e.g., for updating an LwM2M Server Account) remains possible, but only if the LwM2M Client retains the corresponding LwM2M Bootstrap-Server Account.

    1.  ### Bootstrap Security

The information conveyed through the Bootstrap Interface is sensitive and requires that communication session, security mechanisms and/or keys MUST be different instances from the one that is used for the other LwM2M Interfaces.

If the LwM2M Client or the LwM2M Bootstrap-Server needs to convey Bootstrap Information across the Bootstrap Interface, the LwM2M Client or the LwM2M Bootstrap-Server MUST establish a new secure communication session.

If security materials (e.g., LwM2M Server URI, Security Mode, and Security Key), are changed in the LwM2M Client, the LwM2M Client MUST disconnect the existing communication session between the LwM2M Server and LwM2M Client and establish a new secure communication session between the LwM2M Server and LwM2M Client using the security mechanism and/or keys which have been configured by Bootstrap Interface.

### Bootstrap and Configuration Consistency

When a Bootstrap Information is loaded in the LwM2M Client, any detected inconsistency MUST be reported in sending an error response code to the BOOTSTRAP-FINISH command.

As an example, during a Bootstrap phase, a Multi-Servers Configuration is loaded in a LwM2M Client with the associated Instances of the Access Control Object, while this particular LwM2M Client is not supporting the Access Control Object itself (Single Server context support only). In that case, the client is not able to find a satisfactory consistent configuration by itself, so that the Bootstrap sequence cannot be ended successfully.

On receipt of the error response code to the BOOTSTRAP-FINISH command, the Bootstrap-Server MAY take corrective actions before issuing a new BOOTSTRAP-FINISH command.

As specified in Section 5.2.3 “Bootstrap Modes”, the LwM2M Client MUST consider the Bootstrap procedure is failed when the LwM2M Client didn’t receive a BOOTSTRAP-FINISH command in a certain period (EXCHANGE\_LIFETIME).

### Bootstrap Commands

The mapping to CoAP Methods of the LwM2M Bootstrap Interface operations specified in this section, is detailed in chapter 8 of the present document (Transport Layer Binding and Encodings).

#### BOOTSTRAP-REQUEST

The Bootstrap-Request operation is only performed to initiate the Bootstrap Sequence in the “Client Initiated Bootstrap” mode.

The Bootstrap-Request operation has the following parameter:

|                               |              |                   |                                                                                                                                                 |
|-------------------------------|--------------|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **Parameter**                 | **Required** | **Default Value** | **Notes**                                                                                                                                       |
| /bs?ep={Endpoint Client Name} | Yes          | -                 | Indicates the LwM2M Client’s “Endpoint Name” in order to allow the LwM2M Bootstrap to provision the Bootstrap Information for the LwM2M Client. |

#### BOOTSTRAP-FINISH

The Bootstrap-Finish operation is only performed to terminate the Bootstrap Sequence previously initiated either in “Client Initiated Bootstrap” mode or in “Server Initiated Bootstrap” mode.

This command informs the LwM2M Client, that all the Bootstrap Information have been provided by the LwM2M Bootstrap-Server.

The Bootstrap-Finish operation has the following parameter:

|               |              |                   |           |
|---------------|--------------|-------------------|-----------|
| **Parameter** | **Required** | **Default Value** | **Notes** |
| /bs           | Yes          | -                 | -         |

#### Bootstrap DISCOVER

The “Discover” operation in Bootstrap Interface is different from the “Discover” operation in Device Management and Service Enablement interface.

The “Discover” operation on the Bootstrap Interface is used to discover which LwM2M Objects and Object Instances are supported by a certain LwM2M Client. In particular, the Security Object Instances (ID:0) are reported, while they are not accessible in Device Management and Service Enablement Interface. This operation is useful to clean-up or to update a LwM2M Client configuration (e.g., adding (removing) a LwM2M Server Account to (from) the LwM2M Client configuration).

The returned payload is a list of application/link-format CoRE Links \[RFC6690\] containing the LwM2M Enabler Version and for each targeted Object - in addition with the LwM2M Enabler Version and the Object Versions if they are required (see section 6.2 “Object Versioning” and Table 3 of this document &lt;PROPERTIES&gt; Class Attributes) - a sub-list of its Object Instances. In order to fully identify the Server supported by the Client, the Object Instances of the Server Account(s) (Object ID:0, Object ID:1) also includes the associated Short Server ID in the parameters list.

The Bootstrap-Server Security Object Instance doesn’t include a Short Server ID in its parameter list, since it has none associated with.

The targeted URI ‘/’ is accepted in place of the Object ID URI, for informing the Client to report all existing Object Instances.

The “Discover” operation has the following parameters:

|               |              |                   |                                              |
|---------------|--------------|-------------------|----------------------------------------------|
| **Parameter** | **Required** | **Default Value** | **Notes**                                    |
| Object ID     | No           | -                 | Indicates the Object. (/ means all Objects ) |

<span id="_Toc492475259" class="anchor"></span>Table 6: Bootstrap Discover parameters

For example:

-   when the “Discover” operation targets an Object with Object ID of 0 (Security Object), the response to the operation could be:

> lwm2m="1.0",&lt;/0/0&gt;;ssid=101, &lt;/0/1/&gt;, &lt;/0/2&gt;;ssid=102 with the meaning 3 LwM2M Servers are supported in that Client (that supports the LwM2M Enabler in version 1.0), while the Instance ID:1 of the Security Object ID:0 contains the credentials for the LwM2M Bootstrap-Server.

-   when the “Discover” operation targets an Object with ‘/’ the response to the operation could be

> lwm2m="1.0",&lt;/0/0&gt;;ssid=101,&lt;/0/1&gt;, &lt;/1/0/&gt;;ssid=101, &lt;/3/0&gt;,&lt;/5&gt;,&lt;/4&gt; with the meaning the Client is supporting (in LwM2M version 1.0) a Bootstrap-Server Account (/0/1), a Server Account (/0/0, /1/0) with a Short Server ID=101, A Device Object Instance (/3/0) and 2 other Objects which are not instantiated yet (Firmware Update /5, and Connectivity Monitory Object /4).

-   When the “Discover” addresses a LwM2M Client supporting the LwM2M Enabler in release 2.0, and containing a configuration with an hypothetical LwM2M Object ID:55 in Version 1.9, with one Instance (/55/0)

lwm2m="2.0",&lt;/0/0&gt;,&lt;/0/1&gt;;ssid=101, &lt;/1/0/&gt;;ssid=101, &lt;/3/0&gt;,&lt;/5&gt;,&lt;/4&gt;,&lt;/55&gt;;ver=1.9, &lt;/55/0&gt;

#### BOOTSTRAP WRITE

The “Write” operation in Bootstrap Interface is different from the “Write” Operation in Device Management and Service Enablement interface; the LwM2M Client MUST write the value included in the payload regardless of an existence of the targeted Object Instance(s) or Resource(s).

When the “Write” operation targets an Object or an Object Instance, the LwM2M Client MUST ignore optional resources it does not support in the payload. If the LwM2M Client supports optional resources not present in the payload, it MUST NOT instantiate these optional resources.

The Write operation can be sent multiple times.

Only in Bootstrap Interface, the “Write” MAY target just an Object ID, which will allow a Bootstrap-Server in using a TLV or JSON formatted payload, to populate a LwM2M Client in a single message containing several Instances of the same Object.

The Bootstrap “Write” operation has the following parameters:

|                    |              |                   |                                                                                                                       |
|--------------------|--------------|-------------------|-----------------------------------------------------------------------------------------------------------------------|
| **Parameter**      | **Required** | **Default Value** | **Notes**                                                                                                             |
| Object ID          | Yes          | -                 | Indicates the Object.                                                                                                 |
| Object Instance ID | No           | -                 | Indicates the Object Instance to write.                                                                               
                                                                                                                           
    If no Object Instance ID is indicated, Object Instance(s) MUST be specified in the TLV or JSON payload.                |
| Resource ID        | No           | -                 | Indicates the Resource to write. The payload is the new value for the Resource.                                       
                                                                                                                           
    If no Resource ID is indicated, then the value included payload is an Object Instance containing the Resource values.  |
| New Value          | Yes          | -                 | The new value included in the payload to update the Object Instance(s) or Resource.                                   |

#### BOOTSTRAP DELETE

The Delete operation targets one or several Object Instances and can be sent multiple times.

Only in Bootstrap Interface, the Delete operation MAY target any Instance or all Instances of any Object including the Security Object (ID:0), supported by the LwM2M Client. The two exceptions are the LwM2M Bootstrap-Server Account and the single Instance of the Mandatory Device Object (ID:3) which are not affected by any Delete operation.

When the Delete operation is used without any parameter (i.e. without Object ID parameter), all Instances of all Objects in the LwM2M Client MUST be removed (except for the two cases mentioned above); this functionality could be used for initialization purpose before LwM2M Bootstrap-Server sends Write operation(s) to the LwM2M Client.

The Delete operation has the following parameters:

|                    |              |                   |                                                                                                                                                                                                                                                     |
|--------------------|--------------|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Parameter**      | **Required** | **Default Value** | **Notes**                                                                                                                                                                                                                                           |
| Object ID          | No           | -                 | Indicates the Object from which Object Instance will be deleted; if no Object ID is indicated, all existing Object Instances (except the LwM2M Bootstrap-Server Account and the Instance of the Device Object) in the LwM2M Client will be deleted. |
| Object Instance ID | No           | -                 | Indicates the Object Instance to delete. If no Object Instance ID is indicated, then all Instances of the designated Object (Object ID MUST be provided) are deleted.                                                                               |

Client Registration Interface
-----------------------------

The LwM2M Server MUST support all the operations in this interface and the LwM2M Client MUST support “Register” and “Update” and SHOULD support “De-register” operation.

The Client Registration Interface[1] is used by a LwM2M Client to register with one or more LwM2M Servers, maintain each registration and de-register from a LwM2M Server. The registration is based on the Resource Model and Identifiers defined in Section 6 Identifiers and Resources. When registering, the LwM2M Client performs the “Register” operation and provides the properties the LwM2M Server requires to contact the LwM2M Client (e.g., End Point Name); maintain the registration and session (e.g., Lifetime, Queue Mode) between the LwM2M Client and LwM2M Server as well as knowledge of the Objects the LwM2M Client supports and existing Object Instances in the LwM2M Client. The registration is soft state, with a lifetime indicated by the Lifetime Resource of that LwM2M Server Object Instance. The LwM2M Client periodically performs an update of its registration information to the registered LwM2M Server(s) by performing the “Update” operation–possibly without any parameters. If the lifetime of a registration expires without receiving an update from the LwM2M Client:

-   the LwM2M Server MUST remove the registration of that Client;

-   the LwM2M Client MUST re-register (“Update” is not sufficient) to the LwM2M Server in order to be connected again, before initiating any further communication.

If the LwM2M Server or the LwM2M Client set a value to the Lifetime Resource of the Server Object Instance, this value becomes the new lifetime of the Registration session.

During “Register” or “Update” Operations, the parameter Lifetime – if present – MUST match the current value of the Mandatory Lifetime Resource of the LwM2M Server Object Instance.

Finally, when shutting down or discontinuing use of a LwM2M Server, the LwM2M Client performs a “De-register” operation.

The Binding Resource of the LwM2M Server Object informs the LwM2M Client of the transport protocol preferences of the LwM2M Server for the communication session between the LwM2M Client and LwM2M Server. The LwM2M Client SHOULD perform the operations with the modes indicated by the Binding Resource of the LwM2M Server Object Instance.

<span id="_Toc492474250" class="anchor"></span>Figure 9: Client Registration Interface example flows

### Register

Registration is performed when a LwM2M Client sends a “Register” operation to the LwM2M Server. After the LwM2M Device is turned on and the bootstrap procedure has been completed, the LwM2M Client MUST perform a “Register” operation to each LwM2M Server that the LwM2M Client has a Server Object Instance. Table 7 describes the parameters used for the “Register” operation.

The “Register” operation includes the Endpoint Client Name parameter along with other parameters listed in Table 7. The “Register” operation MUST include a value for the Endpoint Client Name parameter that is unique on that LwM2M Server.

Upon receiving a “Register” operation from the LwM2M Client, the LwM2M Server records the connection information of the registration message (e.g., source IP address and port or MSISDN) and uses this information for all future interactions with that LwM2M Client.

If the LwM2M Client sends a “Register” operation to the LwM2M Server even though the LwM2M Server has registration information of the LwM2M Client, the LwM2M Server removes the existing registration information and performs the new “Register” operation. This situation happens when the LwM2M Client forgets the state of the LwM2M Server (e.g., factory reset).

The LwM2M Server MUST support all the parameters listed at Table 7 and the LwM2M Client MUST support Endpoint Client Name, LwM2M Version, Lifetime, and Object and Object Instances and MAY support Binding Mode and SMS Number.

|                              |              |                   |                                                                                                                                                                                                                            |
|------------------------------|--------------|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Parameter**                | **Required** | **Default Value** | **Notes**                                                                                                                                                                                                                  |
| Endpoint Client Name         | Yes          |                   | See Section 147138816.6.3                                                                                                                                                                                                  |
| Lifetime                     | Yes          |                   | Indicates the expected lifetime of the registration for this LwM2M client. This value MUST be the same as the value held in the Resource named “Lifetime” of the corresponding instance of Server Object (ID \#1): /1/x/1. |
| LwM2M Version                | Yes          |                   | Indicates the version of the LwM2M Enabler that the LwM2M Client supports.                                                                                                                                                 |
| Binding Mode                 | No           | U                 | Indicates current binding and Queue mode of the LwM2M Client. This value MUST be the same as the value held in the Resource named “Binding” of the corresponding instance of Server Object (ID \#1): /1/x/7.               
                                                                                                                                                                                                                                
    The valid values of the parameter are listed in the Section 5.3.1.1.                                                                                                                                                        |
| SMS Number                   | No           |                   | The value of this parameter is the MSISDN where the LwM2M Client can be reached for use with the SMS binding.                                                                                                              |
| Objects and Object Instances | Yes          |                   | The list of Objects supported and Object Instances available on the LwM2M Client (Security Object ID:0 MUST not be part of this list).                                                                                     |

<span id="_Ref474359095" class="anchor"><span id="_Ref404851043" class="anchor"><span id="_Toc492475260" class="anchor"><span id="_Ref368263227" class="anchor"></span></span></span></span>Table 7: Registration parameters

A LwM2M Server MUST refuse a Client’s Registration request, if it doesn’t support the LwM2M Enabler version indicated by the Client (i.e. major digit of the LwM2M versions in Client and Server are different, or the LwM2M version supported by the Client – e.g., 1.1 - is superior to the LwM2M version supported by the Server – e.g., 1.0 -).

The list of Objects and Object Instances is included in the payload of the registration message. Except the Security Object (ID:0), all the mandatory Objects defined in the LwM2M Enabler (i.e. Server Object ID:1 and the Device Object ID:3) MUST be part of the registration payload list. The Security Object ID:0 MUST NOT be part of the Registration Objects and Object Instances list.

When an Object defined outside of a LwM2M Enabler has to-be-registered by the Client, but is not supported by the Server (unknown Object or unsupported Object version) it MUST be silently ignored by this Server and will not prevent the Client’s Registration request to be accepted.

The payload Media-Type of that registration message MUST be the Core Link Format (application/link-format) defined in \[RFC6690\], so that each Object is described as a Link according to that format. The Target component of the link is required, and consists of the Object path augmented of the Object Version Core link parameters “ver” if required as it is defined in section 6.2 of this document. Any other parameters included in the link MUST be silently ignored, unless specified for use by the LwM2M Enabler.

The payload for a LwM2M Client supporting LwM2M Server, Access Control, Device, Connectivity Monitoring and Firmware Update Objects from Appendix E would simply be:

&lt;/1&gt;, &lt;/2&gt;, &lt;/3&gt;, &lt;/4&gt;, &lt;/5&gt;

If Objects Instances are already available on the LwM2M Client at the time of registration, then the format would be (for the example client of Appendix F):

&lt;/1/0&gt;,&lt;/1/1&gt;,&lt;/2/0&gt;,&lt;/2/1&gt;,&lt;/2/2&gt;,&lt;/2/3&gt;,&lt;/2/4&gt;,&lt;/3/0&gt;,&lt;/4/0&gt;,&lt;/5&gt;

If the LwM2M Client supports the JSON data format for all the Objects it SHOULD inform the LwM2M Server by including the content type in the root path link using the ct= link attribute. An example is as follows (note that the content type value 11543 is the value assigned in the CoAP Content-Format Registry for the LwM2M JSON format).

&lt;/&gt;;ct=11543, &lt;/1/0&gt;,&lt;/1/1&gt;,&lt;/2/0&gt;,&lt;/2/1&gt;,&lt;/2/2&gt;,&lt;/2/3&gt;,&lt;/2/4&gt;,&lt;/3/0&gt;,&lt;/4/0&gt;,&lt;/5&gt;

#### Behaviour with Current Transport Binding and Mode

Behaviour of the LwM2M Server and the LwM2M Client is differentiated by Current Transport Binding and Mode. Current Transport Binding and Mode is decided by “Binding” Resource set by the LwM2M Server and whether SMS and/or Queue Mode are supported by the LwM2M Client. Queue Mode is useful when the LwM2M Device is not reachable by the LwM2M Server at all the times and it could help the LwM2M Client sleep longer. Table 8 describes the behaviour of the LwM2M Server and the LwM2M Client for each Current Transport Binding and Mode.

<table>
<tbody>
<tr class="odd">
<td><strong>Current Transport Binding and Mode</strong></td>
<td><strong>Behaviour</strong></td>
</tr>
<tr class="even">
<td>U (UDP)</td>
<td><p>The LwM2M Server expects that the LwM2M Client is reachable via the UDP binding at any time.<br />
The LwM2M Server MUST send requests to a LwM2M Client using the UDP binding. The LwM2M Client MUST send the response to such a request over the UDP binding.</p>
<p>This is the normal default mode of operation.</p></td>
</tr>
<tr class="odd">
<td>UQ (UDP with Queue Mode)</td>
<td>The Server MUST queue all requests to the LwM2M Client, sending requests via UDP when the LwM2M Client is on-line as described in Section 8.4 Queue Mode Operation.<br />
The LwM2M Server MUST send requests to a LwM2M Client using the UDP binding. The LwM2M Client MUST send the response to such a request over the UDP binding.</td>
</tr>
<tr class="even">
<td>S (SMS)</td>
<td><p>The LwM2M Server expects that the LwM2M Client is reachable via the SMS binding at any time.</p>
<p>The LwM2M Server MUST send requests to a LwM2M Client using the SMS binding. The LwM2M Client MUST send the response to such a request over the SMS binding.</p></td>
</tr>
<tr class="odd">
<td>SQ (SMS with Queue Mode)</td>
<td>The Server MUST queue all requests to the LwM2M Client, sending requests via SMS when the LwM2M Client is on-line as described in Section 8.4 Queue Mode Operation.<br />
Requests MUST be sent to the LwM2M Client using the SMS binding. The LwM2M Client MUST send the response to such a request over the SMS binding.</td>
</tr>
<tr class="even">
<td>US (UDP and SMS)</td>
<td><p>The LwM2M Server expects that the LwM2M Client is reachable via the UDP binding at any time.</p>
<p>The LwM2M Server expects that the LwM2M Client is reachable via the SMS binding at any time.</p>
<p>If the LwM2M Server sends requests to a LwM2M Client using the UDP binding, The LwM2M Client MUST send the response to such a request over the UDP binding.</p>
<p>If the LwM2M Server sends requests to a LwM2M Client using the SMS binding, The LwM2M Client MUST send the immediate response to such a request over the SMS binding.</p></td>
</tr>
<tr class="odd">
<td>UQS (UDP with Queue Mode and SMS)</td>
<td><p>The Server MUST queue all requests to the LwM2M Client, sending requests via UDP when the LwM2M Client is on-line as described in Section 8.4 Queue Mode Operation.</p>
<p>The LwM2M Server expects that the LwM2M Client is reachable via the SMS binding at any time.</p>
<p>If the LwM2M Server sends requests to a LwM2M Client using the UDP binding, The LwM2M Client MUST send the response to such a request over the UDP binding.</p>
<p>If the LwM2M Server sends requests to a LwM2M Client using the SMS binding, The LwM2M Client MUST send the immediate response to such a request over the SMS binding.</p>
<p>The LwM2M Server MAY request the LwM2M Client to perform “Update” operation via UDP by sending “Execute” operation on “Registration Update Trigger” Resource via SMS.</p></td>
</tr>
</tbody>
</table>

<span id="Table_7" class="anchor"><span id="_Ref373944813" class="anchor"><span id="_Ref404851114" class="anchor"><span id="_Toc492475261" class="anchor"></span></span></span></span>Table 8: Behaviour with Current Transport Binding and Mode

UQSQ and USQ are not supported.

### Update

Periodically or based on certain events within the LwM2M Client or initiated by the LwM2M Server, the LwM2M Client updates its registration information with a LwM2M Server by sending an “Update” operation to the LwM2M Server.

The “Update” operation can be initiated by the LwM2M Server via an “Execute” operation on the “Registration Update Trigger” Resource of the LwM2M Server Object. The LwM2M Client can perform an “Update” operation to refresh the lifetime of its registration to a LwM2M Server.

When any of the parameters listed in Table 9 changes, the LwM2M Client MUST send an “Update” operation to the LwM2M Server. This “Update” operation MUST contain only the parameters listed in Table 9 which have changed compared to the last registration parameters sent to the LwM2M Server.

|                              |              |
|------------------------------|--------------|
| **Parameter**                | **Required** |
| Lifetime                     | No           |
| Binding Mode                 | No           |
| SMS Number                   | No           |
| Objects and Object Instances | No           |

<span id="Table_8" class="anchor"><span id="_Ref368263443" class="anchor"><span id="_Ref404851179" class="anchor"><span id="_Toc492475262" class="anchor"></span></span></span></span>Table 9: Update parameters

When present,the Objects and Object Instance list MUST contain all the supported Objects and Object Instances available on the LwM2M Client. The Security Object ID:0 MUST NOT be part of Update Objects and Object Instances list.

The payload Media-Type of that “Update” message is the same as the one of the “Registration” message (section 5.3.1).

When an Object defined outside of a LwM2M Enabler is part of the Client update registration list, but is not supported by the Server (unknown Object or unsupported Object version), it MUST be silently ignored by this Server and will not prevent the Client’s Registration request to be accepted.

Two common operations are:

1.  Extending the lifetime of a registration

In this case the Client sends a Registration Update with no parameters.

Figure 10 shows an example exchange where the Client sends a Registration Update message that only refreshes the registration, i.e., the message does not contain any parameters. With the second Registration Update the Client changes the lifetime field to 6000 (seconds) and hence the lt parameter is included in the message.

<span id="_Toc492474251" class="anchor"></span>Figure 10: Client Registration Update example flows \#1

1.  Adding and removing Objects and Object Instances

In this case the client sends registration update with a body listing the complete list of objects and object instances.

Figure 11 shows an example exchange whereby the Client starts with an initial registration of two instances for a LwM2M Object with ID 12. Later, the server adds a third instance and subsequently deletes the second. In Registration Update messages, the Client includes the new list of Objects and Object Instances.

<span id="_Toc467140169" class="anchor"><span id="_Toc467142983" class="anchor"><span id="_Toc467678125" class="anchor"><span id="_Toc469902267" class="anchor"><span id="_Toc470163060" class="anchor"><span id="_Toc471907858" class="anchor"><span id="_Toc472088090" class="anchor"></span></span></span></span></span></span></span>

<span id="_Toc492474252" class="anchor"></span>Figure 11: Client Registration Update example flows \#2

### De-register

When a LwM2M Client determines that it no longer requires to be available to a LwM2M Server (e.g., LwM2M Device factory reset), the LwM2M Client SHOULD send a “De-register” operation to the LwM2M Server. Upon receiving this message, the LwM2M Server removes the registration information from the LwM2M Server.

Device Management & Service Enablement Interface
------------------------------------------------

The LwM2M Server and the LwM2M Client MUST support all the operations in this interface.

The Device Management and Service Enable Interface[2] is used by the LwM2M Server to access Object Instances and Resources available from a registered LwM2M Client. The interface provides this access through the use of “Create”, “Read”, “Write”, “Delete”, “Execute”, “Write-Attributes”, or “Discover” operations. The operations that Resource supports are defined in the Object definition using the Object Template. The Object Template is described in Appendix D.1 Object Template. The Normative Objects defined by the LwM2M Enabler are described in Appendix E.

The LwM2M Client MUST ignore LwM2M Servers operations on this interface during a Server Initiated Bootstrap.

The LwM2M Client MUST ignore the LwM2M Server operation on this interface until it received its Registration acknowledgement.

The LwM2M Server SHOULD NOT perform any operation on this interface before replying to the registration of this LwM2M Client.

<span id="_Toc492474253" class="anchor"></span>Figure 12: Example flows of Device Management & Service Enablement Interface

### Read

The “Read” operation is used to access the value of a Resource, an array of Resource Instances, an Object Instance or all the Object Instances of an Object. The “Read” operation has the following parameters:

|                    |              |                   |                                                                                                                                  |
|--------------------|--------------|-------------------|----------------------------------------------------------------------------------------------------------------------------------|
| **Parameter**      | **Required** | **Default Value** | **Notes**                                                                                                                        |
| Object ID          | Yes          | -                 | Indicates the Object.                                                                                                            |
| Object Instance ID | No           | -                 | Indicates the Object Instance to read.                                                                                           
                                                                                                                                      
    If no Object Instance ID is indicated, then the Object Instances of the Object, which the Server is authorized to, are returned.  |
| Resource ID        | No           | -                 | Indicates the Resource to read. If no Resource ID is indicated, then the whole Object Instance is returned.                      |

<span id="_Toc492475263" class="anchor"></span>Table 10: Read parameters

### Discover

The “Discover” operation is used to discover LwM2M Attributes attached to an Object, Object Instances, and Resources. This operation can be used to discover which Resources are instantiated in a given Object Instance. The returned payload is a list of application/link-format CoRE Links \[RFC6690\] for each targeted Object, Object Instance, or Resource, along with their attached Attributes including the Object Version attribute if required (see section 6.2 “Object Versioning” and Table 3 of this document &lt;PROPERTIES&gt; Class Attributes).

The “Discover” operation has the following parameters:

|                    |              |                   |                                |
|--------------------|--------------|-------------------|--------------------------------|
| **Parameter**      | **Required** | **Default Value** | **Notes**                      |
| Object ID          | Yes          | -                 | Indicates the Object.          |
| Object Instance ID | No           | -                 | Indicates the Object Instance. |
| Resource ID        | No           | -                 | Indicates the Resource.        |

<span id="_Toc492475264" class="anchor"></span>Table 11: Discover parameters

If Object ID is only specified, the LwM2M Client MUST respond to the “Discover” operation with the list of Object Instances and the list of their respective instantiated Resources. In addition, the list of Attributes which have be assigned to this Object level (see section 5.1.2 Attribute Classification) are also returned.

<span id="_Toc339381134" class="anchor"><span id="_Ref368208008" class="anchor"><span id="_Ref368312191" class="anchor"><span id="_Ref368312655" class="anchor"><span id="_Ref368313062" class="anchor"><span id="_Toc370916059" class="anchor"><span id="_Toc370922881" class="anchor"></span></span></span></span></span></span></span>For example:

-   when the “Discover” operation targets an Object with Object ID of 3, the response to the operation could be:

> &lt;/3&gt;;pmin=10, &lt;/3/0/1&gt;, &lt;3/0/2&gt;, &lt;/3/0/3&gt;, &lt;/3/0/4&gt;, &lt;3/0/6&gt;,&lt;3/0/7&gt;,&lt;3/0/8&gt;,&lt;3/0/11&gt;,&lt;3/0/16&gt;
>
> which means that the LwM2M Client supports the Device Info Object (Instance 0) Resources with IDs 1,2,3,4 6,7,8,11, and 16 among the Resources of Device Info Object, with an R-Attributes assigned to the Object level.

-   when the “Discover” operation targets an Object ID and Object Instance ID only, the list of Attributes assigned to that Object Instance MUST be reported, and the list of instantiated Resources and their attached Attribute MUST be returned in the response as well. For example: if Object ID is 3 and Object Instance ID is 0, then

> &lt;/3/0&gt;;pmax=60, &lt;/3/0/1&gt;, &lt;3/0/2&gt;, &lt;/3/0/3&gt;, &lt;/3/0/4&gt;, &lt;3/0/6&gt;;dim=8,&lt;3/0/7&gt;;dim=8;gt=50;lt=42.2,&lt;3/0/8&gt;;dim=8,&lt;3/0/11&gt;,&lt;3/0/16&gt;
>
> means that regarding the Device Info Object Instance, an R-Attribute has been assigned to this Instance level. And the LwM2M Client supports the multiple Resources 6, 7, and 8 with a dimension of 8 and has 2 additional Notification parameters assigned for Resource 7.

-   when the “Discover” operation targets an Object ID, Object Instance ID and Resource ID, the attributes of that Resource MUST be returned. In addition, the R-Attributes inherited from upper levels (Object and Object Instance level) are also reported for that Resource (The rules of Section 5.1.2 apply) For example: if Object ID is 3, and Resource ID is 7, then

> &lt;/3/0/7&gt;;dim=8;pmin=10;pmax=60;gt=50;lt=42.2
>
> with pmin assigned at the Object level, and pmax assigned at the Object Instance level.

-   If a Resource, an Object Instance, or an Object has attributes for multiple LwM2M Servers, then the Attributes returned in the link, MUST only be related to the Server which performed the DISCOVER request. As example, for the Device Object (ID:3) having the Resource ID:7 with two Observe operations from two Servers 1 & 2, then the answers to DISCOVER command on both Servers will be differentiated e.g.,

> from Server 1: DISCOVER /3/0/7 could provide the answer: &lt;/3/0/7&gt;;dim=8;gt=50;lt=42.2
>
> from Server 2: DISCOVER /3/0/7 could provide the answer: &lt;/3/0/7&gt;;dim=8;pmax=300;gt=80;lt=75.5

### Write

The “Write” operation is used to change the value of a Resource, the values of an array of Resources Instances or the values of multiple Resources from an Object Instance.

The request includes the value to be written encoded in one of the data format defined in section 6.4.

When more than a single value of a Resource has to be changed in a “Write” request, the TLV or JSON data format MUST be used.

The Write request MUST be rejected when the specified data format is not supported by the LwM2M Client.

LwM2M Client and LwM2M Server MUST support the following mechanisms to change multiple Resources or an array of Resource Instances:

-   Replace: replaces the Object Instance or the Resource(s) with the new value provided in the “Write” operation.

-   Partial Update: adds or updates Resources provided in the new value and leaves other existing Resources unchanged.

The “Write” operation has the following parameters:

|                    |              |                   |                                                                                                                       |
|--------------------|--------------|-------------------|-----------------------------------------------------------------------------------------------------------------------|
| **Parameter**      | **Required** | **Default Value** | **Notes**                                                                                                             |
| Object ID          | Yes          | -                 | Indicates the Object.                                                                                                 |
| Object Instance ID | Yes          | -                 | Indicates the Object Instance to write.                                                                               |
| Resource ID        | No           | -                 | Indicates the Resource to write. The payload is the new value for the Resource.                                       
                                                                                                                           
    If no Resource ID is indicated, then the value included payload is an Object Instance containing the Resource values.  |
| New Value          | Yes          | -                 | The new value included in the payload to update the Object Instance or a single Resource.                             |

<span id="_Toc492475265" class="anchor"></span>Table 12: Write parameters

### Write-Attributes

In LwM2M 1.0, only Attributes from the &lt;NOTIFICATION&gt; class MAY be changed in using the “Write-Attributes” operation.

The general rules for Attributes which are specified in Section 5.1.1 fully apply here. Table 3 in Section 5.1.2 provides explanation on the Attributes supported by the “Write-Attributes” operation: Minimum Period, Maximum Period, Greater Than, Less Than, and Step.

The operation permits multiple Attributes to be modified within the same operation.

Including &lt;NOTIFICATION&gt; class Attributes specified in Table 3 Section 5.3.1, the “Write-Attributes” operation has the following parameters:

Note: How to indicate the Attributes in the message payload is specified in \[CoRE\_Interface\].

|                                       |              |                   |                                                                                                                                                                                                                                                                 |
|---------------------------------------|--------------|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Parameter**                         | **Required** | **Default Value** | **Notes**                                                                                                                                                                                                                                                       |
| Object ID                             | Yes          | -                 | Indicates the Object.                                                                                                                                                                                                                                           |
| Object Instance ID                    | No           | -                 | Indicates the Object Instance. When this parameter is omitted, the Resource ID parameter MUST be ignored and Attributes in the command parameters are valid for all resources of all instances of the Object according to the precedence rules (section 5.1.1). |
| Resource ID                           | No           | -                 | Indicates the Resource. When this parameter is omitted, it means the Attributes of this commands are set at an upper level (Object or Object Instance level).                                                                                                   |
| &lt;NOTIFICATION&gt; class Attributes | Yes          |                   | Indicates which Attributes are concerned. When an Attribute is specified without value, it means this Attribute value is unset at the level specified in the command (Object, Object Instance or Resource level).                                               |

<span id="_Ref368263594" class="anchor"><span id="_Ref404851498" class="anchor"><span id="_Toc492475266" class="anchor"></span></span></span>Table 13: Write-Attributes parameters

### Execute

The “Execute” operation is used by the LwM2M Server to initiate some action, and can only be performed on individual Resources. A LwM2M Client MUST return an error when the “Execute” operation is received for an Object Instance(s) or Resource Instance(s).

Resource which supports “Execute” operation MAY have arguments.

|                    |              |                   |                                                                                              |
|--------------------|--------------|-------------------|----------------------------------------------------------------------------------------------|
| **Parameter**      | **Required** | **Default Value** | **Notes**                                                                                    |
| Object ID          | Yes          | -                 | Indicates the Object.                                                                        |
| Object Instance ID | Yes          | -                 | Indicates the Object Instance.                                                               |
| Resource ID        | Yes          | -                 | Indicates the Resource to execute.                                                           |
| Arguments          | No           | -                 | The arguments of the “Execute” operation are expressed in Plain Text format (syntax bellow). |

<span id="_Toc492475267" class="anchor"></span>Table 14: Execute parameters

In using ABNF, the syntax of the arguments, and arguments list is given as follows:

Examples of valid lists of arguments

1.  5

2.  2=’10.3’

3.  7, 0=’ <https://www.oma.org>’

4.  0,1,2,3,4

    1.  ### Create

The “Create” operation is used by the LwM2M Server to create Object Instance(s) within the LwM2M Client. The “Create” operation MUST target an Object, and MUST follow the rules specified in section 7.3 (ACCESS CONTROL) and its sub-sections. If any error occurs, nothing MUST be created.

The Object Instance created in the LwM2M Client by the LwM2M Server MUST be an Object type supported by the LwM2M Client and announced to the LwM2M Server using the “Register” and “Update” operations of the LwM2M Client Registration Interface.

Object Instance whose Object supports at most one Object Instance MUST be assigned an Object Instance ID of 0 when the Object Instance is Created.

The “Create” operation has the following parameters:

|               |              |                   |                                                                         |
|---------------|--------------|-------------------|-------------------------------------------------------------------------|
| **Parameter** | **Required** | **Default Value** | **Notes**                                                               |
| Object ID     | Yes          | -                 | Indicates the Object.                                                   |
| New Value     | Yes          | -                 | The new value included in the payload to create the Object Instance(s). |

<span id="_Toc492475268" class="anchor"></span>Table 15: Create parameters

The new value included in the payload MUST follow the TLV or JSON data format according to section 6.4.

The LwM2M Client MUST ignore optional resources it does not support in the payload. If the LwM2M Client supports optional resources not present in the payload, it MUST NOT instantiate these optional resources.

When there is no reference to Object Instance in the TLV/JSON payload of the “Create” command, the LwM2M Client MUST assigns the ID of the created Object Instance. If a new Object Instance is created through that operation and the LwM2M Client has more than one LwM2M Server Account, then the LwM2M Client creates an Access Control Object Instance for the created Object Instance (7.3 ACCESS CONTROL)

-   Access Control Owner MUST be the LwM2M Server

-   The LwM2M Server MUST have full access rights

    1.  ### Delete

The “Delete” operation is used for LwM2M Server to delete an Object Instance within the LwM2M Client.

The Object Instance that is deleted in the LwM2M Client by the LwM2M Server MUST be an Object Instance that is announced by the LwM2M Client to the LwM2M Server using the “Register” and “Update” operations of the Client Registration Interface.

The only exception concerns the single Instance of the mandatory Device Object (ID:3) which SHALL NOT be affected by any Delete operation.

The Delete operation has the following parameters:

|                    |              |                   |                                          |
|--------------------|--------------|-------------------|------------------------------------------|
| **Parameter**      | **Required** | **Default Value** | **Notes**                                |
| Object ID          | Yes          | -                 | Indicates the Object.                    |
| Object Instance ID | Yes          | -                 | Indicates the Object Instance to delete. |

<span id="_Toc492475269" class="anchor"></span>Table 16: Delete parameters

Information Reporting Interface
-------------------------------

The LwM2M Server and the LwM2M Client MUST support all the operations in this interface.

The Information Reporting Interface[3] is used by a LwM2M Server to observe any changes in a Resource on a registered LwM2M Client, receiving notifications when new values are available. This observation relationship is initiated by sending an “Observe” operation to the L2M2M Client for an Object, an Object Instance or a Resource. An observation ends when a “Cancel Observation” operation is performed.

The LwM2M Client MUST ignore LwM2M Servers operations on this interface during a Server Initiated Bootstrap.

The LwM2M Client MUST ignore the LwM2M Server operation on this interface until it received its Registration acknowledgement.

The LwM2M Server SHOULD NOT perform any operation on this interface before replying to the registration of this LwM2M Client.

<span id="_Toc492474254" class="anchor"></span>Figure 13: Example flow for Information Reporting Interface for the RSSI Resource of the Connectivity Monitoring Object of the example client (Appendix E)

### Observe

The LwM2M Server initiates an observation request for changes of a specific Resource, Resources within an Object Instance or for all the Object Instances of an Object within the LwM2M Client.

Related parameters for “Observe” operation are described in 5.4.4 Write-Attributes and those parameters are configured by “Write-Attributes” operation.

The Observe operation includes the following parameters:

|                    |              |                   |                                                                                                                                                                               |
|--------------------|--------------|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Parameter**      | **Required** | **Default Value** | **Notes**                                                                                                                                                                     |
| Object ID          | Yes          | -                 | Indicates the Object.                                                                                                                                                         |
| Object Instance ID | No           | -                 | Indicates the Object Instance to observe. If no Object Instance ID is indicated, then all the Object Instances of Objects are observed and Resource ID MUST NOT be specified. |
| Resource ID        | No           | -                 | Indicates the Resource to observe. If no Resource ID is indicated, then the whole Object Instance is observed.                                                                |

<span id="_Ref479773384" class="anchor"><span id="_Toc492475270" class="anchor"></span></span>Table 17: Observe parameters

<span id="_Ref368312744" class="anchor"><span id="_Ref368313126" class="anchor"><span id="_Toc370916066" class="anchor"><span id="_Toc370922888" class="anchor"></span></span></span></span>Until the LwM2M Client sends a new registration, the LwM2M Server expects the LwM2M Client to remember the observation requests. If a LwM2M Client forgets the observation requests (e.g., device factory reset) it MUST perform a new “Register” operation. The LwM2M Server MUST re-initiate observation requests whenever the LwM2M Client registers.

In order to avoid network traffic increase, the LwM2M Client SHOULD maintain previous observation states in case of reboot, power cycle.

It has to be noted that an “Observe” operation containing only Object ID, will produce the report of all Object Instances information.

Note: When a LwM2M Client deregisters, the LwM2M Server should assume past states are nullified including the previous observations.<span id="_Ref434227137" class="anchor"></span>

### Notify

The “Notify” operation is sent from the LwM2M Client to the LwM2M Server during a valid observation on an Object Instance or Resource. This operation includes the new value of the Object Instance or Resource. The “Notify” operation SHOULD be sent when all the conditions (i.e., Minimum Period, Maximum Period, Greater Than, Less Than, Step) configured by “Write-Attributes” operation for “Observe” operation are met.

|               |              |                   |                                                                              |
|---------------|--------------|-------------------|------------------------------------------------------------------------------|
| **Parameter** | **Required** | **Default Value** | **Notes**                                                                    |
| Updated Value | Yes          | -                 | The new value included in the payload about the Object Instance or Resource. |

<span id="Table17" class="anchor"><span id="_Ref368313535" class="anchor"><span id="_Toc492475271" class="anchor"></span></span></span>Table 18: Notify parameters

The following example shows how the Minimum and Maximum period parameters work as shown in Section 5.4.4. A LwM2M Server makes an observation for a Temperature Resource that is updated inside the LwM2M Client at irregular periods (based on change). The LwM2M Server makes an observation when the Minimum Period = 10 Seconds and Maximum Period = 60 Seconds have been set for that Resource. The LwM2M Client will wait at least 10 Seconds before sending a “Notify” operation to the LwM2M Server (even if the Resource has changed before that), and no longer than 60 Seconds before sending a “Notify” operation (even if the Resource has not changed yet). The “Notify” operation is sent anywhere between 10-60 seconds upon change.

Note: In case an “Observe” operation is initiated on a Resource, an Object Instance or an Object without any conditions previously configured, and with the “Default Minimum Period” in the LwM2M Server Object set to 0 (possibly by default), the “Notify” operation will be sent upon any change of, respectively, the observed Resource value, any Resource value of the observed Object Instance or any Resource value of any Instance of the observed Object. As specified in section 5.5.1 and in Table 17, in case of an “Observe” operation on a certain Object the “Notify” operation includes all Resources of all Instances of the observed Object.

<span id="_Toc492474255" class="anchor"></span>Figure 14: Example of Minimum and Maximum periods in an Observation

This example assumes the Minimum Period has been set to 10 and the Maximum Period set to 60 for the Resource /4/0/2 before making the observation.

### Cancel Observation

The “Cancel Observation” operation is sent from the LwM2M Server to the LwM2M Client to end an observation relationship for Object Instance or Resource.

Identifiers and Resources
=========================

This section defines the identifiers and resource model for the LwM2M Enabler.

Resource Model
--------------

The LwM2M Enabler defines a simple resource model where each piece of information made available by the LwM2M Client is a Resource. Resources are logically organized into Objects, and each Resource is given a unique identifier within that Object.

Figure 15 illustrates this structure, and the relationship between Resources, Objects, and the LwM2M Client. The LwM2M Client may have any number of Resources, each of which belongs to an Object; for example the Firmware Update Object contains all the Resources used for firmware update purposes.

<span id="_Toc492474256" class="anchor"></span>Figure 15: Relationship between LwM2M Client, Object, and Resources

Each Object, defined for the LwM2M Enabler, is assigned a unique OMA LwM2M Object identifier allocated and maintained by the OMA Naming Authority (OMNA). The LwM2M Enabler defines standard Objects and Resources (Appendix E). Further Objects may be added by OMA or other organizations to enable additional M2M Services.

As an Object only specifies a grouping of Resources, an Object MUST be firstly instantiated so that the LwM2M Client can use the Resources of such an Object and the associated functionalities.

When an Object is instantiated – either by the LwM2M Server or the LwM2M Client – an Object Instance is created with a subset of the Resources defined in the Object specification; a LwM2M Server can then access that Object Instance and its set of instantiated Resources.

A Resource which is instantiated within an Object Instance is a Resource which can either:

-   contain a value (if the Resource is Readable and/or Writeable)

-   or can be addressed by a LwM2M Server to trigger an action in the LwM2M Client (if the Resource is Executable)

The Object specification defines the operations (Read, Write, Execute) which are individually supported by the Resources belonging to that Object; this specification also defines the Mandatory or Optional characteristics of such Resources.

A Resource specified as Mandatory within an Object MUST be instantiated in any Instance of that Object.

A Resource specified as Optional within an Object MAY be omitted from some or even all Instances of that Object.

As illustration, the following example using the DISCOVER command on the Server Object, exposes a configuration in which the Server Object (ID:1) has 2 Instances (ID:0, ID:1): the Optional Resources ID:2, ID:4 are only instantiated in the Instance 1 of the Object, while the Optional Resources ID:3 and ID:5 are not instantiated in either of the Server Object Instances. In Server Object ID:1, the Resources 0,1, and 6,7,8 are Mandatory Resources.

According to the DISCOVER /1 request, the following payload is returned:

&lt;/1/0/0&gt;,&lt;/1/0/1&gt;,&lt;/1/0/6&gt;,&lt;/1/0/7&gt;, &lt;/1/0/8&gt;, &lt;/1/1/0&gt;,&lt;/1/1/1&gt;,&lt;/1/1/2&gt;,&lt;/1/1/4&gt;,&lt;/1/1/6&gt;,&lt;/1/1/7&gt;, &lt;/1/1/8&gt;

Objects and Resources have the capability to have multiple instances. Multiple-Instances Resources can be instantiated by LwM2M Server operations in using JSON or TLV formats (Section 5.4). The LwM2M Client also has the capability to instantiate Single or Multiple-Instances Resources.

The LwM2M Server performs operations on an Object, Object Instance and Resources as described in Section 5 Interfaces. These operations are conveyed as described in Section 8 Transport Layer Binding and Encoding and how to convey the Operation data is defined in 6.4.

The LwM2M Enabler defines an access control mechanism per Object Instance. Object Instances SHOULD have an associated Access Control Object Instance. An Access Control Object Instances contains Access Control Lists (ACLs) that define which operations on a given Object Instance are allowed for which LwM2M Server(s).

Figure 16 shows an example of the operations the Resources support and how Object Instances and Resources are associated with Access Control Object Instance. In the example, Object Instance 0 for Object 1 has 2 Resources. Resource 1 supports the ”Read”, “Write” operations, while Resource 0 supports only the “Read” operation. The associated Access Control Object Instance has ACL of Object Instance 0 for Object 1. Server1 is authorized to perform “Read” and “Write” operations to the Object Instance 0 for Object 1 and Resources of the Object Instance. However, due to the supported operations of each Resource, Server1 can perform the “Read” operation on Resource 1 and 0, and also can perform the “Write” operations on Resource 1, but Server1 cannot perform the “Write” operation on Resource 0. The detailed access control mechanism is defined in Section 147138816.7.3 Access Control.

<span id="_Toc492474257" class="anchor"></span>Figure 16: Example of Supported operations and Associated Access Control Object Instance

1.  Object Versioning
    -----------------

    1.  ### General Policy

A LwM2M Object specification is tightly coupled with the LwM2M Enabler which is supporting it. However, a LwM2M Object that is not directly specified in the LwM2M Enabler but in a “companion specification”, MAY evolve (e.g., to fix one Object Resource characteristic issue).

For example:

-   a Resource may be added or removed in the Object

-   a Resource characteristic (mandatory nature, data type, operation mode …) may be changed in the Object

A LwM2M Server MUST be able to determine without ambiguity the specification of the Objects intended to be registered by the LwM2M Client:

-   it is the case for the LwM2M Objects which are specified within the LwM2M

-   for LwM2M Objects specified outside of a LwM2M Enabler, the Server has to be informed if the initial set of Resources characteristics have been modified/fixed, so that the Server can refer to the proper Object Specification

Object versioning aims at identifying the LwM2M Object modifications which can be categorized in 2 types defined below:

-   Evolution of type I: representing non-backward-compatible (“breaking”) evolutions, namely:

    -   A Resource characteristic (optional vs mandatory, data type, supported operations) is changed in the Object

    -   a Resource supporting a feature which is only defined by a new LwM2M Enabler, is added to the Object

-   Evolution of type II: representing backward-compatible (“non-breaking”) evolutions

    -   an optional Resource is added or removed in the Object

In this document, the term “Initial Version” represents:

-   the version 1.0 of the LwM2M Enabler

<!-- -->

-   the version 1.0 of any Object registered for the first time in OMNA

With Object versioning, the Object Identifier is not changed but a new URN identifying that particular version of the Object specification MUST be registered according to the following format

> “urn:oma:lwm2m:{oma, ext, x}:ObjectID\[:{version}\]” where ‘version’ is the Object Version as defined in the following section

### Object Version format

The Object Version of an Object is composed of 2 digits separated by a dot ‘.’:

-   the first digit represents the Major Version of the Object: this digit marks the non-backward compatible evolution of such an Object (Object evolution of type I: section 6.2.1)

-   the second digit represents the Minor Version of the Object: this digit marks the backward compatible evolution of such an Object (Object evolution of type II: see section 6.2.1)

By convention when an Object is in its Initial Version, the Object Version MAY be omitted in the URN.

To be more precise, two separate URNs are accepted as valid for the corresponding version of the object specification:

-   the URN where the Object Version is mentioned explicitly: “urn:oma:lwm2m:{oma, ext, x}:ObjectID:1.0“

-   the URN where the Object Version is absent: “urn:oma:lwm2m:{oma, ext, x}:ObjectID“ (and supposed to be 1.0)).

Example: “urn:oma:lwm2m:oma:44:2.2”

This URN uniquely identifies Object ID:44 in its version “2.2”. Registered Objects are available on the OMNA portal (see Section 6.2.3 and the Appendix J on Object Definition File for further information).

### Object Definition and Object Version Usage

The rules governing in which circumstances the Object Version is provided by the LwM2M Client to the LwM2M Server during the “Register” and “Discover” operations, are synthesized in the following table:

|                      | Object in Initial Version (1.0) | Object Version &gt; 1.0    |
|----------------------|---------------------------------|----------------------------|
| Objects defined      
                       
 within                
                       
 LwM2M TS Enabler      | The LwM2M Client                
                                   
  MAY                              
                                   
  provide the Object Version       | The LwM2M Client           
                               
   MAY                         
                               
   provide the Object Version  |
| Objects defined      
                       
 Outside               
                       
 any LwM2M TS Enabler  | The LwM2M Client                
                                   
  MAY                              
                                   
  provide the Object Version       | The LwM2M Client           
                               
   MUST                        
                               
   provide the Object Version  |

<span id="_Ref467142198" class="anchor"><span id="_Toc492475272" class="anchor"><span id="_Ref455995873" class="anchor"></span></span></span>Table 19: Object Version usage rules

In “Register” and “Discover” operations, when the Object Version of a given Object must be communicated, the LwM2M Client MUST use the “ver” (object version) &lt;PROPERTIES&gt; Class attribute associated to that Object.

Few examples:

1.  URN: “urn:oma:lwm2m:oma:44:2.2” Object 44 in version 2.2

> Details:

-   on the OMNA portal the Object ID:44 will be registered at least twice

<!-- -->

-   with the URN “urn:oma:lwm2m:oma:44” (Initial Version)

-   with the URN “urn:oma:lwm2m:oma:44:2.2” (or the latest release of the major Version 2, LwM2M Server ignores minor releases)

<!-- -->

-   the Object definition contains the minimal version of the LwM2M Enabler supporting that Object (which can be omitted if this LwM2M version is the “Initial Version” one)

-   LwM2M Client “Register” operation: ep=nodename,&lt;/1/0&gt;,&lt;/1/1&gt;,&lt;/3/0&gt;,&lt;/44&gt;;ver= “2.2”,&lt;/44/0&gt;

1.  URN: “urn:oma:lwm2m:oma:3”

> Details: LwM2M Client “Register” operation: ep=nodename,&lt;/1/0&gt;,&lt;/1/1&gt;,&lt;/3/0&gt;

1.  URN: “urn:oma:lwm2m:oma:44”

> Details: LwM2M Client “Register” operation: ep=nodename,&lt;/1/0&gt;,&lt;/1/1&gt;,&lt;/3/0&gt;,&lt;/44/0&gt;

1.  URN: “urn:oma:lwm2m:oma:3” in LwM2M Client supporting LwM2M Enabler version 2.0

> Details:

-   the minimal version of the LwM2M Enabler supporting that Object “3” (Device) is still LwM2M 1.0; this information may be omitted in the Device (ID:3) Object Definition file

-   LwM2M Client “Register” operation: lwm2m=“2.0”,ep=nodename,&lt;/1/0&gt;,&lt;/1/1&gt;,&lt;/3/0&gt;

1.  URN: “urn:oma:lwm2m:oma:4:3.1”

> Context:

-   the LwM2M Client supports LwM2M Enabler version 2.0

-   Object ID: 4 supports a specific feature of LwM2M 2.0 not supported by the LwM2M Enabler Initial Version, and the Object Version 3 is part of the LwM2M Enabler Version 2.0

> Details:

-   the minimal version of the LwM2M Enabler supporting that Object “4” (Device) must be indicated in the Object 4 version 3.1 Definition file: LwM2MVersion=“2.0” and ObjectVersion=“3.1”

-   LwM2M Client “Register” operation: lwm2m=“2.0”,ep=nodename,&lt;/1/0&gt;,&lt;/1/1&gt;,&lt;/3/0&gt;,&lt;/4/0&gt;

    1.  Identifiers
        -----------

The LwM2M Enabler defines specific identifiers for entities used within the LwM2M Protocol. These identifiers are defined in Table 20.

<table>
<tbody>
<tr class="odd">
<td><strong>Identifier</strong></td>
<td><strong>Semantics</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td>Endpoint Client Name</td>
<td>URN</td>
<td><p>Identifies the LwM2M Client on one LwM2M Server (including LwM2M Bootstrap-Server).</p>
<p>Provided to the LwM2M Server during Registration, also provided to LwM2M Bootstrap-Server when executing the Bootstrap procedure.</p>
<p>Recommended URN formats are documented in Section 6.3.1 Endpoint Client Name.</p></td>
</tr>
<tr class="odd">
<td>LwM2M Bootstrap-Server URI</td>
<td>URI</td>
<td>Uniquely identifies the LwM2M Bootstrap-Server. Provided to the LwM2M Client during the Bootstrap procedure.</td>
</tr>
<tr class="even">
<td>LwM2M Server URI</td>
<td>URI</td>
<td>Uniquely identifies the LwM2M Server. Provided to the Client during Bootstrap procedure.</td>
</tr>
<tr class="odd">
<td>Short Server ID</td>
<td>16-bit unsigned integer</td>
<td><p>Uniquely identifies each LwM2M Server configured for the LwM2M Client. The identifier is assigned during the Bootstrap procedure.</p>
<p>Default Short Server ID is 0 and default Short Server ID MUST NOT be used for identifying the LwM2M Server.</p>
<p>MAX_ID 65535 is a reserved value and MUST NOT be used for identifying the LwM2M Server.</p></td>
</tr>
<tr class="even">
<td>Human Readable Object URN</td>
<td>URN for the OMA Management Object</td>
<td>Assigned by the Object specification.</td>
</tr>
<tr class="odd">
<td>Object ID</td>
<td>16-bit unsigned integer</td>
<td>Uniquely identifies the Object in the LwM2M Client. This identifier is assigned by OMA.</td>
</tr>
<tr class="even">
<td>Object Instance ID</td>
<td>16-bit unsigned integer</td>
<td>Uniquely identifies the Object Instance of the Object within the LwM2M Client. This identifier is assigned by LwM2M Client or LwM2M Server.<br />
MAX_ID 65535 is a reserved value and MUST NOT be used for identifying the Object Instance.</td>
</tr>
<tr class="odd">
<td>Resource ID</td>
<td>16-bit unsigned integer</td>
<td>Uniquely identifies the Resource within the Object. Short integer ID, with a range assigned by the Object specification and unique to that Object, and a Reusable Resource ID range assigned by OMA and re-usable between Objects.</td>
</tr>
<tr class="even">
<td>Resource Instance ID</td>
<td>16-bit unsigned integer</td>
<td>Uniquely identifies the Resource Instance in the Resource. This identifier is assigned by LwM2M Client or LwM2M Server.</td>
</tr>
</tbody>
</table>

<span id="_Ref467142318" class="anchor"><span id="_Toc492475273" class="anchor"><span id="_Ref371020092" class="anchor"><span id="_Ref404851771" class="anchor"></span></span></span></span>Table 20: LwM2M Identifiers

### Endpoint Client Name

Following formats are RECOMMENDED for this identifier to guarantee uniqueness:

<table>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Format</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UUID URN: Identify a device using a Universally Unique IDentifier (UUID). The UUID specifies a valid, hex digit character string as defined in [RFC4122]. The format of the URN is<br />
urn:uuid:########-####-####-############</p>
<p>OPS URN: Identify a device using the format &lt;OUI&gt; &quot;-&quot; &lt;ProductClass&gt; &quot;-&quot; &lt;SerialNumber&gt; as defined in Section 3.4.4 of [TR-069]. The format of the URN is urn:dev:ops:&lt;OUI&gt; &quot;-&quot; &lt;ProductClass&gt; &quot;-&quot; &lt;SerialNumber&gt;.</p>
<p>OS URN: Identify a device using the format &lt;OUI&gt; &quot;-&quot;&lt;SerialNumber&gt; as defined in Section 3.4.4 of [TR-069]. The format of the URN is urn:dev:os:&lt;OUI&gt; &quot;-&quot;&lt;SerialNumber&gt;.</p>
<p>IMEI URN: Identify a device using an International Mobile Equipment Identifiers [3GPP-TS_23.003]. The IMEI URN specifies a valid, 15 digit IMEI. The format of the URN is urn:imei:###############</p>
<p>ESN URN: Identify a device using an Electronic Serial Number. The ESN specifies a valid, 8 digit ESN. The format of the URN is urn:esn:########</p>
<p>MEID URN: Identify a device using a Mobile Equipment Identifier. The MEID URN specifies a valid, 14 digit MEID. The format of the URN is urn:meid:##############</p>
<p>IMEI-MSISDN URN: Identify a device using a combination of International Mobile Equipment Identifier [3GPP-TS_23.003] and MSISDN. IMEI is 15 digits and MSISDN is 15 digits. The format of the URN is urn:imei-msisdn: ###############-###############</p></td>
</tr>
</tbody>
</table>

Other URN formats MAY be used. In particular, URN formats defined in \[DMREPPRO\] Section 5.5 can be used.

### Reusable Resources

When Objects are designed for a similar purpose, for example Objects for use in network management, or Objects for use in embedded device automation, similar Resources are useful in more than one Object. For example in embedded device automation, Objects for different purposes may contain common Resource types such as digital input, digital output, analogue input, analogue output, dimmer value, unit, min measurement, max measurement, value range etc.

If a Resource can feasibly be re-used with the same meaning in multiple Object definitions, it can be defined as a Reusable Resource ID and registered with OMNA. Other Objects may then make use of this Reusable Resource ID in another Object definition.

The definition of a Reusable Resource and its usage when hosted in an Object specification MUST follow several rules:

-   the Name, ID, Operation, Type, Range and Units are frozen characteristics when the Reusable Resource is registered at OMNA and cannot not be changed when such a Resource is specified in the definition of a hosting Object.

-   the registered Description field of a Reusable Resource is also a frozen characteristic; when extension is required to fit the real need of the Object hosting such a Resource, that extension must be mentioned in the Object specification but outside of the Description field itself; furthermore any extension MUST be compatible with the content of the registered Description field.

-   a Reusable Resource is registered without defining “Multiple-Resource”, or “Mandatory” characteristics; both characteristics will be determined when such a Resource is specified in the definition of a hosting Object.

Note: If the operators/vendors want to extend the resources in a non-standard way, it is advisable to refer OMNA and use the private resource range. This action of using private range, would ensure backward compatibility in case the resource(s) is getting extended in future releases of LwM2M TS, by OMA DM WG.

Data Formats for Transferring Resource Information
--------------------------------------------------

Four data formats are defined by the LwM2M Enabler in this section: plain text, opaque, TLV and JSON.

The LwM2M Server MUST support all data formats. The LwM2M Client MUST support the TLV data format. In addition a LwM2M Client MAY choose to support other data formats in the table below i.e., JSON, plain text and opaque.

<span id="_Ref368312768" class="anchor"><span id="_Ref368313143" class="anchor"><span id="_Toc370916074" class="anchor"><span id="_Toc370922896" class="anchor"></span></span></span></span>Messages containing data MUST specify the payload encoding by using one of the supported data format.

A LwM2M Server data request MAY contain an option specifying the data formats the Server would prefer to receive for the payload; if this data format is not accepted by the LwM2M Client, the request is rejected; if the LwM2M Client doesn’t support that option or if the LwM2M Server expresses no data format preference, the LwM2M Client will use its own preferred data format.

The IANA registered Media Type supported in LwM2M TS 1.0 are listed in the table below

| **Data Format** | **IANA Media Type**            | **Numeric Content-Formats \[CoAP\]** |
|-----------------|--------------------------------|--------------------------------------|
| Plain Text      | text/plain                     | 0                                    |
| Core Link Param | application/link-format        | 40                                   |
| Opaque          | application/octet-stream       | 42                                   |
| TLV             | application/vnd.oma.lwm2m+tlv  | 11542                                |
| JSON            | application/vnd.oma.lwm2m+json | 11543                                |

### Plain Text

The plain text format is used for “Read” and “Write” operations on singular Resources where the value of the Resource is represented as described in Appendix C.

For example a request to the example client’s Device Object Instance, Manufacturer Resource would return the following plain text payload:

Req: GET /3/0/0

Res: 2.05 Content

Open Mobile Alliance

This data format has a Media Type of text/plain

### Opaque

The opaque format is used for “Read” and “Write” operations on singular Resources where the value of the Resource is an opaque sequence of binary octets. This data format is used for binary Resources such as firmware images or application specific binary formats.

This data format has a Media Type of application/octet-stream<span id="_Ref368312790" class="anchor"><span id="_Ref368313159" class="anchor"><span id="_Ref368314167" class="anchor"><span id="_Toc370916076" class="anchor"><span id="_Toc370922898" class="anchor"></span></span></span></span></span>.

### TLV

For “Read” and “Write” operations, the binary TLV (Type-Length-Value) format is used to represent an array of values or a singular value using a compact binary representation, which is easy to process on simple embedded devices. The format has a minimum overhead per value of just 2 bytes and a maximum overhead of 5 bytes depending on the type of Identifier and length of the value. The maximum size of an Object Instance or Resource in this format is 16.7 MB. The format is self-describing, thus a parser can skip TLVs for which the Resource is not known.

This data format has a Media Type of application/vnd.oma.lwm2m+tlv.

The format is an array of the following byte sequence, where each array entry represents an Object Instance, Resource, or Resource Instance:

|            |                                                                  |                                                                                                                                |
|------------|------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| **Field ** | **Format and Length**                                            | **Description**                                                                                                                |
| Type       | 8-bits masked field:                                             
                                                                    
  0bxxxxxxxx (MSB is the bit following 0b)                          
                                                                    
  Bit numbering is 0 for the LSB to 7 for the MSB                   | Bits 7-6: Indicates the type of Identifier.                                                                                    
                                                                                                                                   
   00= Object Instance in which case the Value contains one or more Resource TLVs                                                  
                                                                                                                                   
   01= Resource Instance with Value for use within a multiple Resource TLV                                                         
                                                                                                                                   
   10= multiple Resource, in which case the Value contains one or more Resource Instance TLVs                                      
                                                                                                                                   
   11= Resource with Value                                                                                                         |
|            |                                                                  | Bit 5: Indicates the Length of the Identifier.                                                                                 
                                                                                                                                   
   0=The Identifier field of this TLV is 8 bits long                                                                               
                                                                                                                                   
   1=The Identifier field of this TLV is 16 bits long                                                                              |
|            |                                                                  | Bit 4-3: Indicates the type of Length.                                                                                         
                                                                                                                                   
   00=No length field, the value immediately follows the Identifier field in is of the length indicated by Bits 2-0 of this field  
                                                                                                                                   
   01 = The Length field is 8-bits and Bits 2-0 MUST be ignored                                                                    
                                                                                                                                   
   10 = The Length field is 16-bits and Bits 2-0 MUST be ignored                                                                   
                                                                                                                                   
   11 = The Length field is 24-bits and Bits 2-0 MUST be ignored                                                                   |
|            |                                                                  | Bits 2-0: A 3-bit unsigned integer indicating the Length of the Value.                                                         |
| Identifier | 8-bit or 16-bit unsigned integer as indicated by the Type field. | The Object Instance, Resource, or Resource Instance ID as indicated by the Type field.                                         |
| Length     | 0-24-bit unsigned integer as indicated by the Type field.        | The Length of the following field in bytes.                                                                                    |
| Value      | Sequence of bytes of Length                                      | Value of the tag. The format of the value depends on the Resource’s data type (See Appendix C).                                |

<span id="_Ref472009246" class="anchor"><span id="_Toc492475274" class="anchor"><span id="_Ref368310482" class="anchor"></span></span></span>Table 21: TLV format and description

Each TLV entry starts with a Type byte that indicates if the TLV contains an Object Instance, a Resource, multiple Resources, or a Resource Instance. Object Instance and Resource with Resource Instance TLVs contains other TLVs in their value. The hierarchy is as follows and may be up to 3 levels deep.

-   Object Instance TLV, which contains

    -   Resource TLVs or

    -   multiple Resource TLVs, which contains

        -   Resource Instance TLVs

For simplicity and to prevent any ambiguity on Object Instance Identity, when the Object Instance ID is not specified in the request, the Object Instance TLV MUST be used, whatever the number of Object Instances (1 or more) to return to the LwM2M Server.

When a Multiple Resource has to be returned to the LwM2M Server, the Multiple Resource TLV MUST be used whatever the number of Instances (0, 1 or more) of that resource.

The following figure illustrates the possible nesting of Object Instance, Resource, multiple Resources, and Resource Instance TLVs. One or several Resource TLVs, and/or one or several multiple Resource TLVs MAY be nested in an Object Instance TLV. A multiple Resource TLV contains one or several Resource Instance TLVs.

<span id="_Toc492474258" class="anchor"></span>Figure 17: TLV nesting

#### Single Object Instance Request Example

In this example, a request for the Device Object Instance (ID:3) of a LwM2M client is made (Read /3/0). The client responds with a TLV payload including all of the readable Resources. This TLV payload would have the following format. The total payload size with the TLV encoding is 121 bytes:

C8 00 14 4F 70 65 6E 20 4D 6F 62 69 6C 65 20 41 6C 6C 69 61 6E 63 65

C8 01 16 4C 69 67 68 74 77 65 69 67 74 20 4D 32 4D 20 43 6C 69 65 6E 74

C8 02 09 33 34 35 30 30 30 31 32 33

C3 03 31 2E 30

86 06

41 00 01

41 01 05

88 07 08

42 00 0E D8

42 01 13 88

87 08

41 00 7D

42 01 03 84

C1 09 64

C1 0A 0F

83 0B

41 00 00

C4 0D 51 82 42 8F

C6 0E 2B 30 32 3A 30 30

C1 10 55

|                              |               |                |                    |                                     |                 |
|------------------------------|---------------|----------------|--------------------|-------------------------------------|-----------------|
| **TLV**                      | **Type Byte** | **ID Byte(s)** | **Length Byte(s)** | **Value**                           | **Total Bytes** |
| Manufacturer Resource        | 0b11 0 01 000 | 0x00           | 0x14 (20 bytes)    | Open Mobile Alliance \[String\]     | 23              |
| Model Number                 | 0b11 0 01 000 | 0x01           | 0x16 (22 bytes)    | “Lightweight M2M Client” \[String\] | 25              |
| Serial Number                | 0b11 0 01 000 | 0x02           | 0x09 (9 bytes)     | “345000123” \[String\]              | 12              |
| Firmware Version             | 0b11 0 00 011 | 0x03           | ─                  | “1.0” \[String\] (3 bytes)          | 5               |
| Available Power Sources      | 0b10 0 00 110 | 0x06           | ─                  | The next two rows (6 bytes)         | 2               |
| Available Power Sources\[0\] | 0b01 0 00 001 | 0x00           | ─                  | 0X01 \[8-bit Integer\]              | 3               |
| Available Power Sources\[1\] | 0b01 0 00 001 | 0x01           | ─                  | 0X05 \[8-bit Integer\]              | 3               |
| Power Source Voltage         | 0b10 0 01 000 | 0x07           | 0x08 (8 bytes)     | The next two rows                   | 3               |
| Power Source Voltage\[0\]    | 0b01 0 00 010 | 0x00           | ─                  | 0X0ED8 \[16-bit Integer\]           | 4               |
| Power Source Voltage\[1\]    | 0b01 0 00 010 | 0x01           | ─                  | 0X1388 \[16-bit Integer\]           | 4               |
| Power Source Current         | 0b10 0 00 111 | 0x08           | ─                  | The next two rows (7 bytes)         | 2               |
| Power Source Current\[0\]    | 0b01 0 00 001 | 0x00           | ─                  | 0X7D \[8-bit Integer\]              | 3               |
| Power Source Current\[1\]    | 0b01 0 00 010 | 0x01           | ─                  | 0X0384 \[16-bit Integer\]           | 4               |
| Battery Level                | 0b11 0 00 001 | 0x09           | ─                  | 0x64 \[8-bit Integer\]              | 3               |
| Memory Free                  | 0b11 0 00 001 | 0x0A           | ─                  | 0x0F \[8-bit Integer\]              | 3               |
| Error Code                   | 0b10 0 00 011 | 0x0B           | ─                  | The next row (3 bytes)              | 2               |
| Error Code\[0\]              | 0b01 0 00 001 | 0x00           | ─                  | 0x00 \[8-bit Integer\]              | 3               |
| Current Time                 | 0b11 0 00 100 | 0x0D           | ─                  | 0x5182428F \[32-bit Integer\]       | 6               |
| UTC Offset                   | 0b11 0 00 110 | 0x0E           | ─                  | “+02:00” \[String\] (6 bytes)       | 8               |
| Supported Binding and Modes  | 0b11 0 00 001 | 0x10           | ─                  | “U” \[String\] (1 byte)             | 3               |
| **Total**                    | 121           |

#### Multiple Object Instance Request Examples

1.  Request on Single-Instance Object

In this example, a request for the Device Object Instance (ID:3) of a LwM2M client is made (Read /3). The Device Object is a Single-Instance Object, but the Object Instance TLV is used (to be compared with the example of the previous section).

The client responds with a TLV payload including the Object Instance ID and all its readable Resources. This TLV payload would have the following value (indented for readability) and format. The total payload size with the TLV encoding is 124 bytes:

08 00 79

C8 00 14 4F 70 65 6E 20 4D 6F 62 69 6C 65 20 41 6C 6C 69 61 6E 63 65

C8 01 16 4C 69 67 68 74 77 65 69 67 74 20 4D 32 4D 20 43 6C 69 65 6E 74

C8 02 09 33 34 35 30 30 30 31 32 33

C3 03 31 2E 30

86 06

41 00 01

41 01 05

88 07 08

42 00 0E D8

42 01 13 88

87 08

41 00 7D

42 01 03 84

C1 09 64

C1 0A 0F

83 0B

41 00 00

C4 0D 51 82 42 8F

C6 0E 2B 30 32 3A 30 30

C1 10 55

|                              |                   |                |                      |                                     |                 |
|------------------------------|-------------------|----------------|----------------------|-------------------------------------|-----------------|
| **TLV**                      | **Type Byte**     | **ID Byte(s)** | **Length Byte(s)**   | **Value**                           | **Total Bytes** |
| **Device Object Instance 0** | **0b00 0 01 000** | **0x00**       | **0x79 (121 bytes)** | **The next 20 rows**                | **3**           |
| Manufacturer Resource        | 0b11 0 01 000     | 0x00           | 0x14 (20 bytes)      | Open Mobile Alliance \[String\]     | 23              |
| Model Number                 | 0b11 0 01 000     | 0x01           | 0x16 (22 bytes)      | “Lightweight M2M Client” \[String\] | 25              |
| Serial Number                | 0b11 0 01 000     | 0x02           | 0x09 (9 bytes)       | “345000123” \[String\]              | 12              |
| Firmware Version             | 0b11 0 00 011     | 0x03           | ─                    | “1.0” \[String\] (3 bytes)          | 5               |
| Available Power Sources      | 0b10 0 00 110     | 0x06           | ─                    | The next two rows (6 bytes)         | 2               |
| Available Power Sources\[0\] | 0b01 0 00 001     | 0x00           | ─                    | 0X01 \[8-bit Integer\]              | 3               |
| Available Power Sources\[1\] | 0b01 0 00 001     | 0x01           | ─                    | 0X05 \[8-bit Integer\]              | 3               |
| Power Source Voltage         | 0b10 0 01 000     | 0x07           | 0x08 (8 bytes)       | The next two rows                   | 3               |
| Power Source Voltage\[0\]    | 0b01 0 00 010     | 0x00           | ─                    | 0X0ED8 \[16-bit Integer\]           | 4               |
| Power Source Voltage\[1\]    | 0b01 0 00 010     | 0x01           | ─                    | 0X1388 \[16-bit Integer\]           | 4               |
| Power Source Current         | 0b10 0 00 111     | 0x08           | ─                    | The next two rows (7 bytes)         | 2               |
| Power Source Current\[0\]    | 0b01 0 00 001     | 0x00           | ─                    | 0X7D \[8-bit Integer\]              | 3               |
| Power Source Current\[1\]    | 0b01 0 00 010     | 0x01           | ─                    | 0X0384 \[16-bit Integer\]           | 4               |
| Battery Level                | 0b11 0 00 001     | 0x09           | ─                    | 0x64 \[8-bit Integer\]              | 3               |
| Memory Free                  | 0b11 0 00 001     | 0x0A           | ─                    | 0x0F \[8-bit Integer\]              | 3               |
| Error Code                   | 0b10 0 00 011     | 0x0B           | ─                    | The next row (3 bytes)              | 2               |
| Error Code\[0\]              | 0b01 0 00 001     | 0x00           | ─                    | 0x00 \[8-bit Integer\]              | 3               |
| Current Time                 | 0b11 0 00 100     | 0x0D           | ─                    | 0x5182428F \[32-bit Integer\]       | 6               |
| UTC Offset                   | 0b11 0 00 110     | 0x0E           | ─                    | “+02:00” \[String\] (6 bytes)       | 8               |
| Supported Binding and Modes  | 0b11 0 00 001     | 0x10           | ─                    | “U” \[String\] (1 byte)             | 3               |
| **Total**                    | 124               |

1.  Request on Multiple-Instances Object having 2 instances

In this example, a request on the Access Control Object (ID:2) of a LwM2M client is made (Read /2). The Access Control Object is a Multiple-Instances Object. In this simplified example, it has only 2 instances describing the access rights of two LwM2M Servers with Short IDs 127 and 310 on Objects Instances /1/0 and /3/0.

The client responds with a TLV payload including the 2 Object Instances (ID:0 and ID:2) and their Resources. This TLV payload would have the following value (indented for readability) and format. The total payload size with the TLV encoding is 38 bytes:

08 00 0E

C1 00 01

C1 01 00

83 02

41 7F 07

C1 03 7F

08 02 12

C1 00 03

C1 01 00

86 02 41 7F 07 61 01 36 01

C1 03 7F

|                                      |                   |                |                     |                                 |                 |
|--------------------------------------|-------------------|----------------|---------------------|---------------------------------|-----------------|
| **TLV**                              | **Type Byte**     | **ID Byte(s)** | **Length Byte(s)**  | **Value**                       | **Total Bytes** |
| **Access Control Object Instance 0** | **0b00 0 01 000** | **0x00**       | **0x0E (17 bytes)** | **The next 5 rows**             | **3**           |
| Object ID                            | 0b11 0 00 001     | 0x00           | ─                   | 0x01 \[8-bit Integer\]          | 3               |
| Object Instance ID                   | 0b11 0 00 001     | 0x01           | ─                   | 0x00 \[8-bit Integer\]          | 3               |
| ACL                                  | 0b10 0 00 011     | 0x02           | ─                   | The next row (3 bytes)          | 2               |
| *ACL \[127\]*                        | *0b01 0 00 001*   | *0x7F*         | ─                   | *0b000 00111* \[8-bit Integer\] | 3               |
| Access Control Owner                 | 0b11 0 00 001     | 0x03           | ─                   | 0x7F \[8-bit Integer\]          | 3               |
| **Access Control Object Instance 2** | **0b00 0 01 000** | **0x02**       | **0x12 (18 bytes)** | **The next 6 rows**             | **3**           |
| Object ID                            | 0b11 0 00 001     | 0x00           | ─                   | 0x03 \[8-bit Integer\]          | 3               |
| Object Instance ID                   | 0b11 0 00 001     | 0x01           | ─                   | 0x00 \[8-bit Integer\]          | 3               |
| ACL                                  | 0b10 0 00 110     | 0x02           | ─                   | The next 2 rows                 | 2               |
| *ACL \[127\]*                        | *0b01 0 00 001*   | *0x7F*         | ─                   | *0b000 00111* \[8-bit Integer\] | 3               |
| *ACL \[310\]*                        | *0b01 1 00 001*   | *0x0136*       | ─                   | *0b000 00001* \[8-bit Integer\] | 4               |
| Access Control Owner                 | 0b11 0 00 001     | 0x03           | ─                   | 0x7F \[8-bit Integer\]          | 3               |
| **Total**                            | 38                |

1.  <span id="_Ref368312801" class="anchor"><span id="_Ref368313172" class="anchor"><span id="_Toc370916077" class="anchor"><span id="_Toc370922899" class="anchor"></span></span></span></span>Request on Multiple-Instances Object having 1 instance only

In this example, a request to the Server Object Instances of a LwM2M client is performed (Read /1). The Server Object is a Multiple-Instances Object. The client has only one Server Object instance and will respond with a TLV payload including the single Object Instance (0) and their Resources. This TLV payload would have the following value (indented for readability) and format. The total payload size with the TLV encoding is 18 bytes:

08 00 0D

C1 00 01

C4 01 00 01 51 80

C1 06 01

C1 07 55

|                                               |                   |                |                    |                          |                 |
|-----------------------------------------------|-------------------|----------------|--------------------|--------------------------|-----------------|
| **TLV**                                       | **Type Byte**     | **ID Byte(s)** | **Length Byte(s)** | **Value**                | **Total Bytes** |
| **Server Object Instance 0**                  | **0b00 0 01 000** | **0x00**       | **0x0D**           
                        
    **(13 Bytes)**      | **The next 5 rows**      | **3**           |
| Short Server ID                               | 0b11 0 00 001     | 0x00           | ─                  | 0x01 \[8-bit Integer\]   | 2               |
| Lifetime                                      | 0b11 0 00 100     | 0x01           | ─                  | 86400 \[32-bit Integer\] | 5               |
| Notification Storing When Disabled or Offline | 0b11 0 00 001     | 0x06           | ─                  | True \[Boolean\]         | 3               |
| Binding                                       | 0b11 0 00 001     | 0x07           | ─                  | “U” \[String\] (1 byte)  | 3               |
| **Total**                                     | 16                |

#### Example of Request on an Object Instance containing an Object Link Resource

Examples are based on the LwM2M Object Tree illustration of Figure 28. The TLV format doesn’t report Object hierarchy.

Example 1) request to Object 65 Instance 0: Read /65/0

88 00 0C

44 00 00 42 00 00

44 01 00 42 00 01

C8 01 0D 38 36 31 33 38 30 30 37 35 35 35 30 30

C4 02 12 34 56 78

|                 |               |                |                    |                                       |                 |
|-----------------|---------------|----------------|--------------------|---------------------------------------|-----------------|
| **TLV**         | **Type Byte** | **ID Byte(s)** | **Length Byte(s)** | **Value**                             | **Total Bytes** |
| Res 0 lnk       | 0b1 0 0 01000 | 0x00           | 0x0C(12 bytes)     | The next 2 rows                       | 3               |
| Res 0 lnk \[0\] | 0b01 000 100  | 0x00           | ─                  | 0x0042 0000 \[Objlnk\] (66:0)         | 6               |
| Res 0 lnk \[1\] | 0b01 0 00 100 | 0x01           | ─                  | 0x0042 0001 \[Objlnk\] (66:1)         | 6               |
| Res 1           | 0b11 0 01 000 | 0x01           | 0x0D               | “8613800755500” \[String\] (13 bytes) | 16              |
| Res 2           | 0b11 0 00 100 | 0x02           | ─                  | 0x12345678 \[32-bit Integer\]         | 6               |
| **Total**       | 37            |

Example 2) request to Object 66: Read /66: TLV payload will contain 2 Object Instances

08 00 23

C8 00 0B 6D 79 53 65 72 76 69 63 65 20 31

C8 01 0F 49 6E 74 65 72 6E 65 74 2E 31 35 2E 32 33 34

C4 02 00 43 00 00

08 01 23

C8 00 0B 6D 79 53 65 72 76 69 63 65 20 32

C8 01 0F 49 6E 74 65 72 6E 65 74 2E 31 35 2E 32 33 35

C4 02 FF FF FF FF

|                          |                   |                |                     |                                         |                 |
|--------------------------|-------------------|----------------|---------------------|-----------------------------------------|-----------------|
| **TLV**                  | **Type Byte**     | **ID Byte(s)** | **Length Byte(s)**  | **Value**                               | **Total Bytes** |
| **Object 66 Instance 0** | **0b00 0 01 000** | **0x00**       | **0x23 (35 bytes)** | **The next 3 rows**                     | 3               |
| Res 0                    | **0b11 0 01 000** | 0x00           | 0x0B                | “myService 1” \[String\] (11 bytes)     | 14              |
| Res 1                    | **0b11 0 01 000** | 0x01           | 0x0F                | “Internet.15.234” \[String\] (15 bytes) | 15              |
| Res 2 lnk                | 0b11 0 00 100     | *0x02*         | ─                   | 0x0043 0000 \[Objlnk\] (67:0)           | 6               |
| **Object 66 Instance 1** | **0b00 0 01000**  | **0x01**       | **0x23 (35 bytes)** | **The next 3 rows**                     | **3**           |
| Res 0                    | 0b11 0 01 000     | 0x00           | 0x0B                | “myService 2” \[String\] (11 bytes)     | 14              |
| Res 1                    | 0b11 0 00 000     | 0x01           | 0x0F                | “Internet.15.235” \[String\] (15 bytes) | 15              |
| Res 2 lnk                | 0b11 0 00 100     | 0x02           | ─                   | 0xFFFF FFFF \[Objlnk\] (no link)        | 6               |
| **Total**                | 76                |

### JSON

When a LwM2M Client is supporting the JSON data format and such a format is used to transport Object Instance(s), multiple resource and single resource values for both “Read” and “Write” operations, JSON payload MUST use the format defined in this section. Such a format MAY be used for transporting a single value of a Resource

The format MUST comply to \[SENML\] JSON representation extended for supporting LwM2M Object Link data type and MUST support all attributes defined in Table 22.

According to \[SENML\] semantics, JSON data format in LwM2M, is composed of optional attributes (Base Time, Base Name) and of a mandatory Resource Array having one or more entries. Each array entry contains several optional or mandatory parameters (Name, Time...).

Each entry of the JSON format is a Resource Instance, where the Name attribute need to be prepended by the Base Name attribute to form the unique identifier of this Resource instance.

The Name attribute in of this array entry is a URI path relative to the Base Name; namely the Name attribute could simply be the full URI of a requested Resource Instance when Base Name is absent.

The JSON is useful for transporting multiple Resource Instances for example when transporting all Instances of an Object with all Resources, and Resource Instances within a single LwM2M Client response.

In particular, when Base Name is set to the LwM2M Object root (e.g., “/”), the JSON format may support to return a hierarchy of Object Instances when Object Link datatype resources are reported (example given below). The resource instances tree report is performed in using a Breadth-First traversal strategy (see JSON second example below); a given Object Instance MUST appear at most once in that report. The JSON format also includes optional time fields, which allows for multiple versions of representations to be sent in the same payload. The time fields MUST only be used when sending notifications.

Note: According to \[SENML\] specification, time values (Base Time and Time) are represented in floating point as seconds, a missing attribute is considered to have a value of zero.

Regarding the Base Time, “*Positive values (&gt;0) represent an absolute time relative to the unix epoch, while negative values (&lt;= 0) represent a relative time in the past from the current time*” \[SENML\].

Historical version of notifications are typically generated when “Notification Storing When Disabled or Offline” resource of LwM2M Server Object is set to true (see Appendix D.2) and when the Device comes on line after having been disabled for a period of time.

This JSON data format has a Media Type of application/vnd.oma.lwm2m+json.

| **Attributes** | **JSON Variable** | **Mandatory?** | **Description**                                                                                                                   |
|----------------|-------------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------|
| Base Name      | bn                | No             | The base name string which is prepended to the Name value of the entry for forming a globally unique identifier for the resource. |
| Base Time      | bt                | No             | The base time which the Time values are relative to.                                                                              |
| Resource Array | e                 | Yes            | The Resource list as JSON value array according to \[SENML\] with Array parameter extension (Object Link).                        |
|                | Array Parameters  |                |                                                                                                                                   |
|                | Name              | n              | No                                                                                                                                |
|                | Time              | t              | No                                                                                                                                |
|                | Float Value       | v              | One value field is mandatory                                                                                                      |
|                | Boolean Value     | bv             |                                                                                                                                   |
|                | ObjectLink Value  | ov             |                                                                                                                                   |
|                | String Value      | sv             |                                                                                                                                   |

<span id="_Ref467142362" class="anchor"><span id="_Toc492475275" class="anchor"><span id="_Ref368310645" class="anchor"><span id="_Ref404856880" class="anchor"><span id="_Ref429390480" class="anchor"><span id="_Ref429390487" class="anchor"></span></span></span></span></span></span>Table 22: JSON format and description

For example a request to Device Object of the LwM2M example client (Read /3/0) would return the following JSON payload. This example has a size of 457 bytes.

{“bn”:“/3/0/”,

“e”:\[

{"n":"0","sv":"Open Mobile Alliance"},

{"n":"1","sv":"Lightweight M2M Client"},

{"n":"2","sv":"345000123"},

{"n":"3","sv":"1.0"},

{"n":"6/0","v":1},

{"n":"6/1","v":5},

{"n":"7/0","v":3800},

{"n":"7/1","v":5000},

{"n":"8/0","v":125},

{"n":"8/1","v":900},

{"n":"9","v":100},

{"n":"10","v":15},

{"n":"11/0","v":0},

{"n":"13","v":1367491215},

{"n":"14","sv":"+02:00"},

{"n":"16","sv":"U"}\]

}

For example a notification about a Resource containing multiple historical representations of a Temperature Resource (ID:2) (e.g. Instance ID:1 of hypothetical Object ID 72) could result in the following JSON payload:

{“bn”:“/72/“,

“e”:\[

{"n":"1/2","v":22.4,"t":-5},

{"n":"1/2","v":22.9,"t":-30},

{"n":"1/2","v":24.1,"t":-50}\],

"bt":25462634

}

For example a request to Object 65 of the LwM2M example from Figure 28 (Read /65/0) would return the following JSON payload.

Because the Base Name is specified, the full hierarchy linked to the Instance 0 of Object 65 can be reported in a single response (Object 66 Instance 0 & 1, and Instance 0 of Object 67 are part of the payload). This example has a size of 435 bytes.

{ "bn":"/",

"e":\[

{"n":"65/0/0/0","ov":"66:0"},

{"n":"65/0/0/1","ov":"66:1"},

{"n":"65/0/1","sv":"8613800755500"},

{"n":"65/0/2","v":1},

{"n":"66/0/0","sv":"myService1"},

{"n":"66/0/1","sv":"Internet.15.234"},

{"n":"66/0/2","ov":"67:0"},

{"n":"66/1/0","sv":"myService2"},

{"n":"66/1/1","sv":"Internet.15.235"},

{"n":"66/1/2","ov":"FFFF:FFFF"},

{"n":"67/0/0","sv":"85.76.76.84"},

{"n":"67/0/1","sv":"85.76.255.255"}\]

}

<span id="_Toc370916078" class="anchor"><span id="_Toc370922900" class="anchor"><span id="_Ref368262730" class="anchor"><span id="_Ref368262747" class="anchor"><span id="_Ref368309988" class="anchor"><span id="_Toc370916087" class="anchor"><span id="_Toc370922909" class="anchor"></span></span></span></span></span></span></span>For example, a request to Device Object on Resource 0 of the LwM2M example client (Read /3/0/0) could return the following JSON payload.

{“bn”:“/3/0/0”,

“e”:\[

{“sv":"Open Mobile Alliance}\]

}

Access Control
--------------

As the LwM2M Client MAY support one or more LwM2M Servers, there is a need to determine which operation on a certain Object or Object Instance is authorized for which LwM2M Server: Access Control Object is designed for supporting that capability. In the particular case where a single LwM2M Server Account exists in the LwM2M Client, the Server MUST have full access right on all the Objects and Object Instances in the LwM2M Client, and the Access Control Object MAY be not instantiated.

The section 7.3.1 and its sub-sections specify what MUST be applied in multiple LwM2M Servers environment. For consistency and for reducing the efforts of the LwM2M Client when switching from single to multiple LwM2M Servers environment after deployment, the Access Control Object MAY also be instantiated in a single LwM2M2 Server context. In the case the Access Control Object is instantiated in a single LwM2M2 Server context, section 7.3.1 and its sub-sections MUST also be applied that context.

1.  ### Access Control Object

    1.  #### Access Control Object overview

In the presence of several LwM2M Servers, there is a need to determine if a certain LwM2M Server is authorized to instantiate a supported Object in the LwM2M Client. This kind of authorization can only be managed during a Bootstrap Phase.

Furthermore, the LwM2M Client needs to determine - per supported Object Instance - who the “Access Control Owner” of that Object Instance is and which access rights have been granted to other LwM2M Servers likely to interact with that LwM2M Client on such Object Instance.

The Access Control Object is specified in Appendix E.3 and Examples of Access Control Object Instances are presented in Appendix F.

1.  #### Access Control Object Management

    1.  ##### Access Control on Object

To authorize a LwM2M Server to instantiate a certain Object supported by the LwM2M Client, not only an Access Control Object Instance - as defined in the table below - MUST be associated to such an Object, but this AC Object Instance MUST also contained an ACL Resource Instance targeting the authorized LwM2M Server.

This kind of Access Control Object Instance associated with a certain Object, MUST only be created or updated during a Bootstrap Phase. The absence of such an association for a certain Object, prevents this Object to be instantiated by any LwM2M Server.

When such an Access Control Object Instance already exists for a certain Object, this Access Control Object Instance MAY be updated for supporting additional LwM2M Servers; in that case a new ACL Instance per Server is created in that Access Control Object Instance with the Short Server ID of the LwM2M Server as index of this new ACL Instance, and with the “Create” (“C”) access right as ACL Resource value.

| **Resource ID** | **Resource Name**        | **Value**                                                                 |
|-----------------|--------------------------|---------------------------------------------------------------------------|
| 0               | **Object ID**            | ID of the targeted Object                                                 |
| 1               | **Object Instance ID**   | MAX\_ID=65535 (irrelevant)                                                |
| 2               | **ACL**                  | A Resource Instance per LwM2M Server authorized to instantiate the Object 
                                                                              
   5<sup>th</sup> LSB: “Create” is only configured                            |
| 3               | **Access Control Owner** | MAX\_ID=65535 (meaning: managed by Bootstrap Interface)                   |

##### Access Control on Object Instance

For being able to register which operations MAY be performed on an Object Instance by a certain LwM2M Server, this Object Instance MUST be associated to an Access Control Object Instance as defined in the table below.

This kind of Access Control Object Instance associated with a certain Object Instance, MAY be created or updated either during a Bootstrap Phase or through the Device Management and Service Enablement Interface.

In particular:

-   when a LwM2M Server creates under authorization an Object Instance (see section 7.3.2 Authorization) in the LwM2M Client, an Access Control Object Instance MUST be created in the LwM2M Client with the Resources values which MUST be set as given in the table just below. The Access Control Owner Resource is configured with the Short Server ID of the LwM2M Server.

| **Resource ID** | **Resource Name**        | **Value**                                                                       |
|-----------------|--------------------------|---------------------------------------------------------------------------------|
| 0               | **Object ID**            | ID of the targeted Object                                                       |
| 1               | **Object Instance ID**   | ID of the newly created Object Instance                                         |
| 2               | **ACL**                  | Any combination of the Access Right {none,R,W,E,D} is acceptable (Appendix E.3) |
| 3               | **Access Control Owner** | The Short Server ID of the LwM2M Server owner of the associated Object Instance |

-   when this Access Control Object Instance is created during the Bootstrap Phase, ACL(s) and Access Control Owner MUST be set with values respecting the consistency of the LwM2M Client configuration.

-   through the Device Management and Service Enablement Interface, an Access Control Object Instance MUST only be managed by the LwM2M Server declared as the “Access Control Owner” in it.

-   when the LwM2M Server - which is the “Access Control Owner” - adds or modifies (using “Write” operation) access right on the Object Instance for a certain LwM2M Server,

    1.  an ACL Resource having the targeted Short Server ID as ACL Resource Instance ID, has to be instantiated by the LwM2M Client if ACL Resource Instance for the LwM2M Server doesn’t exist yet

    2.  the appropriate access right (R,W,D,E) for that targeted Server on the Object Instance has to be set as ACL Resource Instance value

-   A specific ACL Resource Instance MAY be used to grant access rights to LwM2M Servers (except the one defined as the Access Control Owner) which don’t have their own ACL Resource Instance. The ID of this ACL Resource Instance containing the default access rights MUST be 0.

-   when an Object Instance is removed via “Delete” operation performed by the LwM2M Server which is the “Access Control Owner”, the associated Access Control Object Instance MUST be removed by the LwM2M Client.

The Figure 18 illustrates the Access Control Management of an Object Instance (/X/2) supported by a LwM2M Client. An Access Control Object Instance (/2/Y) is declared in ② which defines the Access Rights applicable to the Instance 2 of the Object X pointed in ①.

In this Access Control Object Instance ②, 4 Instances of the ACL Resource are defined:

-   ACL Instance 101 contains the operations granted to the Server having 101 as Short ID (Instance ID:2 of the Server Object ID:1 as pointed in ③)

-   ACL Instance 22 contains the operations granted to the Server having 22 as Short ID

-   ACL Instance 31 contains the operations granted to the Server having 31 as Short ID

-   ACL Instance 0 contains the operations granted by default to any Server for which a specific ACL Instance is not defined in this Instance of the Access Control Object (default Access Rights).

This Access Control Object Instance ② also contains a reference to a Server (Access Control Owner) which is the only one Server authorized to manage that Instance of the Access Control Object.

<span id="_Ref474361607" class="anchor"><span id="_Toc492474259" class="anchor"></span></span>Figure 18: Illustration of the relations between the LwM2M Access Control Object and the other LwM2M Objects

#### LwM2M Server Context Switch

In a single LwM2M Server context, Access Control Object MAY NOT be instantiated. In that case, adding a new LwM2M Server Account, means this initial single Server context MUST be switched to a multi-Server context in which Access Control Object MUST be instantiated. This context switch must be managed in a Bootstrap Phase.

Note: The Bootstrap Discover command allows to retrieve data regarding the configuration of the initial single LwM2M Server context (list of Objects, Object Instances and Short Server IDs), the Bootstrap Server has then all information to setup a proper multi-Server context from this initial single Server context one.

### Authorization

The LwM2M Client MUST authorize a CREATE operation requested by a LwM2M Server for instantiating a certain Object, only if the associated Access Control Object Instance exists and contains an ACL Resource Instance for that LwM2M Server set with the Access Right “Create” (section 7.3.1.2.1).

The LwM2M Client MUST authorize other operations than CREATE requested by a LwM2M Server either on an Object Instance, or on Resource after performing a two-steps check:

-   1<sup>st</sup> step: the LwM2M Client gets the access right of the targeted Object Instance (as described in section 7.3.2.1) - and checks whether this access right is sufficient – according to the following table - to perform the LwM2M Server requested operation.

| LwM2M Operations                 | Minimum Access Right |
|----------------------------------|----------------------|
| READ – OBSERVE – WRITE-ATTRIBUTE | R                    |
| WRITE                            | W                    |
| DISCOVER                         | -                    |
| DELETE                           | D                    |
| EXECUTE                          | E                    |

-   2<sup>nd</sup> step: if at step 1, the LwM2M Server is authorized to perform the operation, the LwM2M Client still needs to check if the LwM2M Server requested operation is supported by the targeted Resource or Object Instance (details are provided in section 7.3.2.2, 7.3.2.3, and 147138816.7.3.27.3.2.4).

The LwM2M Object specification defines which operations are allowed to be performed on Resource within an Object Instance (Refer to Supported Operations in Appendix D LwM2M Object Template and Guidelines). The operations allowed on a given Resource MUST apply to all the Resource Instances of that Resource.

The LwM2M Client MUST support the authorization procedure described in Section 7.3.2 and its sub-sections.

#### Obtaining Access Right

For “Create” operation sent by the LwM2M Server, the LwM2M Client MUST get access right from the ACL Resource Instance corresponding to this LwM2M Server and located in the Access Control Object Instance associated to the targeted Object. Such an Access Control Object Instance – if it exists – has been provisioned during a Bootstrap Phase (Access Control Owner is MAX\_ID=65535). If this access right doesn’t have the “Create” value, or cannot be obtained, the LwM2M Server has no access right.

For the operations except than “Create” operation the LwM2M Client MUST perform the following procedure:

1.  if this LwM2M Server is the only LwM2M Server Account declared in the LwM2M Client (i.e. single Server environment) , the LwM2M Server has full access right on Object Instance(s). When the LwM2M Client gets an Access Control Object Instance associated with the Object Instance the LwM2M Server has requested access to, it MUST proceed according to the sequence below:

    1.  If the LwM2M Server is declared as Access Control Owner of this Object Instance and there is no ACL Resource Instance for that Server, then LwM2M Client gets full access right.

    2.  If the Client has an ACL Resource Instance for the LwM2M Server, the LwM2M Client gets access right from that ACL Resource Instance.

    3.  If the LwM2M Server is not declared as Access Control Owner of this Object Instance and the Client doesn’t have ACL Resource Instance for that Server, the LwM2M Client gets access right from the ACL Resource Instance (ID:0) containing the default access rights if it exists (Section 7.3.1.2.2).

    4.  If the Client doesn’t have this ACL Resource Instance ID:0 containing the default access rights, then the LwM2M Server has no access right, and an “Unauthorized” error code is reported to the LwM2M Server.

        1.  #### Operation on Resource

When the LwM2M Server targets a Resource, the LwM2M Client MUST obtain an access right for the LwM2M Server on the Object Instance that Resource belongs to according to Section 7.3.2.1 and MUST check if the access right is granted prior to perform the requested operation.

-   If the operation is not permitted, the LwM2M Client MUST send an “Unauthorized” error code to the LwM2M Server.

-   If the operation is permitted, the LwM2M Client verifies if the Resource supports the operation.

    -   If the operation is not supported by the Resource, the LwM2M Client MUST send a “Method Not Allowed” error code to the LwM2M Server.

    -   If the Resource supports the operation, the LwM2M Client MUST perform the requested operation.

        1.  #### Operation on Object Instance

When the LwM2M Server targets an Object Instance, the LwM2M Client MUST obtain an access right for the LwM2M Server on Object Instance according to Section 7.3.2.1 and MUST check if the access right is granted prior to perform the requested operation.

-   If the operation is not permitted, the LwM2M Client MUST send an “Unauthorized” error code to the LwM2M Server.

-   If the operation is permitted, the following cases apply, according to the requested operation:

<!-- -->

-   For the “Write” operation on an Object Instance, the LwM2M Client MUST perform the operation, if all the Resources conveyed in the operation are allowed to perform the “Write” operation. If any Resource does not support the “Write” operation, the LwM2M Client MUST inform the LwM2M Server that the Object Instance cannot perform the requested “Write” operation in sending a “Operation is not supported” error code.

-   For the “Read” and “Observe” operations, the LwM2M Client MUST retrieve all the Resources except the Resource(s) which doesn’t support the “Read” operation and sends the retrieved Resource(s) information to the LwM2M Server.

-   For the “Execute” operation, the LwM2M Client MUST NOT perform the operation, and MUST send an “Operation is not supported” error code to the LwM2M Server.

-   For the “Delete”, “Write-Attributes”, and “Discover” operations, the LwM2M Client MUST perform the operation.

    1.  #### Operation on Object

If a given LwM2M Server targets an Object with a “Write”, “Execute”, or “Delete” operation, the LwM2M Client MUST NOT perform such an operation and MUST send a “Method Not Allowed” error code to the LwM2M Server.

-   When the LwM2M Server targets an Object for the “Create” operation, the LwM2M Client MUST obtain an access right for the LwM2M Server on Object according to Section 7.3.2.1 “Obtaining Access Right” and MUST check if the access right is granted prior to perform the requested operation.

    If the “Create” operation is permitted, the LwM2M Client MUST perform the instantiation on the Object only if all the mandatory Resources are present in the “New Value” parameter (see Section 5). If all the mandatory Resources are not present, the LwM2M Client MUST send a “Bad Request” error code to the LwM2M Server.

    Optional Resources MAY be conveyed in the “New Value” parameter as well; the LwM2M Client MAY ignore the optional resources it doesn’t support. The values of the Read-only Resources MUST be setup by the LwM2M Client only; if a value of such a Read-only Resource is present in the “New Value” parameter, this value MUST simply be ignored. If the payload (New Value) conveys an Object Instance ID in conflict with one already present in the LwM2M Client, the complete request MUST be rejected and a “Bad Request” error code MUST be sent back.

-   The “Discover” operation on Object is specific in the sense, that no access right is needed; the LwM2M Client MUST perform the operation.

-   For the “Read” and “Observe” operations, the LwM2M Client MUST obtain the access right for the LwM2M Server on each Object Instance according to Section 7.3.2.1 “Obtaining Access Right” and the LwM2M Client MUST retrieve all the Object Instances for which the LwM2M Server has “Read” access right; for each of these qualified Object Instances, the LwM2M Client MUST retrieve all the Resources except the Resources which do not support the “Read” operation. The LwM2M Client MUST then aggregate all the information individually produced by the operation on each of these Object Instances and send that to the LwM2M Server.

-   For the “Write-Attributes” operation, the LwM2M Client MUST perform the operation.

    1.  #### Notify Operation Consideration

If the LwM2M Client needs to send a “Notify” operation containing an Object Instance or a Resource to the LwM2M Server, the LwM2M Client MUST check if the LwM2M Server is authorized for the “Read” operation. If the LwM2M Server is not authorized, the Client MUST NOT send the “Notify” operation.

1.  <span id="_Toc492474571" class="anchor"><span id="_Toc492475596" class="anchor"><span id="_Toc51147387" class="anchor"><span id="_Toc51149241" class="anchor"><span id="_Toc492474572" class="anchor"><span id="_Toc492475597" class="anchor"><span id="_Toc492474573" class="anchor"><span id="_Toc492475598" class="anchor"><span id="_Toc492474574" class="anchor"><span id="_Toc492475599" class="anchor"><span id="_Toc492474575" class="anchor"><span id="_Toc492475600" class="anchor"><span id="_Toc492474576" class="anchor"><span id="_Toc492475601" class="anchor"><span id="_Toc492474577" class="anchor"><span id="_Toc492475602" class="anchor"><span id="_Toc492474578" class="anchor"><span id="_Toc492475603" class="anchor"><span id="_Toc492474579" class="anchor"><span id="_Toc492475604" class="anchor"><span id="_Toc492474580" class="anchor"><span id="_Toc492475605" class="anchor"><span id="_Toc492474581" class="anchor"><span id="_Toc492475606" class="anchor"><span id="_Toc492474582" class="anchor"><span id="_Toc492475607" class="anchor"><span id="_Toc492474583" class="anchor"><span id="_Toc492475608" class="anchor"><span id="_Toc492474584" class="anchor"><span id="_Toc492475609" class="anchor"><span id="_Toc492474585" class="anchor"><span id="_Toc492475610" class="anchor"><span id="_Toc492474586" class="anchor"><span id="_Toc492475611" class="anchor"><span id="_Toc492474587" class="anchor"><span id="_Toc492475612" class="anchor"><span id="_Toc492474588" class="anchor"><span id="_Toc492475613" class="anchor"><span id="_Toc492474589" class="anchor"><span id="_Toc492475614" class="anchor"><span id="_Toc492474590" class="anchor"><span id="_Toc492475615" class="anchor"><span id="_Toc492474591" class="anchor"><span id="_Toc492475616" class="anchor"><span id="_Toc492474592" class="anchor"><span id="_Toc492475617" class="anchor"><span id="_Toc492474593" class="anchor"><span id="_Toc492475618" class="anchor"><span id="_Toc492474594" class="anchor"><span id="_Toc492475619" class="anchor"><span id="_Toc492474595" class="anchor"><span id="_Toc492475620" class="anchor"><span id="_Toc492474596" class="anchor"><span id="_Toc492475621" class="anchor"><span id="_Toc492474597" class="anchor"><span id="_Toc492475622" class="anchor"><span id="_Toc492474598" class="anchor"><span id="_Toc492475623" class="anchor"><span id="_Toc492474599" class="anchor"><span id="_Toc492475624" class="anchor"><span id="_Toc492474600" class="anchor"><span id="_Toc492475625" class="anchor"><span id="_Toc492474601" class="anchor"><span id="_Toc492475626" class="anchor"><span id="_Toc492474602" class="anchor"><span id="_Toc492475627" class="anchor"><span id="_Toc492474603" class="anchor"><span id="_Toc492475628" class="anchor"><span id="_Toc492474604" class="anchor"><span id="_Toc492475629" class="anchor"><span id="_Toc492474605" class="anchor"><span id="_Toc492475630" class="anchor"><span id="_Toc492474606" class="anchor"><span id="_Toc492475631" class="anchor"><span id="_Toc492474646" class="anchor"><span id="_Toc492475671" class="anchor"><span id="_Toc492474647" class="anchor"><span id="_Toc492475672" class="anchor"><span id="_Toc492474648" class="anchor"><span id="_Toc492475673" class="anchor"><span id="_Toc492474649" class="anchor"><span id="_Toc492475674" class="anchor"><span id="_Toc492474650" class="anchor"><span id="_Toc492475675" class="anchor"><span id="_Toc492474651" class="anchor"><span id="_Toc492475676" class="anchor"><span id="_Toc492474652" class="anchor"><span id="_Toc492475677" class="anchor"><span id="_Toc492474653" class="anchor"><span id="_Toc492475678" class="anchor"><span id="_Toc492474654" class="anchor"><span id="_Toc492475679" class="anchor"><span id="_Toc492474655" class="anchor"><span id="_Toc492475680" class="anchor"><span id="_Toc492474656" class="anchor"><span id="_Toc492475681" class="anchor"><span id="_Toc492474657" class="anchor"><span id="_Toc492475682" class="anchor"><span id="_Toc492474658" class="anchor"><span id="_Toc492475683" class="anchor"><span id="_Toc492474659" class="anchor"><span id="_Toc492475684" class="anchor"><span id="_Toc492474684" class="anchor"><span id="_Toc492475709" class="anchor"><span id="_Toc492474685" class="anchor"><span id="_Toc492475710" class="anchor"><span id="_Toc492474686" class="anchor"><span id="_Toc492475711" class="anchor"><span id="_Toc492474687" class="anchor"><span id="_Toc492475712" class="anchor"><span id="_Toc465754838" class="anchor"><span id="_Toc465771927" class="anchor"><span id="_Toc466534693" class="anchor"><span id="_Toc467143094" class="anchor"><span id="_Toc467678236" class="anchor"><span id="_Toc469902378" class="anchor"><span id="_Toc470163171" class="anchor"><span id="_Toc472075966" class="anchor"><span id="_Toc472087971" class="anchor"><span id="_Toc418067426" class="anchor"><span id="_Toc418067562" class="anchor"><span id="_Toc429570988" class="anchor"><span id="_Toc492474688" class="anchor"><span id="_Toc492475713" class="anchor"><span id="_Toc492474689" class="anchor"><span id="_Toc492475714" class="anchor"><span id="_Toc492474690" class="anchor"><span id="_Toc492475715" class="anchor"><span id="_Toc492474691" class="anchor"><span id="_Toc492475716" class="anchor"><span id="_Toc492474692" class="anchor"><span id="_Toc492475717" class="anchor"><span id="_Toc492474693" class="anchor"><span id="_Toc492475718" class="anchor"><span id="_Toc492474694" class="anchor"><span id="_Toc492475719" class="anchor"><span id="_Toc492474695" class="anchor"><span id="_Toc492475720" class="anchor"><span id="_Toc492474696" class="anchor"><span id="_Toc492475721" class="anchor"><span id="_Toc492474697" class="anchor"><span id="_Toc492475722" class="anchor"><span id="_Toc492474698" class="anchor"><span id="_Toc492475723" class="anchor"><span id="_Toc492474699" class="anchor"><span id="_Toc492475724" class="anchor"><span id="_Toc492474700" class="anchor"><span id="_Toc492475725" class="anchor"><span id="_Toc492474701" class="anchor"><span id="_Toc492475726" class="anchor"><span id="_Toc492474702" class="anchor"><span id="_Toc492475727" class="anchor"><span id="_Toc492474703" class="anchor"><span id="_Toc492475728" class="anchor"><span id="_Toc492474704" class="anchor"><span id="_Toc492475729" class="anchor"><span id="_Toc492474705" class="anchor"><span id="_Toc492475730" class="anchor"><span id="_Toc492474706" class="anchor"><span id="_Toc492475731" class="anchor"><span id="_Toc492474707" class="anchor"><span id="_Toc492475732" class="anchor"><span id="_Toc492474708" class="anchor"><span id="_Toc492475733" class="anchor"><span id="_Toc492474709" class="anchor"><span id="_Toc492475734" class="anchor"><span id="_Toc492474710" class="anchor"><span id="_Toc492475735" class="anchor"><span id="_Toc492474711" class="anchor"><span id="_Toc492475736" class="anchor"><span id="_Toc492474712" class="anchor"><span id="_Toc492475737" class="anchor"><span id="_Toc492474713" class="anchor"><span id="_Toc492475738" class="anchor"><span id="_Toc492474714" class="anchor"><span id="_Toc492475739" class="anchor"><span id="_Toc492474715" class="anchor"><span id="_Toc492475740" class="anchor"><span id="_Toc492474747" class="anchor"><span id="_Toc492475772" class="anchor"><span id="_Toc492474777" class="anchor"><span id="_Toc492475802" class="anchor"><span id="_Toc492474778" class="anchor"><span id="_Toc492475803" class="anchor"><span id="_Toc492474779" class="anchor"><span id="_Toc492475804" class="anchor"><span id="_Toc492474780" class="anchor"><span id="_Toc492475805" class="anchor"><span id="_Toc492474781" class="anchor"><span id="_Toc492475806" class="anchor"><span id="_Toc492474782" class="anchor"><span id="_Toc492475807" class="anchor"><span id="_Toc492474783" class="anchor"><span id="_Toc492475808" class="anchor"><span id="_Toc466534695" class="anchor"><span id="_Toc467143096" class="anchor"><span id="_Toc467678238" class="anchor"><span id="_Toc469902380" class="anchor"><span id="_Toc470163173" class="anchor"><span id="_Toc472075968" class="anchor"><span id="_Toc472087973" class="anchor"><span id="_Toc492474784" class="anchor"><span id="_Toc492475809" class="anchor"><span id="_Toc492474785" class="anchor"><span id="_Toc492475810" class="anchor"><span id="_Toc492474786" class="anchor"><span id="_Toc492475811" class="anchor"><span id="_Toc492474787" class="anchor"><span id="_Toc492475812" class="anchor"><span id="_Toc492474788" class="anchor"><span id="_Toc492475813" class="anchor"><span id="_Toc492474807" class="anchor"><span id="_Toc492475832" class="anchor"><span id="_Toc492474819" class="anchor"><span id="_Toc492475844" class="anchor"><span id="_Toc492474820" class="anchor"><span id="_Toc492475845" class="anchor"><span id="_Toc492474821" class="anchor"><span id="_Toc492475846" class="anchor"><span id="_Toc492474822" class="anchor"><span id="_Toc492475847" class="anchor"><span id="_Toc418067429" class="anchor"><span id="_Toc418067565" class="anchor"><span id="_Toc429570991" class="anchor"><span id="_Toc492474823" class="anchor"><span id="_Toc492475848" class="anchor"><span id="_Toc492474824" class="anchor"><span id="_Toc492475849" class="anchor"><span id="_Toc492474825" class="anchor"><span id="_Toc492475850" class="anchor"><span id="_Toc492474826" class="anchor"><span id="_Toc492475851" class="anchor"><span id="_Toc492474827" class="anchor"><span id="_Toc492475852" class="anchor"><span id="_Toc492474828" class="anchor"><span id="_Toc492475853" class="anchor"><span id="_Toc492474829" class="anchor"><span id="_Toc492475854" class="anchor"><span id="_Toc492474830" class="anchor"><span id="_Toc492475855" class="anchor"><span id="_Toc492474831" class="anchor"><span id="_Toc492475856" class="anchor"><span id="_Toc492474832" class="anchor"><span id="_Toc492475857" class="anchor"><span id="_Toc492474833" class="anchor"><span id="_Toc492475858" class="anchor"><span id="_Toc492474834" class="anchor"><span id="_Toc492475859" class="anchor"><span id="_Toc492474835" class="anchor"><span id="_Toc492475860" class="anchor"><span id="_Toc492474836" class="anchor"><span id="_Toc492475861" class="anchor"><span id="_Toc492474837" class="anchor"><span id="_Toc492475862" class="anchor"><span id="_Toc492474838" class="anchor"><span id="_Toc492475863" class="anchor"><span id="_Toc492474839" class="anchor"><span id="_Toc492475864" class="anchor"><span id="_Toc492474840" class="anchor"><span id="_Toc492475865" class="anchor"><span id="_Toc492474841" class="anchor"><span id="_Toc492475866" class="anchor"><span id="_Toc492474842" class="anchor"><span id="_Toc492475867" class="anchor"><span id="_Toc418067431" class="anchor"><span id="_Toc418067567" class="anchor"><span id="_Toc429570993" class="anchor"><span id="_Toc357001306" class="anchor"><span id="_Toc492474843" class="anchor"><span id="_Toc492475868" class="anchor"><span id="_Toc492474844" class="anchor"><span id="_Toc492475869" class="anchor"><span id="_Toc492474845" class="anchor"><span id="_Toc492475870" class="anchor"><span id="_Toc492474846" class="anchor"><span id="_Toc492475871" class="anchor"><span id="_Toc466534699" class="anchor"><span id="_Toc467143100" class="anchor"><span id="_Toc467678242" class="anchor"><span id="_Toc469902384" class="anchor"><span id="_Toc470163177" class="anchor"><span id="_Toc472075972" class="anchor"><span id="_Toc472087977" class="anchor"><span id="_Toc492474847" class="anchor"><span id="_Toc492475872" class="anchor"><span id="_Toc492474848" class="anchor"><span id="_Toc492475873" class="anchor"><span id="_Toc492474859" class="anchor"><span id="_Toc492475884" class="anchor"><span id="_Toc492474867" class="anchor"><span id="_Toc492475892" class="anchor"><span id="_Toc492474871" class="anchor"><span id="_Toc492475896" class="anchor"><span id="_Toc492474879" class="anchor"><span id="_Toc492475904" class="anchor"><span id="_Toc492474883" class="anchor"><span id="_Toc492475908" class="anchor"><span id="_Toc492474891" class="anchor"><span id="_Toc492475916" class="anchor"><span id="_Toc492474899" class="anchor"><span id="_Toc492475924" class="anchor"><span id="_Toc492474903" class="anchor"><span id="_Toc492475928" class="anchor"><span id="_Toc492474913" class="anchor"><span id="_Toc492475938" class="anchor"><span id="_Toc492474919" class="anchor"><span id="_Toc492475944" class="anchor"><span id="_Toc492474923" class="anchor"><span id="_Toc492475948" class="anchor"><span id="_Toc492474931" class="anchor"><span id="_Toc492475956" class="anchor"><span id="_Toc492474935" class="anchor"><span id="_Toc492475960" class="anchor"><span id="_Toc492474943" class="anchor"><span id="_Toc492475968" class="anchor"><span id="_Toc492474947" class="anchor"><span id="_Toc492475972" class="anchor"><span id="_Toc492474957" class="anchor"><span id="_Toc492475982" class="anchor"><span id="_Toc492474963" class="anchor"><span id="_Toc492475988" class="anchor"><span id="_Toc492474967" class="anchor"><span id="_Toc492475992" class="anchor"><span id="_Toc492474971" class="anchor"><span id="_Toc492475996" class="anchor"><span id="_Toc492474975" class="anchor"><span id="_Toc492476000" class="anchor"><span id="_Toc492474983" class="anchor"><span id="_Toc492476008" class="anchor"><span id="_Toc492474987" class="anchor"><span id="_Toc492476012" class="anchor"><span id="_Toc492474991" class="anchor"><span id="_Toc492476016" class="anchor"><span id="_Toc492474995" class="anchor"><span id="_Toc492476020" class="anchor"><span id="_Toc492474999" class="anchor"><span id="_Toc492476024" class="anchor"><span id="_Toc492475007" class="anchor"><span id="_Toc492476032" class="anchor"><span id="_Toc492475011" class="anchor"><span id="_Toc492476036" class="anchor"><span id="_Toc492475015" class="anchor"><span id="_Toc492476040" class="anchor"><span id="_Toc492475019" class="anchor"><span id="_Toc492476044" class="anchor"><span id="_Toc492475023" class="anchor"><span id="_Toc492476048" class="anchor"><span id="_Toc492475027" class="anchor"><span id="_Toc492476052" class="anchor"><span id="_Toc492475031" class="anchor"><span id="_Toc492476056" class="anchor"><span id="_Toc492475035" class="anchor"><span id="_Toc492476060" class="anchor"><span id="_Toc492475043" class="anchor"><span id="_Toc492476068" class="anchor"><span id="_Toc492475047" class="anchor"><span id="_Toc492476072" class="anchor"><span id="_Toc492475051" class="anchor"><span id="_Toc492476076" class="anchor"><span id="_Toc492475055" class="anchor"><span id="_Toc492476080" class="anchor"><span id="_Toc492475063" class="anchor"><span id="_Toc492476088" class="anchor"><span id="_Toc492475067" class="anchor"><span id="_Toc492476092" class="anchor"><span id="_Toc492475071" class="anchor"><span id="_Toc492476096" class="anchor"><span id="_Toc492475075" class="anchor"><span id="_Toc492476100" class="anchor"><span id="_Toc492475083" class="anchor"><span id="_Toc492476108" class="anchor"><span id="_Toc492475087" class="anchor"><span id="_Toc492476112" class="anchor"><span id="_Toc492475091" class="anchor"><span id="_Toc492476116" class="anchor"><span id="_Toc492475095" class="anchor"><span id="_Toc492476120" class="anchor"><span id="_Toc492475103" class="anchor"><span id="_Toc492476128" class="anchor"><span id="_Toc492475107" class="anchor"><span id="_Toc492476132" class="anchor"><span id="_Toc492475111" class="anchor"><span id="_Toc492476136" class="anchor"><span id="_Toc492475115" class="anchor"><span id="_Toc492476140" class="anchor"><span id="_Toc492475126" class="anchor"><span id="_Toc492476151" class="anchor"><span id="_Toc492475130" class="anchor"><span id="_Toc492476155" class="anchor"><span id="_Toc492475134" class="anchor"><span id="_Toc492476159" class="anchor"><span id="_Toc492475138" class="anchor"><span id="_Toc492476163" class="anchor"><span id="_Toc492475142" class="anchor"><span id="_Toc492476167" class="anchor"><span id="_Toc492475150" class="anchor"><span id="_Toc492476175" class="anchor"><span id="_Toc492475151" class="anchor"><span id="_Toc492476176" class="anchor"><span id="_Toc429570996" class="anchor"><span id="_Toc492475152" class="anchor"><span id="_Toc492476177" class="anchor"><span id="_Toc492475153" class="anchor"><span id="_Toc492476178" class="anchor"><span id="_Toc492475154" class="anchor"><span id="_Toc492476179" class="anchor"><span id="_Toc492475155" class="anchor"><span id="_Toc492476180" class="anchor"><span id="_Toc492475156" class="anchor"><span id="_Toc492476181" class="anchor"><span id="_Toc492475157" class="anchor"><span id="_Toc492476182" class="anchor"><span id="_Toc370916101" class="anchor"><span id="_Toc370922923" class="anchor"><span id="_Ref373945283" class="anchor"><span id="_Ref373945385" class="anchor"><span id="_Toc492476183" class="anchor"><span id="_Toc493059869" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>Change History (Informative)

2.  <span id="_Toc370916102" class="anchor"><span id="_Toc370922924" class="anchor"><span id="_Toc492476184" class="anchor"><span id="_Toc493059870" class="anchor"></span></span></span></span>Approved Version History

|                                             |             |                                                                                                    |
|---------------------------------------------|-------------|----------------------------------------------------------------------------------------------------|
| Reference                                   | Date        | Description                                                                                        |
| OMA-TS-LightweightM2M-V1\_0-20170208-A      | 08 Feb 2017 | Status changed to Approved by TP                                                                   
                                                                                                       
   TP Ref \# OMA-TP-2017-0009-INP\_LightweightM2M-V1\_0\_ERP\_for\_Final\_Approval                     |
| OMA-TS-LightweightM2M-V1\_0\_1-20170704-A   | 04 Jul 2017 | Status changed to Approved by TP                                                                   
                                                                                                       
   TP Ref \# OMA-TP-2017-0029R01-INP\_LightweightM2M\_V1.0.1\_ERP\_for\_Final\_Approval\_Notification  |
| OMA-TS-LightweightM2M-V1\_1-Core-20170915-D | 15 Sep 2017 | Split the 1\_0\_1 approved TS (see above row for reference) in to Core and Transport Bindings      
                                                                                                       
   Deleted 7.1, 7.2, 8 from Core TS and moved it to Transport TS                                       |

1.  <span id="_Toc319321637" class="anchor"><span id="_Toc339548465" class="anchor"><span id="_Toc365994798" class="anchor"><span id="_Ref368310684" class="anchor"><span id="_Toc370916104" class="anchor"><span id="_Toc370922926" class="anchor"><span id="_Ref373946610" class="anchor"><span id="_Toc492476185" class="anchor"><span id="_Toc493059871" class="anchor"></span></span></span></span></span></span></span></span></span>Static Conformance Requirements (Normative)

The notation used in this appendix is specified in \[SCRRULES\].

1.  <span id="_Toc319321638" class="anchor"><span id="_Toc339548466" class="anchor"><span id="_Toc365994799" class="anchor"><span id="_Toc370916105" class="anchor"><span id="_Toc370922927" class="anchor"><span id="_Toc492476186" class="anchor"><span id="_Toc493059872" class="anchor"></span></span></span></span></span></span></span>SCR for LwM2M Client

2.  <span id="_Toc370916106" class="anchor"><span id="_Toc370922928" class="anchor"><span id="_Toc492476187" class="anchor"><span id="_Toc319321639" class="anchor"><span id="_Toc339548467" class="anchor"><span id="_Toc493059873" class="anchor"></span></span></span></span></span></span>Bootstrap Interface

|                    |                                                                                                   |                             |                       |
|--------------------|---------------------------------------------------------------------------------------------------|-----------------------------|-----------------------|
| **Item**           | **Function**                                                                                      | **Reference**               | **Requirement**       |
| LwM2M-BOOT-001-C-M | Support of at least one Bootstrap Mode                                                            | Section 5.1                 |                       |
| LwM2M-BOOT-002-C-O | Support of Factory Bootstrap Mode                                                                 | Section 5.2.3.1             |                       |
| LwM2M-BOOT-003-C-O | Support of Bootstrap from Smartcard                                                               | Section 5.2.3.2, Appendix F | LwM2M-BOOT-012C-O     |
| LwM2M-BOOT-004-C-O | Support of Client Initiated Bootstrap                                                             | Section 5.2.3.3             |                       |
| LwM2M-BOOT-005-C-O | Support of Server Initiated Bootstrap                                                             | Section 5.2.3.4             |                       |
| LwM2M-BOOT-006-C-M | Support of LwM2M Server Bootstrap Information                                                     | Section 5.2.2               |                       |
| LwM2M-BOOT-007-C-O | Support of LwM2M Bootstrap-Server Bootstrap Information                                           | Section 5.2.2               |                       |
| LwM2M-BOOT-008-C-M | Support of accepting Bootstrap Information transferred                                            | Section 5.2.2               |                       |
| LwM2M-BOOT-009-C-M | Support of Bootstrap Sequence                                                                     | Section 5.2.4               |                       |
| LwM2M-BOOT-010-C-M | Support of Bootstrap Security                                                                     | Section 5.2.5               |                       |
| LwM2M-BOOT-011-C-O | Support of Bootstrap from Smartcard with Secure Channel                                           | Section 5.2.3.2, Appendix F | LwM2M-BOOT-012C-O AND 
                           
    LwM2M-SEC-007-C-O      |
| LwM2M-BOOT-012-C-O | Retrieve & Process bootstrap data from Smartcard                                                  | Section 5.2.3.2             |                       |
| LwM2M-BOOT-013-C-O | Check for Bootstrap Data change in Smartcard                                                      | Section 5.2.3.2             |                       |
| LwM2M-BOOT-014-C-O | Support of the BOOSTRAP-REQUEST operation                                                         | Section 5.2.7.1             | LwM2M-BOOT-004-C-O    |
| LwM2M-BOOT-015-C-O | Support of the BOOTSTRAP-FINISH, BOOTSTRAP DISCOVER, BOOTSTRAP WRITE, BOOTSTRAP DELETE operations | Section 5.2.7.2             
                                
   Section 5.2.7.3              
                                
   Section 5.2.7.4              
                                
   Section 5.2.7.5              | LwM2M-BOOT-004-C-O OR 
                           
    LwM2M-BOOT-005-C-O     |
| LwM2M-BOOT-016-C-O | Check and report Bootstrap Configuration Inconsistency                                            | Section 5.2.6               | LwM2M-BOOT-004-C-O OR 
                           
    LwM2M-BOOT-005-C-O     |

1.  <span id="_Toc370916107" class="anchor"><span id="_Toc370922929" class="anchor"><span id="_Toc492476188" class="anchor"><span id="_Toc493059874" class="anchor"></span></span></span></span>Client Registration

|                   |                                                                                |                        |                        |
|-------------------|--------------------------------------------------------------------------------|------------------------|------------------------|
| **Item**          | **Function**                                                                   | **Reference**          | **Requirement**        |
| LwM2M-CR-001-C-M  | Support of “Register” operation                                                | Section 5.3.1          |                        |
| LwM2M-CR-002-C-M  | Support of Endpoint Client Name parameter                                      | Section 5.3.1          |                        |
| LwM2M-CR-003-C-M  | Support of Lifetime parameter                                                  | Section 5.3.1          |                        |
| LwM2M-CR-004-C-M  | Support of LwM2M Version parameter                                             | Section 5.3.1          |                        |
| LwM2M-CR-005-C-M  | Support of Binding Mode parameter                                              | Section 5.3.1, 5.3.1.1 |                        |
| LwM2M-CR-006-C-O  | Support of SMS Number parameter                                                | Section 5.3.1          |                        |
| LwM2M-CR-007-C-M  | Support of Object and Object Instances parameter                               | Section 5.3.1          |                        |
| LwM2M-CR-008-C-M  | Support of “Update” operation                                                  | Section 5.3.2          |                        |
| LwM2M-CR-009-C-O  | Support of “De-register” operation                                             | Section 5.3.3          |                        |
| LwM2M-CR-010-C-O  | Support of Updating Bootstrap Information from Smartcard at Register/Update    | Section 5.3.2          | (LwM2M-CR-001-C-M OR   
                            
    LwM2M-CR-008-C-M ) AND  
                            
    LwM2M-BOOT-013-C-O AND  
                            
    (LwM2M-BOOT-003-C-O OR  
                            
    LwM2M-BOOT-011-C-O)     |
| LwM2M-CR-0011-C-M | No Security Object (ID:0) and Security Object Instances in the parameters list | Section 5.3.1          |                        |
| LwM2M-CR-0012-C-M | Support of Object Versioning in the Object and Object Instances parameter list | Section 5.3.1          |                        |

1.  <span id="_Toc370916108" class="anchor"><span id="_Toc370922930" class="anchor"><span id="_Toc492476189" class="anchor"><span id="_Toc493059875" class="anchor"></span></span></span></span>Device Management and Service Enablement Interface

|                    |                                         |               |                 |
|--------------------|-----------------------------------------|---------------|-----------------|
| **Item**           | **Function**                            | **Reference** | **Requirement** |
| LwM2M-DMSE-001-C-M | Support of “Read” operation             | Section 5.4.1 |                 |
| LwM2M-DMSE-002-C-M | Support of “Discover” operation         | Section 5.4.2 |                 |
| LwM2M-DMSE-003-C-M | Support of “Write” operation            | Section 5.4.3 |                 |
| LwM2M-DMSE-004-C-M | Support of “Write-Attributes” operation | Section 5.4.4 |                 |
| LwM2M-DMSE-005-C-O | Support of Minimum Period parameter     | Section 5.4.4 |                 |
| LwM2M-DMSE-006-C-O | Support of Maximum Period parameter     | Section 5.4.4 |                 |
| LwM2M-DMSE-007-C-O | Support of Greater Than parameter       | Section 5.4.4 |                 |
| LwM2M-DMSE-008-C-O | Support of Less Than parameter          | Section 5.4.4 |                 |
| LwM2M-DMSE-009-C-O | Support of Step parameter               | Section 5.4.4 |                 |
| LwM2M-DMSE-010-C-O | Support of Cancel parameter             | Section 5.4.4 |                 |
| LwM2M-DMSE-011-C-M | Support of “Execute” operation          | Section 5.4.5 |                 |
| LwM2M-DMSE-012-C-M | Support of “Create” operation           | Section 5.4.6 |                 |
| LwM2M-DMSE-013-C-M | Support of “Delete” operation           | Section 5.4.7 |                 |

1.  <span id="_Toc370916109" class="anchor"><span id="_Toc370922931" class="anchor"><span id="_Toc492476190" class="anchor"><span id="_Toc493059876" class="anchor"></span></span></span></span>Information Reporting

|                  |                                           |               |                 |
|------------------|-------------------------------------------|---------------|-----------------|
| **Item**         | **Function**                              | **Reference** | **Requirement** |
| LwM2M-IR-001-C-M | Support of “Observe” operation            | Section 5.5.1 |                 |
| LwM2M-IR-002-C-M | Support of “Notify” operation             | Section 5.5.2 |                 |
| LwM2M-IR-003-C-M | Support of “Cancel Observation” operation | Section 5.5.3 |                 |

1.  <span id="_Toc370916110" class="anchor"><span id="_Toc370922932" class="anchor"><span id="_Toc492476191" class="anchor"><span id="_Toc493059877" class="anchor"></span></span></span></span>Data Format

|                  |                              |                              |                 |
|------------------|------------------------------|------------------------------|-----------------|
| **Item**         | **Function**                 | **Reference**                | **Requirement** |
| LwM2M-DF-001-C-O | Support of Plain Text format | Section 6.4, 6.4.1           |                 |
| LwM2M-DF-002-C-O | Support of Opaque format     | Section 147138816.6.4, 6.4.2 |                 |
| LwM2M-DF-003-C-M | Support of TLV format        | Section 147138816.6.4, 6.4.3 |                 |
| LwM2M-DF-004-C-O | Support of JSON format       | Section 147138816.6.4, 6.4.4 |                 |

1.  <span id="_Toc370916111" class="anchor"><span id="_Toc370922933" class="anchor"><span id="_Toc492476192" class="anchor"><span id="_Toc493059878" class="anchor"></span></span></span></span>Security

|                   |                                                   |                         |                                                                                  |
|-------------------|---------------------------------------------------|-------------------------|----------------------------------------------------------------------------------|
| **Item**          | **Function**                                      | **Reference**           | **Requirement**                                                                  |
| LwM2M-SEC-001-C-M | Support of at least one key mode                  | Section 7.1             | LwM2M-SEC-002-C-O OR LwM2M-SEC-003-C-O OR LwM2M-SEC-004-C-O OR LwM2M-SEC-004-C-O |
| LwM2M-SEC-002-C-O | Support of Pre-Shared Keys mode                   | Section 7.1.7           |                                                                                  |
| LwM2M-SEC-003-C-O | Support of Raw Public Key Certificates mode       | Section 7.1.8           |                                                                                  |
| LwM2M-SEC-004-C-O | Support of X.509 Certificates mode                | Section 7.1.9           |                                                                                  |
| LwM2M-SEC-005-C-O | Support of No Sec mode                            | Section 7.1.10          |                                                                                  |
| LwM2M-SEC-006-C-O | Support of UDP Channel Security                   | Section 7.1             |                                                                                  |
| LwM2M-SEC-007-C-O | Support of Smartcard Secure Channel               | Section 7.1, Appendix G | LwM2M-SEC-009-C-O                                                                |
| LwM2M-SEC-008-C-O | Support of Access Control Mechanism               | Section 7.3             |                                                                                  |
| LwM2M-SEC-009-C-O | Smartcard Secure Channel using \[GLOBALPLATFORM\] 
                                                     
  \[GP SCP03\]                                       |                         |                                                                                  |

1.  <span id="_Toc370916112" class="anchor"><span id="_Toc370922934" class="anchor"><span id="_Toc492476193" class="anchor"><span id="_Toc493059879" class="anchor"></span></span></span></span>Mechanism

|                                                                  |                        |               |                 |
|------------------------------------------------------------------|------------------------|---------------|-----------------|
| **Item**                                                         | **Function**           | **Reference** | **Requirement** |
| LwM2M-MEC-001-C-O                                                | Support of Queue Mode  | Section 8.3   |                 |
| <span id="_Toc365994807" class="anchor"></span>LwM2M-MEC-002-C-M | Support of UDP Binding | Section 8.6.1 |                 |
| LwM2M-MEC-003-C-O                                                | Support of SMS Binding | Section 8.6.2 |                 |

1.  <span id="_Toc370916113" class="anchor"><span id="_Toc370922935" class="anchor"><span id="_Toc492476194" class="anchor"><span id="_Toc493059880" class="anchor"></span></span></span></span>Objects

|                   |                                           |               |                 |
|-------------------|-------------------------------------------|---------------|-----------------|
| **Item**          | **Function**                              | **Reference** | **Requirement** |
| LwM2M-OBJ-001-C-M | Support of LwM2M Security Object          | Appendix E.1  |                 |
| LwM2M-OBJ-002-C-M | Support of LwM2M Server Object            | Appendix E.2  |                 |
| LwM2M-OBJ-003-C-O | Support of Access Control Object          | Appendix E.3  |                 |
| LwM2M-OBJ-004-C-M | Support of Device Object                  | Appendix E.4  |                 |
| LwM2M-OBJ-005-C-O | Support of Connectivity Monitoring Object | Appendix E.5  |                 |
| LwM2M-OBJ-006-C-O | Support of Firmware Update Object         | Appendix E.6  |                 |
| LwM2M-OBJ-007-C-O | Support of Location Object                | Appendix E.7  |                 |
| LwM2M-OBJ-008-C-O | Support of Connectivity Statistics Object | Appendix E.8  |                 |

1.  <span id="_Toc370916114" class="anchor"><span id="_Toc370922936" class="anchor"><span id="_Toc492476195" class="anchor"><span id="_Toc493059881" class="anchor"></span></span></span></span>SCR for LwM2M Server

2.  <span id="_Toc370916115" class="anchor"><span id="_Toc370922937" class="anchor"><span id="_Toc492476196" class="anchor"><span id="_Toc493059882" class="anchor"></span></span></span></span>Bootstrap Interface

|                    |                                       |                 |                 |
|--------------------|---------------------------------------|-----------------|-----------------|
| **Item**           | **Function**                          | **Reference**   | **Requirement** |
| LwM2M-BOOT-005-S-M | Support of Server Initiated Bootstrap | Section 5.2.3.4 |                 |
| LwM2M-BOOT-010-S-M | Support of Bootstrap Security         | Section 5.2.5   |                 |

1.  <span id="_Toc370916116" class="anchor"><span id="_Toc370922938" class="anchor"><span id="_Toc492476197" class="anchor"><span id="_Toc493059883" class="anchor"></span></span></span></span>Client Registration

|                  |                                                  |                        |                 |
|------------------|--------------------------------------------------|------------------------|-----------------|
| **Item**         | **Function**                                     | **Reference**          | **Requirement** |
| LwM2M-CR-001-S-M | Support of “Register” operation                  | Section 5.3.1          |                 |
| LwM2M-CR-002-S-M | Support of Endpoint Client Name parameter        | Section 5.3.1          |                 |
| LwM2M-CR-003-S-M | Support of Lifetime parameter                    | Section 5.3.1          |                 |
| LwM2M-CR-004-S-M | Support of LwM2M Version parameter               | Section 5.3.1          |                 |
| LwM2M-CR-005-S-M | Support of Binding Mode parameter                | Section 5.3.1, 5.3.1.1 |                 |
| LwM2M-CR-006-S-M | Support of SMS Number parameter                  | Section 5.3.1          |                 |
| LwM2M-CR-007-S-M | Support of Object and Object Instances parameter | Section 5.3.1          |                 |
| LwM2M-CR-008-S-M | Support of “Update” operation                    | Section 5.3.2          |                 |
| LwM2M-CR-009-S-M | Support of “De-register” operation               | Section 5.3.3          |                 |

1.  <span id="_Toc370916117" class="anchor"><span id="_Toc370922939" class="anchor"><span id="_Toc492476198" class="anchor"><span id="_Toc493059884" class="anchor"></span></span></span></span>Device Management and Service Enablement Interface

|                    |                                         |               |                 |
|--------------------|-----------------------------------------|---------------|-----------------|
| **Item**           | **Function**                            | **Reference** | **Requirement** |
| LwM2M-DMSE-001-S-M | Support of “Read” operation             | Section 5.4.1 |                 |
| LwM2M-DMSE-002-S-M | Support of “Discover” operation         | Section 5.4.2 |                 |
| LwM2M-DMSE-003-S-M | Support of “Write” operation            | Section 5.4.3 |                 |
| LwM2M-DMSE-004-S-M | Support of “Write-Attributes” operation | Section 5.4.4 |                 |
| LwM2M-DMSE-005-S-M | Support of Minimum Period parameter     | Section 5.4.4 |                 |
| LwM2M-DMSE-006-S-M | Support of Maximum Period parameter     | Section 5.4.4 |                 |
| LwM2M-DMSE-007-S-M | Support of Greater Than parameter       | Section 5.4.4 |                 |
| LwM2M-DMSE-008-S-M | Support of Less Than parameter          | Section 5.4.4 |                 |
| LwM2M-DMSE-009-S-M | Support of Step parameter               | Section 5.4.4 |                 |
| LwM2M-DMSE-010-S-M | Support of “Execute” operation          | Section 5.4.5 |                 |
| LwM2M-DMSE-011-S-M | Support of “Create” operation           | Section 5.4.6 |                 |
| LwM2M-DMSE-012-S-M | Support of “Delete” operation           | Section 5.4.7 |                 |

1.  <span id="_Toc370916118" class="anchor"><span id="_Toc370922940" class="anchor"><span id="_Toc492476199" class="anchor"><span id="_Toc493059885" class="anchor"></span></span></span></span>Information Reporting

|                  |                                           |               |                 |
|------------------|-------------------------------------------|---------------|-----------------|
| **Item**         | **Function**                              | **Reference** | **Requirement** |
| LwM2M-IR-001-S-M | Support of “Observe” operation            | Section 5.5.1 |                 |
| LwM2M-IR-002-S-M | Support of “Notify” operation             | Section 5.5.2 |                 |
| LwM2M-IR-003-S-M | Support of “Cancel Observation” operation | Section 5.5.3 |                 |

1.  <span id="_Toc370916119" class="anchor"><span id="_Toc370922941" class="anchor"><span id="_Toc492476200" class="anchor"><span id="_Toc493059886" class="anchor"></span></span></span></span>Data Format

|                  |                              |                    |                 |
|------------------|------------------------------|--------------------|-----------------|
| **Item**         | **Function**                 | **Reference**      | **Requirement** |
| LwM2M-DF-001-S-M | Support of Plain Text format | Section 6.4, 6.4.1 |                 |
| LwM2M-DF-002-S-M | Support of Opaque format     | Section 6.4, 6.4.2 |                 |
| LwM2M-DF-003-S-M | Support of TLV format        | Section 6.4, 6.4.3 |                 |
| LwM2M-DF-004-S-M | Support of JSON format       | Section 6.4, 6.4.4 |                 |

1.  <span id="_Toc370916120" class="anchor"><span id="_Toc370922942" class="anchor"><span id="_Toc492476201" class="anchor"><span id="_Toc493059887" class="anchor"></span></span></span></span>Security

|                   |                                             |                |                 |
|-------------------|---------------------------------------------|----------------|-----------------|
| **Item**          | **Function**                                | **Reference**  | **Requirement** |
| LwM2M-SEC-002-S-M | Support of Pre-Shared Keys mode             | Section 7.1.7  |                 |
| LwM2M-SEC-003-S-M | Support of Raw Public Key Certificates mode | Section 7.1.8  |                 |
| LwM2M-SEC-004-S-M | Support of X.509 Certificates mode          | Section 7.1.9  |                 |
| LwM2M-SEC-005-S-M | Support of No Sec mode                      | Section 7.1.10 |                 |
| LwM2M-SEC-006-S-M | Support of UDP Channel Security             | Section 7.1    |                 |

1.  <span id="_Toc370916121" class="anchor"><span id="_Toc370922943" class="anchor"><span id="_Toc492476202" class="anchor"><span id="_Toc493059888" class="anchor"></span></span></span></span>Mechanism

|                   |                        |               |                 |
|-------------------|------------------------|---------------|-----------------|
| **Item**          | **Function**           | **Reference** | **Requirement** |
| LwM2M-MEC-001-S-M | Support of Queue Mode  | Section 8.3   |                 |
| LwM2M-MEC-002-S-M | Support of UDP Binding | Section 8.6.1 |                 |
| LwM2M-MEC-003-S-O | Support of SMS Binding | Section 8.6.2 |                 |

1.  <span id="_Toc370916122" class="anchor"><span id="_Toc370922944" class="anchor"><span id="_Toc492476203" class="anchor"><span id="_Toc493059889" class="anchor"></span></span></span></span>Objects

|                   |                                           |               |                 |
|-------------------|-------------------------------------------|---------------|-----------------|
| **Item**          | **Function**                              | **Reference** | **Requirement** |
| LwM2M-OBJ-001-S-M | Support of LwM2M Security Object          | Appendix E.1  |                 |
| LwM2M-OBJ-002-S-M | Support of LwM2M Server Object            | Appendix E.2  |                 |
| LwM2M-OBJ-003-S-O | Support of Access Control Object          | Appendix E.3  |                 |
| LwM2M-OBJ-004-S-M | Support of Device Object                  | Appendix E.4  |                 |
| LwM2M-OBJ-005-S-O | Support of Connectivity Monitoring Object | Appendix E.5  |                 |
| LwM2M-OBJ-006-S-O | Support of Firmware Update Object         | Appendix E.6  |                 |
| LwM2M-OBJ-007-S-O | Support of Location Object                | Appendix E.7  |                 |
| LwM2M-OBJ-008-S-O | Support of Connectivity Statistics Object | Appendix E.8  |                 |

1.  <span id="_Toc370916123" class="anchor"><span id="_Toc370922945" class="anchor"><span id="_Ref390936821" class="anchor"><span id="_Ref390936853" class="anchor"><span id="_Ref398727991" class="anchor"><span id="_Ref398728155" class="anchor"><span id="_Ref436754394" class="anchor"><span id="_Ref472081954" class="anchor"><span id="_Toc492476204" class="anchor"><span id="_Toc493059890" class="anchor"></span></span></span></span></span></span></span></span></span></span>Data Types (Normative)

<span id="OLE_LINK7" class="anchor"><span id="OLE_LINK8" class="anchor"></span></span>This appendix defines the data types that a Resource can be defined to be.

<table>
<tbody>
<tr class="odd">
<td><strong>Data Type</strong></td>
<td><strong>Description</strong></td>
<td><strong>Text Format</strong></td>
<td><strong>TLV Format</strong></td>
</tr>
<tr class="even">
<td><strong>String</strong></td>
<td>A UTF-8 string, the minimum and/or maximum length of the String MAY be defined.</td>
<td>Represented as a UTF-8 string.</td>
<td>Represented as a UTF-8 string of Length bytes.</td>
</tr>
<tr class="odd">
<td><strong>Integer</strong></td>
<td>An 8, 16, 32 or 64-bit signed integer. The valid range of the value for a Resource SHOULD be defined. This data type is also used for the purpose of enumeration.</td>
<td><p>Represented as an ASCII signed integer.</p>
<p>For example, the integer value -750 results in the 4 characters/byte long ASCII string “-750”.</p></td>
<td>Represented as a binary signed integer in network byte order, and in two’s complement representation. The value may be 1 (8-bit), 2 (16-bit), 4 (32-bit) or 8 (64-bit) bytes long as indicated by the Length field. When transmitted over network, the data is represented in network byte order (big endian).</td>
</tr>
<tr class="even">
<td><strong>Float</strong></td>
<td>A 32 or 64-bit floating point value. The valid range of the value for a Resource SHOULD be defined.</td>
<td><p>Represented as an ASCII signed numeric representation.</p>
<p>For example, we use a floating point number with the significand of 6.667, a base of 10 and the exponent of -11. This represents the number 6.667e-11 in scientific notation and will be represented as &quot;0.00000000006667&quot; as an ASCII string.</p></td>
<td>Represented as a binary floating point value [IEEE 754-2008] [FLOAT]. The value may use the binary32 (4 byte length) or binary64 (8 byte length) format as indicated by the Length field. When transmitted over network, the data is represented in network byte order (big endian).</td>
</tr>
<tr class="odd">
<td><strong>Boolean</strong></td>
<td>An 8 bit unsigned integer with the value 0 for False and the value 1 for True.</td>
<td>Represented as the ASCII value 0 or 1.</td>
<td>Represented as an 8 bit unsigned Integer with value 0, or 1. The Length of a Boolean value MUST always be 1 byte.</td>
</tr>
<tr class="even">
<td><strong>Opaque</strong></td>
<td>A sequence of binary octets, the minimum and/or maximum length of the String MAY be defined.</td>
<td><p>Represented as a Base64 encoding of the binary data [RFC4648].</p>
<p>For example, the sequence of bytes (in hex notation) {0x01, 0x02, 0x03, 0x04, 0x05} converts to the ASCII string “AQIDBAU=” in Base64 encoding.</p></td>
<td>Represented as a sequence of binary data of Length bytes.</td>
</tr>
<tr class="odd">
<td><strong>Time</strong></td>
<td>Unix Time. A signed integer representing the number of seconds since Jan 1<sup>st</sup>, 1970 in the UTC time zone.</td>
<td>Represented as an ASCII integer.<br />
For example, 1476186613 seconds since Jan 01 1970, which represents Tuesday, 11-Oct-16 11:50:13 UTC, are represented as the ASCII string &quot;1476186613&quot;, which has 10 characters/bytes.</td>
<td>Same representation as Integer.</td>
</tr>
<tr class="even">
<td><strong>Objlnk</strong></td>
<td><p>Object Link. The object link is used to refer an Instance of a given Object. An Object link value is composed of two concatenated 16 bit unsigned integers following the Network Byte Order convention. The Most Significant Half-word is an Object ID, the Least Significant Half-word is an Object Instance ID.</p>
<p>An Object Link referencing no Object Instance will contain the concatenation of 2 MAX-ID values (null link).</p></td>
<td>Represented as a UTF-8 string containing 2 16-bits ASCII integers separated by a ‘:’ ASCII character.</td>
<td>Same representation as two 16 bit unsigned integers one beside the other. The first one represents the Object ID, and the second one represents the Object Instance ID. This value is always 4 bytes long.</td>
</tr>
<tr class="odd">
<td><strong>none</strong></td>
<td>no specific data type affected to that resource: it exclusively concerns Executable Resource</td>
<td>Not applicable</td>
<td>Not applicable</td>
</tr>
</tbody>
</table>

<span id="_Toc492474260" class="anchor"><span id="_Ref467141522" class="anchor"><span id="_Ref404864748" class="anchor"><span id="Figure_26" class="anchor"></span></span></span></span>Figure 28: Object link Resource simple illustration

1.  <span id="_Ref404857365" class="anchor"><span id="_Toc492476205" class="anchor"><span id="_Toc493059891" class="anchor"></span></span></span>LwM2M Object Template and Guidelines (Normative)

This Appendix provides the template to be used for the specification of LwM2M Objects. Furthermore, guidelines for the creation of LwM2M Objects are provided.

The XML versions of LwM2M Objects MUST comply with the XML schema which can be found here: <http://openmobilealliance.org/tech/profiles/LWM2M.xsd>

1.  <span id="_Ref368263291" class="anchor"><span id="_Ref368263481" class="anchor"><span id="_Ref368312905" class="anchor"><span id="_Toc370916125" class="anchor"><span id="_Toc370922947" class="anchor"><span id="_Toc492476206" class="anchor"><span id="_Toc493059892" class="anchor"></span></span></span></span></span></span></span>Object Template

**Appendix D.x LwM2M Object: *&lt;LwM2M object name&gt;***

**Description**

**Object definition:**

|             |                         |                 |                    |                                                     |
|-------------|-------------------------|-----------------|--------------------|-----------------------------------------------------|
| **Name**    | **Object ID **          | **Instances**   | **Mandatory**      | **Object URN**                                      |
| Object Name | 16-bit Unsigned Integer | Multiple/Single | Mandatory/Optional | urn:oma:lwm2m:{oma,ext,x}:{Object ID}\[:{version}\] |

-   **Name:** specifies the Object name.

-   **Object ID:** specifies the Object ID.

-   **Instances:** indicates whether this Object supports multiple Object Instances or not. If this field is “Multiple” then the number of Object Instance can be from 0 to many. If this field is “Single” then the number of Object Instance can be from 0 to 1. If the Object field “Mandatory” is “Mandatory” and the Object field “Instances” is “Single” then, the number of Object Instance MUST be 1.

-   **Mandatory:** if this field is “Mandatory”, then the LwM2M Client MUST support this Object. If this field is “Optional”, then the LwM2M Client SHOULD support this Object.

-   **Object URN:** specifies the Object URN. The format of the Object URN is “urn:oma:lwm2m:{oma,ext,x}:{Object ID}\[:{version}\]” and {} part means that those values are variable and filled with real value. For example, Object URN of LwM2M Server Object is “urn:oma:lwm2m:oma:1”. The “version” field, follows the rules specified in Section 6.2 related to Object Versioning Policy.

**Resource definition:**

<table>
<tbody>
<tr class="odd">
<td><strong>ID</strong></td>
<td><strong>Name</strong></td>
<td><strong>Operations</strong></td>
<td><strong>Instances</strong></td>
<td><strong>Mandatory</strong></td>
<td><strong>Type</strong></td>
<td><strong>Range or Enumeration</strong></td>
<td><strong>Units</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td>0</td>
<td>Resource Name</td>
<td>R (Read),<br />
W (Write),<br />
E (Execute)</td>
<td>Multiple/Single</td>
<td>Mandatory/Optional</td>
<td><p>String,</p>
<p>Integer,</p>
<p>Float,</p>
<p>Boolean,</p>
<p>Opaque,</p>
<p>Time,</p>
<p>Objlnk none</p></td>
<td>If any</td>
<td>If any</td>
<td>Description</td>
</tr>
</tbody>
</table>

-   **ID:** specifies the Resource ID which is unique within Object.

-   **Name:** specifies the Resource name.

-   **Operations:** indicates which operations the Resource supports in the “Device Management & Service Enablement” Interface. This field can be set to a combination of R (Read, Observe, Discover, Write-Attributes), and W (Write), or can be set to E (Execute); Executable Operation is exclusive regarding the two others (R, W). This field may also have an empty value, which means that this field is not allowed to be accessed via “Device Management & Service Enablement” Interface but allowed to be accessed via “Bootstrap” Interface.

-   **Instances:** indicates whether this Resource supports multiple Resource Instances or not. If this field is “Multiple” then the number of Resource Instance can be from 0 to many. If this field is “Single” then the number of Resource Instance can be from 0 to 1. If the Resource field “Mandatory” is “Mandatory” and the field “Instances” of the Resource is “Single” then, the number of Resource Instance MUST be 1. Resource which supports “Execute” operation MUST have “Single” as value of the “Instances” field.

-   **Mandatory:** if this field is “Mandatory”, then any Instance of the Object that Resource belongs to, MUST instantiate such a Resource (refer Section 6.1, Resource Model). If this field is “Optional”, then this Resource MAY be omitted from some - or even all - Instances of the Object that Resource belongs to.

-   **Type:** Data Type indicates the type of Resource value. Data Types used in this enabler are described in Appendix C Data Types. Resource which supports “Execute” operation MUST have no associated Data Type (none) encoded as an empty value in Object DDF file.

-   **Range or Enumeration:** this field limits the value of Resource.

-   **Units:** specifies the unit of the Resource value.

-   **Description:** specifies the Resource description.

<span id="_Ref368310666" class="anchor"><span id="_Ref368312910" class="anchor"><span id="_Ref368314129" class="anchor"><span id="_Ref368314148" class="anchor"><span id="_Toc370916126" class="anchor"><span id="_Toc370922948" class="anchor"></span></span></span></span></span></span>In addition to the object and resource definition tables, an object containing Executable Resource(s) is specified in third Table, gathering the definition of the arguments of all the Executable Resources of that Object.

This table provides the properties of arguments

**Executable Resource Arguments Definition **

|        |                   |           |          |            |                   |          |                 |
|--------|-------------------|-----------|----------|------------|-------------------|----------|-----------------|
| **ID** | **Resource Name** | **Order** | **Name** | **Type**   | **Range or Enum** | **Unit** | **Description** |
|        |                   | \[0:9\]   | String   | Data Types | If any            | If any   |                 |

Example of an Executable Resource Arguments Definition Table for an Object having 3 Executable Resource

|                                              |
|----------------------------------------------|
|                                              |
| **Execution Resource Arguments definitions** |
|                                              |
|                                              |
|                                              |
|                                              |
|                                              |

1.  <span id="_Ref434222997" class="anchor"><span id="_Ref434231449" class="anchor"><span id="_Toc492476207" class="anchor"><span id="_Toc493059893" class="anchor"></span></span></span></span>Open Mobile Naming Authority (OMNA) Guidelines

This appendix defines guidelines for OMNA regarding registries and protocol ID ranges to be maintained.

1.  <span id="_Toc370916127" class="anchor"><span id="_Toc370922949" class="anchor"><span id="_Toc492476208" class="anchor"><span id="_Toc493059894" class="anchor"></span></span></span></span>Object Registry

LwM2M Objects must be registered with the OMNA Lightweight Object registry. The rules for Object registry are documented at: <http://www.openmobilealliance.org/wp/OMNA/LwM2M/LwM2MRegistry.html>

The URN format for an Object is automatically built from the class of Object, the Object ID and potentially the Object Version (see Section 6.2 Object Versioning) as follows:

urn:oma:lwm2m:{oma,ext,x}:{Object ID}\[:{version}\].

1.  <span id="_Toc370916128" class="anchor"><span id="_Toc370922950" class="anchor"><span id="_Toc492476209" class="anchor"><span id="_Toc493059895" class="anchor"></span></span></span></span>Resource Registry

LwM2M Objects are specified as being composed of Resources, each identified by a Resource ID. Resources can either be specific to each Object with meaning only when used in that Object, or Reusable Resources can be registered, assigned an ID from the OMNA range and re-used in any Object.

The rules for registering Resource are documented at: <http://www.openmobilealliance.org/wp/OMNA/LwM2M/LwM2MRegistry.html>

1.  <span id="_Ref368263337" class="anchor"><span id="_Ref368263505" class="anchor"><span id="_Toc370916129" class="anchor"><span id="_Toc370922951" class="anchor"><span id="_Toc492476210" class="anchor"><span id="_Toc493059896" class="anchor"></span></span></span></span></span></span>LwM2M Objects defined by OMA (Normative)

This Appendix provides LwM2M Objects defined by OMA. Other organizations and companies may define additional LwM2M according to the guidelines and template provided in Appendix D.

The following LwM2M Objects have been defined by OMA as part of LwM2M 1.0:

| **Object**              | **Object ID** |
|-------------------------|---------------|
| LwM2M Security          | 0             |
| LwM2M Server            | 1             |
| Access Control          | 2             |
| Device                  | 3             |
| Connectivity Monitoring | 4             |
| Firmware                | 5             |
| Location                | 6             |
| Connectivity Statistics | 7             |

<span id="_Toc492475276" class="anchor"></span>Table 28: LwM2M Objects defined by OMA LwM2M 1.0

The LwM2M Server MUST support LwM2M Security, LwM2M Server, and Device Object and SHOULD support Access Control, Device, Connectivity, Firmware Update, Location, and Connectivity Statistics Object.

1.  <span id="_Ref368310888" class="anchor"><span id="_Ref368310920" class="anchor"><span id="_Ref368311151" class="anchor"><span id="_Ref368311227" class="anchor"><span id="_Ref368312925" class="anchor"><span id="_Ref368313241" class="anchor"><span id="_Toc370916130" class="anchor"><span id="_Toc370922952" class="anchor"><span id="_Ref467138086" class="anchor"><span id="_Ref467138087" class="anchor"><span id="_Ref473188295" class="anchor"><span id="_Ref474322455" class="anchor"><span id="_Toc492476211" class="anchor"><span id="_Toc493059897" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span>LwM2M Object: LwM2M Security

<table>
<thead>
<tr class="header">
<th><strong>Description</strong></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>This LwM2M Object provides the keying material of a LwM2M Client appropriate to access a specified LwM2M Server. One Object Instance SHOULD address a LwM2M Bootstrap-Server.<br />
These LwM2M Object Resources MUST only be changed by a LwM2M Bootstrap-Server or Bootstrap from Smartcard and MUST NOT be accessible by any other LwM2M Server.</td>
<td></td>
</tr>
<tr class="even">
<td><strong>Object definition</strong></td>
<td></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>Name</strong></th>
<th><strong>Object ID</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Object URN</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>LwM2M Security</td>
<td>0</td>
<td>Multiple</td>
<td>Mandatory</td>
<td>urn:oma:lwm2m:oma:0</td>
</tr>
</tbody>
</table></td>
<td></td>
</tr>
<tr class="even">
<td><strong>Resource definitions</strong></td>
<td></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>ID</strong></th>
<th><strong>Name</strong></th>
<th><strong>Operations</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Type</strong></th>
<th><strong>Range or Enumeration</strong></th>
<th><strong>Units</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>LwM2M Server URI</td>
<td></td>
<td>Single</td>
<td>Mandatory</td>
<td>String</td>
<td>0-255 bytes</td>
<td></td>
<td>Uniquely identifies the LwM2M Server or LwM2M Bootstrap-Server. The format of the CoAP URI is defined in Section 6 of RFC 7252.</td>
</tr>
<tr class="even">
<td>1</td>
<td>Bootstrap-Server</td>
<td></td>
<td>Single</td>
<td>Mandatory</td>
<td>Boolean</td>
<td></td>
<td></td>
<td>Determines if the current instance concerns a LwM2M Bootstrap-Server (true) or a standard LwM2M Server (false)</td>
</tr>
<tr class="odd">
<td>2</td>
<td>Security Mode</td>
<td></td>
<td>Single</td>
<td>Mandatory</td>
<td>Integer</td>
<td>0-4</td>
<td></td>
<td>Determines which UDP payload security mode is used<br />
0: Pre-Shared Key mode<br />
1: Raw Public Key mode<br />
2: Certificate mode<br />
3: NoSec mode<br />
4: Certificate mode with EST</td>
</tr>
<tr class="even">
<td>3</td>
<td>Public Key or Identity</td>
<td></td>
<td>Single</td>
<td>Mandatory</td>
<td>Opaque</td>
<td></td>
<td></td>
<td>Stores the LwM2M Client’s Certificate (Certificate mode), public key (RPK mode) or PSK Identity (PSK mode). The format is defined in Section E.1.1.</td>
</tr>
<tr class="odd">
<td>4</td>
<td>Server Public Key</td>
<td></td>
<td>Single</td>
<td>Mandatory</td>
<td>Opaque</td>
<td></td>
<td></td>
<td>Stores the LwM2M Server’s or LwM2M Bootstrap-Server’s Certificate (Certificate mode), public key (RPK mode). The format is defined in Section E.1.1.</td>
</tr>
<tr class="even">
<td>5</td>
<td>Secret Key</td>
<td></td>
<td>Single</td>
<td>Mandatory</td>
<td>Opaque</td>
<td></td>
<td></td>
<td>Stores the secret key or private key of the security mode. The format of the keying material is defined by the security mode in Section E.1.1. This Resource MUST only be changed by a bootstrap-server and MUST NOT be readable by any server.</td>
</tr>
<tr class="odd">
<td>6</td>
<td>SMS Security Mode</td>
<td></td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td>0-255</td>
<td></td>
<td>Determines which SMS security mode is used (see section 7.2)<br />
0: Reserved for future use<br />
1: DTLS mode (Device terminated) PSK mode assumed<br />
2: Secure Packet Structure mode (Smartcard terminated)<br />
3: NoSec mode<br />
4: Reserved mode (DTLS mode with multiplexing Security Association support)<br />
5-203 : Reserved for future use<br />
204-255: Proprietary modes</td>
</tr>
<tr class="even">
<td>7</td>
<td>SMS Binding Key Parameters</td>
<td></td>
<td>Single</td>
<td>Optional</td>
<td>Opaque</td>
<td>6 bytes</td>
<td></td>
<td>Stores the KIc, KID, SPI and TAR. The format is defined in Section E.1.2.</td>
</tr>
<tr class="odd">
<td>8</td>
<td>SMS Binding Secret Key(s)</td>
<td></td>
<td>Single</td>
<td>Optional</td>
<td>Opaque</td>
<td>16-32-48 bytes</td>
<td></td>
<td><p>Stores the values of the key(s) for the SMS binding.</p>
<p>This resource MUST only be changed by a bootstrap-server and MUST NOT be readable by any server.</p></td>
</tr>
<tr class="even">
<td>9</td>
<td>LwM2M Server SMS Number</td>
<td></td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td><p>MSISDN used by the LwM2M Client to send messages to the LwM2M Server via the SMS binding.</p>
<p>The LwM2M Client SHALL silently ignore any SMS originated from unknown MSISDN</p></td>
</tr>
<tr class="odd">
<td>10</td>
<td>Short Server ID</td>
<td></td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td>1-65534</td>
<td></td>
<td>This identifier uniquely identifies each LwM2M Server configured for the LwM2M Client.<br />
This Resource MUST be set when the Bootstrap-Server Resource has false value.<br />
Specific ID:0 and ID:65535 values MUST NOT be used for identifying the LwM2M Server (Section 6.3).</td>
</tr>
<tr class="even">
<td>11</td>
<td>Client Hold Off Time</td>
<td></td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td>s</td>
<td><p>Relevant information for a Bootstrap-Server only.<br />
The number of seconds to wait before initiating a Client Initiated Bootstrap once the LwM2M Client has determined it should initiate this bootstrap mode.</p>
<p>In case client initiated bootstrap is supported by the LwM2M Client, this resource MUST be supported.</p></td>
</tr>
<tr class="odd">
<td>12</td>
<td>Bootstrap-Server Account Timeout</td>
<td></td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td>s</td>
<td><p>The LwM2M Client MUST purge the LwM2M Bootstrap-Server Account after the timeout value given by this resource. The lowest timeout value is 1.</p>
<p>If the value is set to 0, or if this resource is not instantiated, the Bootstrap-Server Account lifetime is infinite.</p></td>
</tr>
</tbody>
</table></td>
<td><table>
<tbody>
<tr class="odd">
<td></td>
</tr>
</tbody>
</table></td>
</tr>
<tr class="even">
<td><ol style="list-style-type: upper-alpha">
<li><p><span id="_Ref373937639" class="anchor"><span id="_Toc492476212" class="anchor"><span id="_Toc493059898" class="anchor"></span></span></span>UDP Channel Security: Security Key Resource Format</p></li>
</ol>
<p>This section defines the format of the Secret Key and Public Key and Identity Resources of the LwM2M Server and LwM2M Bootstrap-Server Objects when using UDP Channel security. These Resources are used to configure the security mode and keying material that a Client uses with a particular Server. The Objects are configured on the Client using one of the Bootstrap mechanisms described in Section 5.1. The use of this keying material for each security mode is defined in Section 7.1.</p>
<ol style="list-style-type: upper-alpha">
<li><p>Pre-Shared Key (PSK) Mode</p></li>
</ol>
<p>The PSK is a binary shared secret key between the Client and Server of the appropriate length for the Cipher Suite used [RFC4279]. This key is composed of a sequence of binary bytes in the Secret Key Resource. The default PSK Cipher Suites defined in this specification use a 128-bit AES key. Since the security of the default PSK Cipher Suites rely on the length and the entropy of this shared secret it is RECOMMENDED to provision a 16 byte (128 bit) key or longer in the Secret Key Resource. Recommendations for generating random keys are provided in RFC 4086 [RFC4086].<br />
The corresponding PSK Identity for this PSK is stored in the Public Key or Identity Resource. The PSK Identity is simply stored as a UTF-8 String as per [RFC4279]. Clients and Servers MUST support arbitrary PSK Identities of up to 128 bytes and PSK keys of up to 64 bytes in length as required by [RFC4279].</p>
<ol style="list-style-type: upper-alpha">
<li><p>Raw-Public Key (RPK) Mode</p></li>
</ol>
<p>The raw-public key mode requires a public key and a private key of the appropriate type and length for the cipher suite used. These keys are carried as a sequence of binary bytes with the public key stored in the Public Key or Identity Resource, and the private key stored in the Secret Key Resource. The public key MUST be encoded using the SubjectPublicKeyInfo structure, as described in [RFC7250].</p>
<p>The private key is encoded as defined in [RFC5958].</p>
<ol style="list-style-type: upper-alpha">
<li><p>Certificate Mode</p></li>
</ol>
<p>The Certificate mode requires an X.509v3 Certificate along with a matching private key. The private key is stored in the Secret Key Resource, encoded using [RFC5958], as the private key in the RPK mode. The certificate in a DER encoded binary format, as defined in [RFC5280], is stored in the Public Key or Identity Resource.</p>
<ol style="list-style-type: upper-alpha">
<li><p><span id="_Ref403055843" class="anchor"><span id="_Toc492476213" class="anchor"><span id="_Toc493059899" class="anchor"></span></span></span>SMS Payload Security: Security Key Resource Format</p></li>
</ol>
<p>This section defines the format of the Secret Key and Public Key and Identity resources of the LwM2M Server and LwM2M Bootstrap Objects when using SMS Payload security. These resources are used to configure keying material that a Client uses with a particular Server. The Objects are configured on the Client using one of the Bootstrap mechanisms described in Section 5.1. The use of this keying material is defined in Section 7.2.</p>
<p>The SMS key parameters are stored in the order KIc, KID, SPI, TAR (KIc is byte 0).</p>
<p>Ordering of bits within bytes SHALL follow ETSI TS 102 221, section 3.4 “Coding Conventions” (b8 MSB, b1 LSB).</p>
<ol style="list-style-type: upper-alpha">
<li><p><span id="_Toc492476214" class="anchor"><span id="_Toc493059900" class="anchor"></span></span>Unbootstrapping</p></li>
</ol>
<p>Unbootstrapping is the process of deleting a Security Object Instance. If a Security Object Instance is to be deleted, certain related resources and configurations need to be deleted or modified. Therefore, when the Delete operation is sent via the Bootstrap Interface, the Client MUST execute the following procedure.</p>
<ol style="list-style-type: decimal">
<li><blockquote>
<p>If there is an Object Instance that can be accessed only by a Server of the Server Object Instance (i.e., the Server is Access Control Owner and the LwM2M Server can access the Object Instance only in an Access Control Object Instance), the Object Instance and the corresponding Access Control Object Instance MUST be deleted</p>
</blockquote></li>
<li><blockquote>
<p>If an Object Instance can be accessed by multiple Servers including the Server which Security Object Instance is to be deleted, then:</p>
</blockquote>
<ul>
<li><blockquote>
<p>The ACL Resource Instance for the Server in the Access Control Object Instance for the Object Instance MUST be deleted</p>
</blockquote></li>
<li><blockquote>
<p>If the Server is the Access Control Owner of the Access Control Object Instance, then the Access Control Owner MUST be changed to another Server according to the rules below:<br />
The Client MUST choose the Server who has highest sum of each number assigned to an access right (Write: 1, Delete: 1) for the Access Control Owner. If two or more Servers have the same sum, the Client MUST choose one of them as the new Access Control Owner</p>
</blockquote></li>
</ul></li>
<li><blockquote>
<p>Observation operations from the Server MUST be deleted</p>
</blockquote></li>
<li><blockquote>
<p>Server Object Instance MUST be deleted</p>
</blockquote></li>
<li><blockquote>
<p>Client MAY send “De-register” operation to the Server</p>
</blockquote></li>
</ol>
<p>Note: To monitor the change of the Access Control Owner, the Server MAY observe Access Control Owner Resource.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><span id="_Ref368312933" class="anchor"><span id="_Ref368313249" class="anchor"></span></span></td>
<td></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc370916138" class="anchor"><span id="_Toc370922960" class="anchor"><span id="_Ref373937432" class="anchor"><span id="_Ref373937562" class="anchor"><span id="_Ref435446006" class="anchor"><span id="_Toc492476215" class="anchor"><span id="_Toc493059901" class="anchor"></span></span></span></span></span></span></span>LwM2M Object: LwM2M Server

<table>
<thead>
<tr class="header">
<th><table>
<thead>
<tr class="header">
<th><span id="_Toc370916139" class="anchor"><span id="_Toc370922961" class="anchor"></span></span><strong>Description</strong></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>This LwM2M Objects provides the data related to a LwM2M Server. A Bootstrap-Server has no such an Object Instance associated to it.</td>
<td></td>
</tr>
<tr class="even">
<td><strong>Object definition</strong></td>
<td></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>Name</strong></th>
<th><strong>Object ID</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Object URN</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>LwM2M Server</td>
<td>1</td>
<td>Multiple</td>
<td>Mandatory</td>
<td>urn:oma:lwm2m:oma:1</td>
</tr>
</tbody>
</table></td>
<td></td>
</tr>
<tr class="even">
<td><strong>Resource definitions</strong></td>
<td></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>ID</strong></th>
<th><strong>Name</strong></th>
<th><strong>Operations</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Type</strong></th>
<th><strong>Range or Enumeration</strong></th>
<th><strong>Units</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>Short Server ID</td>
<td>R</td>
<td>Single</td>
<td>Mandatory</td>
<td>Integer</td>
<td>1-65535</td>
<td></td>
<td>Used as link to associate server Object Instance.</td>
</tr>
<tr class="even">
<td>1</td>
<td>Lifetime</td>
<td>RW</td>
<td>Single</td>
<td>Mandatory</td>
<td>Integer</td>
<td></td>
<td>s</td>
<td>Specify the lifetime of the registration in seconds (see Section 5.3 Registration)</td>
</tr>
<tr class="odd">
<td>2</td>
<td>Default Minimum Period</td>
<td>RW</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td>s</td>
<td>The default value the LwM2M Client should use for the Minimum Period of an Observation in the absence of this parameter being included in an Observation.<br />
If this Resource doesn’t exist, the default value is 0.</td>
</tr>
<tr class="even">
<td>3</td>
<td>Default Maximum Period</td>
<td>RW</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td>s</td>
<td>The default value the LwM2M Client should use for the Maximum Period of an Observation in the absence of this parameter being included in an Observation.</td>
</tr>
<tr class="odd">
<td>4</td>
<td>Disable</td>
<td>E</td>
<td>Single</td>
<td>Optional</td>
<td></td>
<td></td>
<td></td>
<td>If this Resource is executed, this LwM2M Server Object is disabled for a certain period defined in the Disabled Timeout Resource. After receiving “Execute” operation, LwM2M Client MUST send response of the operation and perform de-registration process, and underlying network connection between the Client and Server MUST be disconnected to disable the LwM2M Server account.<br />
After the above process, the LwM2M Client MUST NOT send any message to the Server and ignore all the messages from the LwM2M Server for the period.</td>
</tr>
<tr class="even">
<td>5</td>
<td>Disable Timeout</td>
<td>RW</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td>s</td>
<td>A period to disable the Server. After this period, the LwM2M Client MUST perform registration process to the Server. If this Resource is not set, a default timeout value is 86400 (1 day).</td>
</tr>
<tr class="odd">
<td>6</td>
<td>Notification Storing When Disabled or Offline</td>
<td>RW</td>
<td>Single</td>
<td>Mandatory</td>
<td>Boolean</td>
<td></td>
<td></td>
<td>If true, the LwM2M Client stores “Notify” operations to the LwM2M Server while the LwM2M Server account is disabled or the LwM2M Client is offline. After the LwM2M Server account is enabled or the LwM2M Client is online, the LwM2M Client reports the stored “Notify” operations to the Server.<br />
If false, the LwM2M Client discards all the “Notify” operations or temporarily disables the Observe function while the LwM2M Server is disabled or the LwM2M Client is offline.<br />
The default value is true.<br />
The maximum number of storing Notifications per Server is up to the implementation.</td>
</tr>
<tr class="even">
<td>7</td>
<td>Binding</td>
<td>RW</td>
<td>Single</td>
<td>Mandatory</td>
<td>String</td>
<td>The possible values of Resource are listed in 5.3.1.1</td>
<td></td>
<td>This Resource defines the transport binding configured for the LwM2M Client.<br />
If the LwM2M Client supports the binding specified in this Resource, the LwM2M Client MUST use that transport for the Current Binding Mode.</td>
</tr>
<tr class="odd">
<td>8</td>
<td>Registration Update Trigger</td>
<td>E</td>
<td>Single</td>
<td>Mandatory</td>
<td></td>
<td></td>
<td></td>
<td>If this Resource is executed the LwM2M Client MUST perform an “Update” operation with this LwM2M Server using that transport for the Current Binding Mode.</td>
</tr>
</tbody>
</table></td>
<td></td>
</tr>
</tbody>
</table></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>

1.  <span id="_Ref368311870" class="anchor"><span id="_Ref368312937" class="anchor"><span id="_Ref368313253" class="anchor"><span id="_Toc370916142" class="anchor"><span id="_Toc370922964" class="anchor"><span id="_Toc492476216" class="anchor"><span id="_Toc493059902" class="anchor"></span></span></span></span></span></span></span>LwM2M Object: Access Control

<table>
<thead>
<tr class="header">
<th><strong>Description</strong></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Access Control Object is used to check whether the LwM2M Server has access right for performing an operation.</td>
<td></td>
</tr>
<tr class="even">
<td><strong>Object definition</strong></td>
<td></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>Name</strong></th>
<th><strong>Object ID</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Object URN</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>LwM2M Access Control</td>
<td>2</td>
<td>Multiple</td>
<td>Optional</td>
<td>urn:oma:lwm2m:oma:2</td>
</tr>
</tbody>
</table></td>
<td></td>
</tr>
<tr class="even">
<td><strong>Resource definitions</strong></td>
<td></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>ID</strong></th>
<th><strong>Name</strong></th>
<th><strong>Operations</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Type</strong></th>
<th><strong>Range or Enumeration</strong></th>
<th><strong>Units</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>Object ID</td>
<td>R</td>
<td>Single</td>
<td>Mandatory</td>
<td>Integer</td>
<td>1-65534</td>
<td></td>
<td>Resources 0 and 1 point to the Object Instance for which the Instances of the ACL Resource of that Access Control Object Instance are applicable.</td>
</tr>
<tr class="even">
<td>1</td>
<td>Object Instance ID</td>
<td>R</td>
<td>Single</td>
<td>Mandatory</td>
<td>Integer</td>
<td>0-65535</td>
<td></td>
<td>See above</td>
</tr>
<tr class="odd">
<td>2</td>
<td>ACL</td>
<td>RW</td>
<td>Multiple</td>
<td>Optional</td>
<td>Integer</td>
<td>16-bit</td>
<td></td>
<td>The Resource Instance ID MUST be the Short Server ID of a certain LwM2M Server for which associated access rights are contained in the Resource Instance value.<br />
The Resource Instance ID 0 is a specific ID, determining the ACL Instance which contains the default access rights.<br />
Each bit set in the Resource Instance value, grants an access right to the LwM2M Server to the corresponding operation.<br />
The bit order is specified as below.<br />
1st LSB: R(Read, Observe, Write-Attributes)<br />
2nd LSB: W(Write)<br />
3rd LSB: E(Execute)<br />
4th LSB: D(Delete)<br />
5th LSB: C(Create)<br />
Other bits are reserved for future use.</td>
</tr>
<tr class="even">
<td>3</td>
<td>Access Control Owner</td>
<td>RW</td>
<td>Single</td>
<td>Mandatory</td>
<td>Integer</td>
<td>0-65535</td>
<td></td>
<td><p>Short Server ID of a certain LwM2M Server; only such an LwM2M Server can manage the Resources of this Object Instance.</p>
<p>The specific value MAX_ID=65535 means this Access Control Object Instance is created and modified during a Bootstrap phase only.</p></td>
</tr>
</tbody>
</table></td>
<td><table>
<tbody>
<tr class="odd">
<td></td>
</tr>
</tbody>
</table></td>
</tr>
<tr class="even">
<td><span id="_Toc361854649" class="anchor"><span id="_Toc361855373" class="anchor"><span id="_Ref368312414" class="anchor"><span id="_Ref368312942" class="anchor"><span id="_Ref368313257" class="anchor"></span></span></span></span></span></td>
<td></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc370916148" class="anchor"><span id="_Toc370922970" class="anchor"><span id="_Ref373937195" class="anchor"><span id="_Ref373937448" class="anchor"><span id="_Ref373937576" class="anchor"></span></span></span></span></span>

2.  <span id="_Ref436812219" class="anchor"><span id="_Ref436813581" class="anchor"><span id="_Toc492476217" class="anchor"><span id="_Toc493059903" class="anchor"></span></span></span></span>LwM2M Object: Device

<table>
<thead>
<tr class="header">
<th><table>
<thead>
<tr class="header">
<th><table>
<thead>
<tr class="header">
<th><span id="_Toc370916149" class="anchor"><span id="_Toc370922971" class="anchor"></span></span><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>This LwM2M Object provides a range of device related information which can be queried by the LwM2M Server, and a device reboot and factory reset function.</td>
</tr>
<tr class="even">
<td><strong>Object definition</strong></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>Name</strong></th>
<th><strong>Object ID</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Object URN</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Device</td>
<td>3</td>
<td>Single</td>
<td>Mandatory</td>
<td>urn:oma:lwm2m:oma:3</td>
</tr>
</tbody>
</table></td>
</tr>
<tr class="even">
<td><strong>Resource definitions</strong></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>ID</strong></th>
<th><strong>Name</strong></th>
<th><strong>Operations</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Type</strong></th>
<th><strong>Range or Enumeration</strong></th>
<th><strong>Units</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>Manufacturer</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td>Human readable manufacturer name</td>
</tr>
<tr class="even">
<td>1</td>
<td>Model Number</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td>A model identifier (manufacturer specified string)</td>
</tr>
<tr class="odd">
<td>2</td>
<td>Serial Number</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td>Serial Number</td>
</tr>
<tr class="even">
<td>3</td>
<td>Firmware Version</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td>Current firmware version of the Device. The Firmware Management function could rely on this resource.</td>
</tr>
<tr class="odd">
<td>4</td>
<td>Reboot</td>
<td>E</td>
<td>Single</td>
<td>Mandatory</td>
<td></td>
<td></td>
<td></td>
<td>Reboot the LwM2M Device to restore the Device from unexpected firmware failure.</td>
</tr>
<tr class="even">
<td>5</td>
<td>Factory Reset</td>
<td>E</td>
<td>Single</td>
<td>Optional</td>
<td></td>
<td></td>
<td></td>
<td>Perform factory reset of the LwM2M Device to make the LwM2M Device to go through initial deployment sequence where provisioning and bootstrap sequence is performed. This requires client ensuring post factory reset to have minimal information to allow it to carry out one of the bootstrap methods specified in section 5.2.3.<br />
When this Resource is executed, “De-register” operation MAY be sent to the LwM2M Server(s) before factory reset of the LwM2M Device.</td>
</tr>
<tr class="odd">
<td>6</td>
<td>Available Power Sources</td>
<td>R</td>
<td>Multiple</td>
<td>Optional</td>
<td>Integer</td>
<td>0-7</td>
<td></td>
<td>0 – DC power<br />
1 – Internal Battery<br />
2 – External Battery<br />
4 – Power over Ethernet<br />
5 – USB<br />
6 – AC (Mains) power<br />
7 – Solar<br />
<br />
The same Resource Instance ID MUST be used to associate a given Power Source (Resource ID:6) with its Present Voltage (Resource ID:7) and its Present Current (Resource ID:8)</td>
</tr>
<tr class="even">
<td>7</td>
<td>Power Source Voltage</td>
<td>R</td>
<td>Multiple</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td>mV</td>
<td>Present voltage for each Available Power Sources Resource Instance.</td>
</tr>
<tr class="odd">
<td>8</td>
<td>Power Source Current</td>
<td>R</td>
<td>Multiple</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td>mA</td>
<td>Present current for each Available Power Source.</td>
</tr>
<tr class="even">
<td>9</td>
<td>Battery Level</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td>0-100</td>
<td>%</td>
<td>Contains the current battery level as a percentage (with a range from 0 to 100). This value is only valid for the Device Internal Battery if present (one Available Power Sources Resource Instance is 1).</td>
</tr>
<tr class="odd">
<td>10</td>
<td>Memory Free</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td>KB</td>
<td>Estimated current available amount of storage space which can store data and software in the LwM2M Device (expressed in kilobytes).</td>
</tr>
<tr class="even">
<td>11</td>
<td>Error Code</td>
<td>R</td>
<td>Multiple</td>
<td>Mandatory</td>
<td>Integer</td>
<td>0-8</td>
<td></td>
<td>0=No error<br />
1=Low battery power<br />
2=External power supply off<br />
3=GPS module failure<br />
4=Low received signal strength<br />
5=Out of memory<br />
6=SMS failure<br />
7=IP connectivity failure<br />
8=Peripheral malfunction<br />
<br />
When the single Device Object Instance is initiated, there is only one error code Resource Instance whose value is equal to 0 that means no error. When the first error happens, the LwM2M Client changes error code Resource Instance to any non-zero value to indicate the error type. When any other error happens, a new error code Resource Instance is created. When an error associated with a Resource Instance is no longer present, that Resource Instance is deleted. When the single existing error is no longer present, the LwM2M Client returns to the original no error state where Instance 0 has value 0.<br />
This error code Resource MAY be observed by the LwM2M Server. How to deal with LwM2M Client’s error report depends on the policy of the LwM2M Server.</td>
</tr>
<tr class="odd">
<td>12</td>
<td>Reset Error Code</td>
<td>E</td>
<td>Single</td>
<td>Optional</td>
<td></td>
<td></td>
<td></td>
<td>Delete all error code Resource Instances and create only one zero-value error code that implies no error, then re-evaluate all error conditions and update and create Resources Instances to capture all current error conditions.</td>
</tr>
<tr class="even">
<td>13</td>
<td>Current Time</td>
<td>RW</td>
<td>Single</td>
<td>Optional</td>
<td>Time</td>
<td></td>
<td></td>
<td>Current UNIX time of the LwM2M Client.<br />
The LwM2M Client should be responsible to increase this time value as every second elapses.<br />
The LwM2M Server is able to write this Resource to make the LwM2M Client synchronized with the LwM2M Server.</td>
</tr>
<tr class="odd">
<td>14</td>
<td>UTC Offset</td>
<td>RW</td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td>Indicates the UTC offset currently in effect for this LwM2M Device. UTC+X [ISO 8601].</td>
</tr>
<tr class="even">
<td>15</td>
<td>Timezone</td>
<td>RW</td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td>Indicates in which time zone the LwM2M Device is located, in IANA Timezone (TZ) database format.</td>
</tr>
<tr class="odd">
<td>16</td>
<td>Supported Binding and Modes</td>
<td>R</td>
<td>Single</td>
<td>Mandatory</td>
<td>String</td>
<td></td>
<td></td>
<td>Indicates which bindings and modes are supported in the LwM2M Client. The possible values of Resource are combination of &quot;U&quot; or &quot;UQ&quot; and &quot;S&quot; or &quot;SQ&quot;.</td>
</tr>
<tr class="even">
<td>17</td>
<td>Device Type</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td>Type of the device (manufacturer specified string: e.g., smart meters / dev Class…)</td>
</tr>
<tr class="odd">
<td>18</td>
<td>Hardware Version</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td>Current hardware version of the device</td>
</tr>
<tr class="even">
<td>19</td>
<td>Software Version</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td>Current software version of the device (manufacturer specified string). On elaborated LwM2M device, SW could be split in 2 parts: a firmware one and a higher level software on top.<br />
Both pieces of Software are together managed by LwM2M Firmware Update Object (Object ID 5)</td>
</tr>
<tr class="odd">
<td>20</td>
<td>Battery Status</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td>0-6</td>
<td></td>
<td><p>This value is only valid for the Device Internal Battery if present (one Available Power Sources Resource Instance value is 1).</p>
<table>
<thead>
<tr class="header">
<th><p><strong>Battery</strong></p>
<p><strong>Status</strong></p></th>
<th><strong>Meaning</strong></th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>Normal</td>
<td>The battery is operating normally and not on power.</td>
</tr>
<tr class="even">
<td>1</td>
<td>Charging</td>
<td>The battery is currently charging.</td>
</tr>
<tr class="odd">
<td>2</td>
<td>Charge Complete</td>
<td>The battery is fully charged and still on power.</td>
</tr>
<tr class="even">
<td>3</td>
<td>Damaged</td>
<td>The battery has some problem.</td>
</tr>
<tr class="odd">
<td>4</td>
<td>Low Battery</td>
<td>The battery is low on charge.</td>
</tr>
<tr class="even">
<td>5</td>
<td>Not Installed</td>
<td>The battery is not installed.</td>
</tr>
<tr class="odd">
<td>6</td>
<td>Unknown</td>
<td>The battery information is not available.</td>
</tr>
</tbody>
</table></td>
</tr>
<tr class="even">
<td>21</td>
<td>Memory Total</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td></td>
<td>Total amount of storage space which can store data and software in the LwM2M Device (expressed in kilobytes).</td>
</tr>
<tr class="odd">
<td>22</td>
<td>ExtDevInfo</td>
<td>R</td>
<td>Multiple</td>
<td>Optional</td>
<td>Objlnk</td>
<td></td>
<td></td>
<td>Reference to external “Device” object instance containing information. For example, such an external device can be a Host Device, which is a device into which the Device containing the LwM2M client is embedded. This Resource may be used to retrieve information about the Host Device.</td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>

1.  <span id="_Ref368312946" class="anchor"><span id="_Ref368313264" class="anchor"><span id="_Toc370916152" class="anchor"><span id="_Toc370922974" class="anchor"></span></span></span></span>

2.  <span id="_Ref436812230" class="anchor"><span id="_Ref436813591" class="anchor"><span id="_Toc492476218" class="anchor"><span id="_Toc493059904" class="anchor"></span></span></span></span>LwM2M Object: Connectivity Monitoring

<table>
<thead>
<tr class="header">
<th><table>
<thead>
<tr class="header">
<th><span id="_Toc370916153" class="anchor"><span id="_Toc370922975" class="anchor"></span></span><strong>Description</strong></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>This LwM2M Object enables monitoring of parameters related to network connectivity.<br />
In this general connectivity Object, the Resources are limited to the most general cases common to most network bearers. It is recommended to read the description, which refers to relevant standard development organizations (e.g., 3GPP, IEEE).<br />
The goal of the Connectivity Monitoring Object is to carry information reflecting the more up to date values of the current connection for monitoring purposes. Resources such as Link Quality, Radio Signal Strength, Cell ID are retrieved during connected mode at least for cellular networks.</td>
<td></td>
</tr>
<tr class="even">
<td><strong>Object definition</strong></td>
<td></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>Name</strong></th>
<th><strong>Object ID</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Object URN</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Connectivity Monitoring</td>
<td>4</td>
<td>Single</td>
<td>Optional</td>
<td>urn:oma:lwm2m:oma:4</td>
</tr>
</tbody>
</table></td>
<td></td>
</tr>
<tr class="even">
<td><strong>Resource definitions</strong></td>
<td></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>ID</strong></th>
<th><strong>Name</strong></th>
<th><strong>Operations</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Type</strong></th>
<th><strong>Range or Enumeration</strong></th>
<th><strong>Units</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>Network Bearer</td>
<td>R</td>
<td>Single</td>
<td>Mandatory</td>
<td>Integer</td>
<td></td>
<td></td>
<td>Indicates the network bearer used for the current LwM2M communication session from the below network bearer list.<br />
0~20 are Cellular Bearers<br />
0: GSM cellular network<br />
1: TD-SCDMA cellular network<br />
2: WCDMA cellular network<br />
3: CDMA2000 cellular network<br />
4: WiMAX cellular network<br />
5: LTE-TDD cellular network<br />
6: LTE-FDD cellular network<br />
7: NB-IoT<br />
8~20: Reserved for other type cellular network<br />
21~40 are Wireless Bearers<br />
21: WLAN network<br />
22: Bluetooth network<br />
23: IEEE 802.15.4 network<br />
24~40: Reserved for other type local wireless network<br />
41~50 are Wireline Bearers<br />
41: Ethernet<br />
42: DSL<br />
43: PLC<br />
44~50: reserved for others type wireline networks.</td>
</tr>
<tr class="even">
<td>1</td>
<td>Available Network Bearer</td>
<td>R</td>
<td>Multiple</td>
<td>Mandatory</td>
<td>Integer</td>
<td></td>
<td></td>
<td>Indicates list of current available network bearer. Each Resource Instance has a value from the network bearer list.</td>
</tr>
<tr class="odd">
<td>2</td>
<td>Radio Signal Strength</td>
<td>R</td>
<td>Single</td>
<td>Mandatory</td>
<td>Integer</td>
<td></td>
<td>dBm</td>
<td><p>This node contains the average value of the received signal strength indication used in the current network bearer (as indicated by Resource 0 of this Object).</p>
<p>For the following network bearers the signal strength parameters indicated below are represented by this resource:<br />
GSM: RSSI<br />
UMTS: RSCP<br />
LTE: RSRP<br />
NB-IoT: NRSRP</p>
<p>For the following network bearers the signal strength parameters indicated below are represented by this resource:<br />
GSM: RSSI<br />
UMTS: RSCP<br />
LTE: RSRP</p>
<p>For more details on Network Measurement Report, refer to the appropriate Cellular or Wireless Network standards. (e.g., for LTE Cellular Network refer to ETSI TS 36.133 specification).</p></td>
</tr>
<tr class="even">
<td>3</td>
<td>Link Quality</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td></td>
<td>This contains received link quality e.g.<br />
LQI for IEEE 802.15.4 (range 0..255), RxQual Downlink for GSM (range 0…7, refer to [3GPP 44.018] for more details on Network Measurement Report encoding),<br />
RSRQ for LTE, (refer to [3GPP 36.214]),<br />
NRSRQ for NB-IoT (refer to [3GPP 36.214]).</td>
</tr>
<tr class="odd">
<td>4</td>
<td>IP Addresses</td>
<td>R</td>
<td>Multiple</td>
<td>Mandatory</td>
<td>String</td>
<td></td>
<td></td>
<td>The IP addresses assigned to the connectivity interface. (e.g., IPv4, IPv6, etc.)</td>
</tr>
<tr class="even">
<td>5</td>
<td>Router IP Addresses</td>
<td>R</td>
<td>Multiple</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td>The IP address of the next-hop IP router, on each of the interfaces specified in resource 4 (IP Addresses)<br />
Note: This IP Address doesn’t indicate the Server IP address.</td>
</tr>
<tr class="odd">
<td>6</td>
<td>Link Utilization</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td>0-100</td>
<td>%</td>
<td>The average utilization of the link to the next-hop IP router in %.</td>
</tr>
<tr class="even">
<td>7</td>
<td>APN</td>
<td>R</td>
<td>Multiple</td>
<td>Optional</td>
<td>String</td>
<td></td>
<td></td>
<td>Access Point Name in case Network Bearer Resource is a Cellular Network.</td>
</tr>
<tr class="odd">
<td>8</td>
<td>Cell ID</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td></td>
<td>Serving Cell ID in case Network Bearer Resource is a Cellular Network.<br />
As specified in TS [3GPP_TS_23.003] and in [3GPP_TS_24.008]. Range (0…65535) in GSM/EDGE<br />
UTRAN Cell ID has a length of 28 bits.<br />
Cell Identity in WCDMA/TD-SCDMA. Range: (0..268435455).<br />
LTE Cell ID has a length of 28 bits.<br />
Parameter definitions in [3GPP_TS_25.331].</td>
</tr>
<tr class="even">
<td>9</td>
<td>SMNC</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td></td>
<td>Serving Mobile Network Code. In case Network Bearer Resource has 0(cellular network). Range (0…999).<br />
As specified in TS [3GPP_TS_23.003].</td>
</tr>
<tr class="odd">
<td>10</td>
<td>SMCC</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td></td>
<td>Serving Mobile Country Code. In case Network Bearer Resource has 0 (cellular network). Range (0…999).<br />
As specified in TS [3GPP_TS_23.003].</td>
</tr>
</tbody>
</table></td>
<td></td>
</tr>
</tbody>
</table></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc361854653" class="anchor"><span id="_Toc361855377" class="anchor"><span id="_Toc361854654" class="anchor"><span id="_Toc361855378" class="anchor"><span id="_Toc361854655" class="anchor"><span id="_Toc361855379" class="anchor"><span id="_Ref368312952" class="anchor"><span id="_Ref368313270" class="anchor"><span id="_Toc370916156" class="anchor"><span id="_Toc370922978" class="anchor"><span id="_Toc492476219" class="anchor"><span id="_Toc493059905" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span>LwM2M Object: Firmware Update

<table>
<thead>
<tr class="header">
<th><table>
<thead>
<tr class="header">
<th><span id="_Toc370916157" class="anchor"><span id="_Toc370922979" class="anchor"></span></span><strong>Description</strong></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>This LwM2M Object enables management of firmware which is to be updated. This Object includes installing firmware package, updating firmware, and performing actions after updating firmware. The firmware update MAY require to reboot the device; it will depend on a number of factors, such as the operating system architecture and the extent of the updated software.</p>
<p>The envisioned functionality with LwM2M version 1.0 is to allow a LwM2M Client to connect to any LwM2M version 1.0 compliant Server to obtain a firmware image using the object and resource structure defined in this section experiencing communication security protection using DTLS. There are, however, other design decisions that need to be taken into account to allow a manufacturer of a device to securely install firmware on a device. Examples for such design decisions are how to manage the firmware update repository at the server side (which may include user interface considerations), the techniques to provide additional application layer security protection of the firmware image, how many versions of firmware image to store on the device, and how to execute the firmware update process considering the hardware specific details of a given IoT hardware product. These aspects are considered to be outside the scope of the LwM2M version 1.0 specification.</p>
<p>A LwM2M Server may also instruct a LwM2M Client to fetch a firmware image from a dedicated server (instead of pushing firmware image to the LwM2M Client). The Package URI resource is contained in the Firmware object and can be used for this purpose.</p>
<p>A LwM2M Client MUST support block-wise transfer [CoAP_Blockwise] if it implements the Firmware Update object.</p>
<p>A LwM2M Server MUST support block-wise transfer. Other protocols, such as HTTP/HTTPs, MAY also be used for downloading firmware updates (via the Package URI resource). For constrained devices it is, however, RECOMMENDED to use CoAP for firmware downloads to avoid the need for additional protocol implementations.</p>
<p>Once a new firmware image is successfully installed in the Device, if the Resource “Firmware Version” ID:3 is available in the Instance of the Device Object (ID:3) the LwM2M Client MUST update such a Resource accordingly to the new firmware image version.</p>
<p>Note : PkgName (ID:6) and PkgVersion (ID:7) Resources contain optional information handled by the Firmware Update functionality for its own purpose and have no direct correlation with the “Firmware Version” ID:3 of Device Object ID:3.</p></td>
<td></td>
</tr>
<tr class="even">
<td><strong>Object definition</strong></td>
<td></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>Name</strong></th>
<th><strong>Object ID</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Object URN</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Firmware Update</td>
<td>5</td>
<td>Single</td>
<td>Optional</td>
<td>urn:oma:lwm2m:oma:5</td>
</tr>
</tbody>
</table></td>
<td></td>
</tr>
<tr class="even">
<td><strong>Resource definitions</strong></td>
<td></td>
</tr>
<tr class="odd">
<td><table>
<thead>
<tr class="header">
<th><strong>ID</strong></th>
<th><strong>Name</strong></th>
<th><strong>Operations</strong></th>
<th><strong>Instances</strong></th>
<th><strong>Mandatory</strong></th>
<th><strong>Type</strong></th>
<th><strong>Range or Enumeration</strong></th>
<th><strong>Units</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>Package</td>
<td>W</td>
<td>Single</td>
<td>Mandatory</td>
<td>Opaque</td>
<td></td>
<td></td>
<td>Firmware package</td>
</tr>
<tr class="even">
<td>1</td>
<td>Package URI</td>
<td>RW</td>
<td>Single</td>
<td>Mandatory</td>
<td>String</td>
<td>0-255 bytes</td>
<td></td>
<td>URI from where the device can download the firmware package by an alternative mechanism. As soon the device has received the Package URI it performs the download at the next practical opportunity.<br />
The URI format is defined in RFC 3986. For example, coaps://example.org/firmware is a syntactically valid URI. The URI scheme determines the protocol to be used. For CoAP this endpoint MAY be a LwM2M Server but does not necessarily need to be. A CoAP server implementing block-wise transfer is sufficient as a server hosting a firmware repository and the expectation is that this server merely serves as a separate file server making firmware images available to LwM2M Clients.</td>
</tr>
<tr class="odd">
<td>2</td>
<td>Update</td>
<td>E</td>
<td>Single</td>
<td>Mandatory</td>
<td>none</td>
<td></td>
<td></td>
<td>Updates firmware by using the firmware package stored in Package, or, by using the firmware downloaded from the Package URI.<br />
This Resource is only executable when the value of the State Resource is Downloaded.</td>
</tr>
<tr class="even">
<td>3</td>
<td>State</td>
<td>R</td>
<td>Single</td>
<td>Mandatory</td>
<td>Integer</td>
<td>0-3</td>
<td></td>
<td><p>Indicates current state with respect to this firmware update. This value is set by the LwM2M Client.<br />
0: Idle (before downloading or after successful updating)<br />
1: Downloading (The data sequence is on the way)<br />
2: Downloaded<br />
3: Updating<br />
If writing the firmware package to Package Resource is done, or, if the device has downloaded the firmware package from the Package URI the state changes to Downloaded.<br />
Writing an empty string to Package URI Resource or setting the Package Resource to NULL (‘\0’), resets the Firmware Update State Machine: the State Resource value is set to Idle and the Update Result Resource value is set to 0.</p>
<p>When in Downloaded state, and the executable Resource Update is triggered, the state changes to Updating.<br />
If the Update Resource failed, the state returns at Downloaded.<br />
If performing the Update Resource was successful, the state changes from Updating to Idle.</p>
<p>Firmware Update mechanisms are illustrated below in Figure 29 of the LwM2M version 1.0 specification.</p></td>
</tr>
<tr class="odd">
<td>5</td>
<td>Update Result</td>
<td>R</td>
<td>Single</td>
<td>Mandatory</td>
<td>Integer</td>
<td>0-9</td>
<td></td>
<td><p>Contains the result of downloading or updating the firmware<br />
0: Initial value. Once the updating process is initiated (Download /Update), this Resource MUST be reset to Initial value.<br />
1: Firmware updated successfully,<br />
2: Not enough flash memory for the new firmware package.<br />
3. Out of RAM during downloading process.<br />
4: Connection lost during downloading process.<br />
5: Integrity check failure for new downloaded package.<br />
6: Unsupported package type.<br />
7: Invalid URI</p>
<p>8: Firmware update failed<br />
9: Unsupported protocol. A LwM2M client indicates the failure to retrieve the firmware image using the URI provided in the Package URI resource by writing the value 9 to the /5/0/5 (Update Result resource) when the URI contained a URI scheme unsupported by the client. Consequently, the LwM2M Client is unable to retrieve the firmware image using the URI provided by the LwM2M Server in the Package URI when it refers to an unsupported protocol.</p></td>
</tr>
<tr class="even">
<td>6</td>
<td>PkgName</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td>0-255 bytes</td>
<td></td>
<td>Name of the Firmware Package</td>
</tr>
<tr class="odd">
<td>7</td>
<td>PkgVersion</td>
<td>R</td>
<td>Single</td>
<td>Optional</td>
<td>String</td>
<td>0-255 bytes</td>
<td></td>
<td>Version of the Firmware package</td>
</tr>
<tr class="even">
<td>8</td>
<td>Firmware Update Protocol Support</td>
<td>R</td>
<td>Multiple</td>
<td>Optional</td>
<td>Integer</td>
<td></td>
<td></td>
<td><p>This resource indicates what protocols the LwM2M Client implements to retrieve firmware images. The LwM2M server uses this information to decide what URI to include in the Package URI. A LwM2M Server MUST NOT include a URI in the Package URI object that uses a protocol that is unsupported by the LwM2M client.</p>
<p>For example, if a LwM2M client indicates that it supports CoAP and CoAPS then a LwM2M Server must not provide an HTTP URI in the Packet URI.</p>
<p>The following values are defined by this version of the specification:</p>
<p>0 – CoAP (as defined in RFC 7252) with the additional support for block-wise transfer. CoAP is the default setting.</p>
<p>1 – CoAPS (as defined in RFC 7252) with the additional support for block-wise transfer</p>
<p>2 – HTTP 1.1 (as defined in RFC 7230)</p>
<p>3 – HTTPS 1.1 (as defined in RFC 7230)</p>
<p>Additional values MAY be defined in the future. Any value not understood by the LwM2M Server MUST be ignored.</p></td>
</tr>
<tr class="odd">
<td>9</td>
<td>Firmware Update Delivery Method</td>
<td>R</td>
<td>Single</td>
<td>Mandatory</td>
<td>Integer</td>
<td></td>
<td></td>
<td><p>The LwM2M Client uses this resource to indicate its support for transferring firmware images to the client either via the Package Resource (=push) or via the Package URI Resource (=pull) mechanism.</p>
<p>0 – Pull only</p>
<p>1 – Push only</p>
<p>2 – Both. In this case the LwM2M Server MAY choose the preferred mechanism for conveying the firmware image to the LwM2M Client.</p></td>
</tr>
</tbody>
</table>
<ol style="list-style-type: upper-alpha">
<li><p><span id="_Toc492476220" class="anchor"><span id="_Toc493059906" class="anchor"></span></span>Firmware Update State Machine</p></li>
</ol></td>
<td><table>
<tbody>
<tr class="odd">
<td></td>
</tr>
</tbody>
</table></td>
</tr>
<tr class="even">
<td><p>Figure 29 shows a possible implementation of the firmware update mechanism, described as a UML 2.0 state diagram. The state diagram consists of states, drawn as rounded rectangles, and transitions, drawn as arrows connecting the states. The syntax of the transition is trigger [guard] / behaviour. A trigger is an event that may cause a transition, guard is a condition and behaviour is an activity that executes while the transition takes place. The states additionally contain a compartment that includes assertions and variable assignments. For example, the assertion in the IDLE state indicates the value of the “Update Result” resource (abbreviated as “Res”) must be between 0 and 9. The State resource is set to zero (0) when the program is in this IDLE state.</p>
<p>Errors during the Firmware Update process MUST be reported only by the “Update Result” resource. For instance, when the LwM2M Server performs a Write operation on resource “Package URI”, the LwM2M Client returns a Success or Failure for the Write operation. Then if the URI is invalid, it changes its “Update Result” resource value to 7.</p>
<p><span id="_Ref467138875" class="anchor"></span></p>
<p><span id="_Toc492474261" class="anchor"></span>Figure 29: Firmware Update Mechanisms</p>
<ol style="list-style-type: upper-alpha">
<li><p><span id="_Toc492476221" class="anchor"><span id="_Toc493059907" class="anchor"></span></span>Examples</p></li>
</ol>
<p><span id="_Toc460336563" class="anchor"><span id="_Toc461094143" class="anchor"><span id="_Toc461197670" class="anchor"><span id="_Toc461617497" class="anchor"><span id="_Toc462231146" class="anchor"><span id="_Toc462843635" class="anchor"><span id="_Toc465694874" class="anchor"><span id="_Toc465754888" class="anchor"><span id="_Toc465771977" class="anchor"><span id="_Toc466534745" class="anchor"><span id="_Toc467143146" class="anchor"><span id="_Toc467678288" class="anchor"><span id="_Toc469902430" class="anchor"><span id="_Toc470163223" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span>The example depicted in Figure 30 illustrates a successful message exchange where a LwM2M Server pushes a firmware image to a LwM2M Client using the block-wise transfer. In this example the LwM2M Server indicates a block size of 128 bytes and the firmware image of 80 KiB (=81920 bytes) will be sent to the LwM2M Client in 640 messages with each 128 bytes payload. Since the LwM2M Server-provided block size matches the preferences of the LwM2M Client the exchange proceeds until the full firmware image is downloaded. In this example, no messages are lost during transmission.</p>
<p><span id="_Toc460336564" class="anchor"><span id="_Toc461094144" class="anchor"><span id="_Toc461197671" class="anchor"><span id="_Toc461617498" class="anchor"><span id="_Toc462231147" class="anchor"><span id="_Toc462843636" class="anchor"><span id="_Toc465694875" class="anchor"><span id="_Toc465754889" class="anchor"><span id="_Toc465771978" class="anchor"><span id="_Toc466534746" class="anchor"><span id="_Toc467143147" class="anchor"><span id="_Toc467678289" class="anchor"><span id="_Toc469902431" class="anchor"><span id="_Toc470163224" class="anchor"><span id="_Toc471907791" class="anchor"><span id="_Toc472076018" class="anchor"><span id="_Toc472088023" class="anchor"><span id="_Toc473189371" class="anchor"><span id="_Toc473886296" class="anchor"><span id="_Toc474327091" class="anchor"><span id="_Toc474339784" class="anchor"><span id="_Toc479158092" class="anchor"><span id="_Toc479847237" class="anchor"><span id="_Toc487470276" class="anchor"><span id="_Toc492476222" class="anchor"><span id="_Toc493059908" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>LwM2M LwM2M</p>
<p><span id="_Toc460336565" class="anchor"><span id="_Toc461094145" class="anchor"><span id="_Toc461197672" class="anchor"><span id="_Toc461617499" class="anchor"><span id="_Toc462231148" class="anchor"><span id="_Toc462843637" class="anchor"><span id="_Toc465694876" class="anchor"><span id="_Toc465754890" class="anchor"><span id="_Toc465771979" class="anchor"><span id="_Toc466534747" class="anchor"><span id="_Toc467143148" class="anchor"><span id="_Toc467678290" class="anchor"><span id="_Toc469902432" class="anchor"><span id="_Toc470163225" class="anchor"><span id="_Toc471907792" class="anchor"><span id="_Toc472076019" class="anchor"><span id="_Toc472088024" class="anchor"><span id="_Toc473189372" class="anchor"><span id="_Toc473886297" class="anchor"><span id="_Toc474327092" class="anchor"><span id="_Toc474339785" class="anchor"><span id="_Toc479158093" class="anchor"><span id="_Toc479847238" class="anchor"><span id="_Toc487470277" class="anchor"><span id="_Toc492476223" class="anchor"><span id="_Toc493059909" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>Server Client</p>
<p><span id="_Toc460336566" class="anchor"><span id="_Toc461094146" class="anchor"><span id="_Toc461197673" class="anchor"><span id="_Toc461617500" class="anchor"><span id="_Toc462231149" class="anchor"><span id="_Toc462843638" class="anchor"><span id="_Toc465694877" class="anchor"><span id="_Toc465754891" class="anchor"><span id="_Toc465771980" class="anchor"><span id="_Toc466534748" class="anchor"><span id="_Toc467143149" class="anchor"><span id="_Toc467678291" class="anchor"><span id="_Toc469902433" class="anchor"><span id="_Toc470163226" class="anchor"><span id="_Toc471907793" class="anchor"><span id="_Toc472076020" class="anchor"><span id="_Toc472088025" class="anchor"><span id="_Toc473189373" class="anchor"><span id="_Toc473886298" class="anchor"><span id="_Toc474327093" class="anchor"><span id="_Toc474339786" class="anchor"><span id="_Toc479158094" class="anchor"><span id="_Toc479847239" class="anchor"><span id="_Toc487470278" class="anchor"><span id="_Toc492476224" class="anchor"><span id="_Toc493059910" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336567" class="anchor"><span id="_Toc461094147" class="anchor"><span id="_Toc461197674" class="anchor"><span id="_Toc461617501" class="anchor"><span id="_Toc462231150" class="anchor"><span id="_Toc462843639" class="anchor"><span id="_Toc465694878" class="anchor"><span id="_Toc465754892" class="anchor"><span id="_Toc465771981" class="anchor"><span id="_Toc466534749" class="anchor"><span id="_Toc467143150" class="anchor"><span id="_Toc467678292" class="anchor"><span id="_Toc469902434" class="anchor"><span id="_Toc470163227" class="anchor"><span id="_Toc471907794" class="anchor"><span id="_Toc472076021" class="anchor"><span id="_Toc472088026" class="anchor"><span id="_Toc473189374" class="anchor"><span id="_Toc473886299" class="anchor"><span id="_Toc474327094" class="anchor"><span id="_Toc474339787" class="anchor"><span id="_Toc479158095" class="anchor"><span id="_Toc479847240" class="anchor"><span id="_Toc487470279" class="anchor"><span id="_Toc492476225" class="anchor"><span id="_Toc493059911" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| CON [MID=1], POST, /5/0/0, 1:0/1/128 ------&gt; |</p>
<p><span id="_Toc460336568" class="anchor"><span id="_Toc461094148" class="anchor"><span id="_Toc461197675" class="anchor"><span id="_Toc461617502" class="anchor"><span id="_Toc462231151" class="anchor"><span id="_Toc462843640" class="anchor"><span id="_Toc465694879" class="anchor"><span id="_Toc465754893" class="anchor"><span id="_Toc465771982" class="anchor"><span id="_Toc466534750" class="anchor"><span id="_Toc467143151" class="anchor"><span id="_Toc467678293" class="anchor"><span id="_Toc469902435" class="anchor"><span id="_Toc470163228" class="anchor"><span id="_Toc471907795" class="anchor"><span id="_Toc472076022" class="anchor"><span id="_Toc472088027" class="anchor"><span id="_Toc473189375" class="anchor"><span id="_Toc473886300" class="anchor"><span id="_Toc474327095" class="anchor"><span id="_Toc474339788" class="anchor"><span id="_Toc479158096" class="anchor"><span id="_Toc479847241" class="anchor"><span id="_Toc487470280" class="anchor"><span id="_Toc492476226" class="anchor"><span id="_Toc493059912" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336569" class="anchor"><span id="_Toc461094149" class="anchor"><span id="_Toc461197676" class="anchor"><span id="_Toc461617503" class="anchor"><span id="_Toc462231152" class="anchor"><span id="_Toc462843641" class="anchor"><span id="_Toc465694880" class="anchor"><span id="_Toc465754894" class="anchor"><span id="_Toc465771983" class="anchor"><span id="_Toc466534751" class="anchor"><span id="_Toc467143152" class="anchor"><span id="_Toc467678294" class="anchor"><span id="_Toc469902436" class="anchor"><span id="_Toc470163229" class="anchor"><span id="_Toc471907796" class="anchor"><span id="_Toc472076023" class="anchor"><span id="_Toc472088028" class="anchor"><span id="_Toc473189376" class="anchor"><span id="_Toc473886301" class="anchor"><span id="_Toc474327096" class="anchor"><span id="_Toc474339789" class="anchor"><span id="_Toc479158097" class="anchor"><span id="_Toc479847242" class="anchor"><span id="_Toc487470281" class="anchor"><span id="_Toc492476227" class="anchor"><span id="_Toc493059913" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| &lt;------ ACK [MID=1], 2.31 Continue, 1:0/1/128 |</p>
<p><span id="_Toc460336570" class="anchor"><span id="_Toc461094150" class="anchor"><span id="_Toc461197677" class="anchor"><span id="_Toc461617504" class="anchor"><span id="_Toc462231153" class="anchor"><span id="_Toc462843642" class="anchor"><span id="_Toc465694881" class="anchor"><span id="_Toc465754895" class="anchor"><span id="_Toc465771984" class="anchor"><span id="_Toc466534752" class="anchor"><span id="_Toc467143153" class="anchor"><span id="_Toc467678295" class="anchor"><span id="_Toc469902437" class="anchor"><span id="_Toc470163230" class="anchor"><span id="_Toc471907797" class="anchor"><span id="_Toc472076024" class="anchor"><span id="_Toc472088029" class="anchor"><span id="_Toc473189377" class="anchor"><span id="_Toc473886302" class="anchor"><span id="_Toc474327097" class="anchor"><span id="_Toc474339790" class="anchor"><span id="_Toc479158098" class="anchor"><span id="_Toc479847243" class="anchor"><span id="_Toc487470282" class="anchor"><span id="_Toc492476228" class="anchor"><span id="_Toc493059914" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336571" class="anchor"><span id="_Toc461094151" class="anchor"><span id="_Toc461197678" class="anchor"><span id="_Toc461617505" class="anchor"><span id="_Toc462231154" class="anchor"><span id="_Toc462843643" class="anchor"><span id="_Toc465694882" class="anchor"><span id="_Toc465754896" class="anchor"><span id="_Toc465771985" class="anchor"><span id="_Toc466534753" class="anchor"><span id="_Toc467143154" class="anchor"><span id="_Toc467678296" class="anchor"><span id="_Toc469902438" class="anchor"><span id="_Toc470163231" class="anchor"><span id="_Toc471907798" class="anchor"><span id="_Toc472076025" class="anchor"><span id="_Toc472088030" class="anchor"><span id="_Toc473189378" class="anchor"><span id="_Toc473886303" class="anchor"><span id="_Toc474327098" class="anchor"><span id="_Toc474339791" class="anchor"><span id="_Toc479158099" class="anchor"><span id="_Toc479847244" class="anchor"><span id="_Toc487470283" class="anchor"><span id="_Toc492476229" class="anchor"><span id="_Toc493059915" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| CON [MID=2], POST, /5/0/0, 1:1/1/128 ------&gt; |</p>
<p><span id="_Toc460336572" class="anchor"><span id="_Toc461094152" class="anchor"><span id="_Toc461197679" class="anchor"><span id="_Toc461617506" class="anchor"><span id="_Toc462231155" class="anchor"><span id="_Toc462843644" class="anchor"><span id="_Toc465694883" class="anchor"><span id="_Toc465754897" class="anchor"><span id="_Toc465771986" class="anchor"><span id="_Toc466534754" class="anchor"><span id="_Toc467143155" class="anchor"><span id="_Toc467678297" class="anchor"><span id="_Toc469902439" class="anchor"><span id="_Toc470163232" class="anchor"><span id="_Toc471907799" class="anchor"><span id="_Toc472076026" class="anchor"><span id="_Toc472088031" class="anchor"><span id="_Toc473189379" class="anchor"><span id="_Toc473886304" class="anchor"><span id="_Toc474327099" class="anchor"><span id="_Toc474339792" class="anchor"><span id="_Toc479158100" class="anchor"><span id="_Toc479847245" class="anchor"><span id="_Toc487470284" class="anchor"><span id="_Toc492476230" class="anchor"><span id="_Toc493059916" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336573" class="anchor"><span id="_Toc461094153" class="anchor"><span id="_Toc461197680" class="anchor"><span id="_Toc461617507" class="anchor"><span id="_Toc462231156" class="anchor"><span id="_Toc462843645" class="anchor"><span id="_Toc465694884" class="anchor"><span id="_Toc465754898" class="anchor"><span id="_Toc465771987" class="anchor"><span id="_Toc466534755" class="anchor"><span id="_Toc467143156" class="anchor"><span id="_Toc467678298" class="anchor"><span id="_Toc469902440" class="anchor"><span id="_Toc470163233" class="anchor"><span id="_Toc471907800" class="anchor"><span id="_Toc472076027" class="anchor"><span id="_Toc472088032" class="anchor"><span id="_Toc473189380" class="anchor"><span id="_Toc473886305" class="anchor"><span id="_Toc474327100" class="anchor"><span id="_Toc474339793" class="anchor"><span id="_Toc479158101" class="anchor"><span id="_Toc479847246" class="anchor"><span id="_Toc487470285" class="anchor"><span id="_Toc492476231" class="anchor"><span id="_Toc493059917" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| &lt;------ ACK [MID=2], 2.31 Continue, 1:1/1/128 |</p>
<p><span id="_Toc460336574" class="anchor"><span id="_Toc461094154" class="anchor"><span id="_Toc461197681" class="anchor"><span id="_Toc461617508" class="anchor"><span id="_Toc462231157" class="anchor"><span id="_Toc462843646" class="anchor"><span id="_Toc465694885" class="anchor"><span id="_Toc465754899" class="anchor"><span id="_Toc465771988" class="anchor"><span id="_Toc466534756" class="anchor"><span id="_Toc467143157" class="anchor"><span id="_Toc467678299" class="anchor"><span id="_Toc469902441" class="anchor"><span id="_Toc470163234" class="anchor"><span id="_Toc471907801" class="anchor"><span id="_Toc472076028" class="anchor"><span id="_Toc472088033" class="anchor"><span id="_Toc473189381" class="anchor"><span id="_Toc473886306" class="anchor"><span id="_Toc474327101" class="anchor"><span id="_Toc474339794" class="anchor"><span id="_Toc479158102" class="anchor"><span id="_Toc479847247" class="anchor"><span id="_Toc487470286" class="anchor"><span id="_Toc492476232" class="anchor"><span id="_Toc493059918" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336575" class="anchor"><span id="_Toc461094155" class="anchor"><span id="_Toc461197682" class="anchor"><span id="_Toc461617509" class="anchor"><span id="_Toc462231158" class="anchor"><span id="_Toc462843647" class="anchor"><span id="_Toc465694886" class="anchor"><span id="_Toc465754900" class="anchor"><span id="_Toc465771989" class="anchor"><span id="_Toc466534757" class="anchor"><span id="_Toc467143158" class="anchor"><span id="_Toc467678300" class="anchor"><span id="_Toc469902442" class="anchor"><span id="_Toc470163235" class="anchor"><span id="_Toc471907802" class="anchor"><span id="_Toc472076029" class="anchor"><span id="_Toc472088034" class="anchor"><span id="_Toc473189382" class="anchor"><span id="_Toc473886307" class="anchor"><span id="_Toc474327102" class="anchor"><span id="_Toc474339795" class="anchor"><span id="_Toc479158103" class="anchor"><span id="_Toc479847248" class="anchor"><span id="_Toc487470287" class="anchor"><span id="_Toc492476233" class="anchor"><span id="_Toc493059919" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| ... 637 exchanges ... |</p>
<p><span id="_Toc460336576" class="anchor"><span id="_Toc461094156" class="anchor"><span id="_Toc461197683" class="anchor"><span id="_Toc461617510" class="anchor"><span id="_Toc462231159" class="anchor"><span id="_Toc462843648" class="anchor"><span id="_Toc465694887" class="anchor"><span id="_Toc465754901" class="anchor"><span id="_Toc465771990" class="anchor"><span id="_Toc466534758" class="anchor"><span id="_Toc467143159" class="anchor"><span id="_Toc467678301" class="anchor"><span id="_Toc469902443" class="anchor"><span id="_Toc470163236" class="anchor"><span id="_Toc471907803" class="anchor"><span id="_Toc472076030" class="anchor"><span id="_Toc472088035" class="anchor"><span id="_Toc473189383" class="anchor"><span id="_Toc473886308" class="anchor"><span id="_Toc474327103" class="anchor"><span id="_Toc474339796" class="anchor"><span id="_Toc479158104" class="anchor"><span id="_Toc479847249" class="anchor"><span id="_Toc487470288" class="anchor"><span id="_Toc492476234" class="anchor"><span id="_Toc493059920" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336577" class="anchor"><span id="_Toc461094157" class="anchor"><span id="_Toc461197684" class="anchor"><span id="_Toc461617511" class="anchor"><span id="_Toc462231160" class="anchor"><span id="_Toc462843649" class="anchor"><span id="_Toc465694888" class="anchor"><span id="_Toc465754902" class="anchor"><span id="_Toc465771991" class="anchor"><span id="_Toc466534759" class="anchor"><span id="_Toc467143160" class="anchor"><span id="_Toc467678302" class="anchor"><span id="_Toc469902444" class="anchor"><span id="_Toc470163237" class="anchor"><span id="_Toc471907804" class="anchor"><span id="_Toc472076031" class="anchor"><span id="_Toc472088036" class="anchor"><span id="_Toc473189384" class="anchor"><span id="_Toc473886309" class="anchor"><span id="_Toc474327104" class="anchor"><span id="_Toc474339797" class="anchor"><span id="_Toc479158105" class="anchor"><span id="_Toc479847250" class="anchor"><span id="_Toc487470289" class="anchor"><span id="_Toc492476235" class="anchor"><span id="_Toc493059921" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| CON [MID=640], POST, /5/0/0, 1:639/0/128 ------&gt; |</p>
<p><span id="_Toc460336578" class="anchor"><span id="_Toc461094158" class="anchor"><span id="_Toc461197685" class="anchor"><span id="_Toc461617512" class="anchor"><span id="_Toc462231161" class="anchor"><span id="_Toc462843650" class="anchor"><span id="_Toc465694889" class="anchor"><span id="_Toc465754903" class="anchor"><span id="_Toc465771992" class="anchor"><span id="_Toc466534760" class="anchor"><span id="_Toc467143161" class="anchor"><span id="_Toc467678303" class="anchor"><span id="_Toc469902445" class="anchor"><span id="_Toc470163238" class="anchor"><span id="_Toc471907805" class="anchor"><span id="_Toc472076032" class="anchor"><span id="_Toc472088037" class="anchor"><span id="_Toc473189385" class="anchor"><span id="_Toc473886310" class="anchor"><span id="_Toc474327105" class="anchor"><span id="_Toc474339798" class="anchor"><span id="_Toc479158106" class="anchor"><span id="_Toc479847251" class="anchor"><span id="_Toc487470290" class="anchor"><span id="_Toc492476236" class="anchor"><span id="_Toc493059922" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336579" class="anchor"><span id="_Toc461094159" class="anchor"><span id="_Toc461197686" class="anchor"><span id="_Toc461617513" class="anchor"><span id="_Toc462231162" class="anchor"><span id="_Toc462843651" class="anchor"><span id="_Toc465694890" class="anchor"><span id="_Toc465754904" class="anchor"><span id="_Toc465771993" class="anchor"><span id="_Toc466534761" class="anchor"><span id="_Toc467143162" class="anchor"><span id="_Toc467678304" class="anchor"><span id="_Toc469902446" class="anchor"><span id="_Toc470163239" class="anchor"><span id="_Toc471907806" class="anchor"><span id="_Toc472076033" class="anchor"><span id="_Toc472088038" class="anchor"><span id="_Toc473189386" class="anchor"><span id="_Toc473886311" class="anchor"><span id="_Toc474327106" class="anchor"><span id="_Toc474339799" class="anchor"><span id="_Toc479158107" class="anchor"><span id="_Toc479847252" class="anchor"><span id="_Toc487470291" class="anchor"><span id="_Toc492476237" class="anchor"><span id="_Toc493059923" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| &lt;------ ACK [MID=640], 2.04 Changed, 1:639/0/128 |</p>
<p><span id="_Toc460336580" class="anchor"><span id="_Toc461094160" class="anchor"><span id="_Toc461197687" class="anchor"><span id="_Toc461617514" class="anchor"><span id="_Toc462231163" class="anchor"><span id="_Toc462843652" class="anchor"><span id="_Toc465694891" class="anchor"><span id="_Toc465754905" class="anchor"><span id="_Toc465771994" class="anchor"><span id="_Toc466534762" class="anchor"><span id="_Toc467143163" class="anchor"><span id="_Toc467678305" class="anchor"><span id="_Toc469902447" class="anchor"><span id="_Toc470163240" class="anchor"><span id="_Toc471907807" class="anchor"><span id="_Toc472076034" class="anchor"><span id="_Toc472088039" class="anchor"><span id="_Toc473189387" class="anchor"><span id="_Toc473886312" class="anchor"><span id="_Toc474327107" class="anchor"><span id="_Toc474339800" class="anchor"><span id="_Toc479158108" class="anchor"><span id="_Toc479847253" class="anchor"><span id="_Toc487470292" class="anchor"><span id="_Toc492476238" class="anchor"><span id="_Toc493059924" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Ref467138911" class="anchor"><span id="_Ref460334002" class="anchor"><span id="_Toc492474262" class="anchor"></span></span></span>Figure 30: Example of a LwM2M Server pushing a firmware image to a LwM2M client</p>
<p>The second example shown in Figure 31 illustrates the case where the client was provided with a URI by the LwM2M Server (using the Package URI resource) and therefore fetches the firmware image from the indicated server. Note that only the retrieval of the firmware image from the LwM2M Server is shown in Figure 31 and not the initial configuration of the Package URI.</p>
<p><span id="_Toc471907808" class="anchor"><span id="_Toc472076035" class="anchor"><span id="_Toc472088040" class="anchor"><span id="_Toc473189388" class="anchor"><span id="_Toc473886313" class="anchor"></span></span></span></span></span> <span id="_Toc474327108" class="anchor"><span id="_Toc474339801" class="anchor"><span id="_Toc479158109" class="anchor"><span id="_Toc479847254" class="anchor"><span id="_Toc487470293" class="anchor"><span id="_Toc492476239" class="anchor"><span id="_Toc493059925" class="anchor"></span></span></span></span></span></span></span>LwM2M LwM2M</p>
<p><span id="_Toc460336582" class="anchor"><span id="_Toc461094162" class="anchor"><span id="_Toc461197689" class="anchor"><span id="_Toc461617516" class="anchor"><span id="_Toc462231165" class="anchor"><span id="_Toc462843654" class="anchor"><span id="_Toc465694893" class="anchor"><span id="_Toc465754907" class="anchor"><span id="_Toc465771996" class="anchor"><span id="_Toc466534764" class="anchor"><span id="_Toc467143165" class="anchor"><span id="_Toc467678307" class="anchor"><span id="_Toc469902449" class="anchor"><span id="_Toc470163242" class="anchor"><span id="_Toc471907809" class="anchor"><span id="_Toc472076036" class="anchor"><span id="_Toc472088041" class="anchor"><span id="_Toc473189389" class="anchor"><span id="_Toc473886314" class="anchor"><span id="_Toc474327109" class="anchor"><span id="_Toc474339802" class="anchor"><span id="_Toc479158110" class="anchor"><span id="_Toc479847255" class="anchor"><span id="_Toc487470294" class="anchor"><span id="_Toc492476240" class="anchor"><span id="_Toc493059926" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>Client Server</p>
<p><span id="_Toc460336583" class="anchor"><span id="_Toc461094163" class="anchor"><span id="_Toc461197690" class="anchor"><span id="_Toc461617517" class="anchor"><span id="_Toc462231166" class="anchor"><span id="_Toc462843655" class="anchor"><span id="_Toc465694894" class="anchor"><span id="_Toc465754908" class="anchor"><span id="_Toc465771997" class="anchor"><span id="_Toc466534765" class="anchor"><span id="_Toc467143166" class="anchor"><span id="_Toc467678308" class="anchor"><span id="_Toc469902450" class="anchor"><span id="_Toc470163243" class="anchor"><span id="_Toc471907810" class="anchor"><span id="_Toc472076037" class="anchor"><span id="_Toc472088042" class="anchor"><span id="_Toc473189390" class="anchor"><span id="_Toc473886315" class="anchor"><span id="_Toc474327110" class="anchor"><span id="_Toc474339803" class="anchor"><span id="_Toc479158111" class="anchor"><span id="_Toc479847256" class="anchor"><span id="_Toc487470295" class="anchor"><span id="_Toc492476241" class="anchor"><span id="_Toc493059927" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336584" class="anchor"><span id="_Toc461094164" class="anchor"><span id="_Toc461197691" class="anchor"><span id="_Toc461617518" class="anchor"><span id="_Toc462231167" class="anchor"><span id="_Toc462843656" class="anchor"><span id="_Toc465694895" class="anchor"><span id="_Toc465754909" class="anchor"><span id="_Toc465771998" class="anchor"><span id="_Toc466534766" class="anchor"><span id="_Toc467143167" class="anchor"><span id="_Toc467678309" class="anchor"><span id="_Toc469902451" class="anchor"><span id="_Toc470163244" class="anchor"><span id="_Toc471907811" class="anchor"><span id="_Toc472076038" class="anchor"><span id="_Toc472088043" class="anchor"><span id="_Toc473189391" class="anchor"><span id="_Toc473886316" class="anchor"><span id="_Toc474327111" class="anchor"><span id="_Toc474339804" class="anchor"><span id="_Toc479158112" class="anchor"><span id="_Toc479847257" class="anchor"><span id="_Toc487470296" class="anchor"><span id="_Toc492476242" class="anchor"><span id="_Toc493059928" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| CON [MID=1], GET, /firmware ------&gt; |</p>
<p><span id="_Toc460336585" class="anchor"><span id="_Toc461094165" class="anchor"><span id="_Toc461197692" class="anchor"><span id="_Toc461617519" class="anchor"><span id="_Toc462231168" class="anchor"><span id="_Toc462843657" class="anchor"><span id="_Toc465694896" class="anchor"><span id="_Toc465754910" class="anchor"><span id="_Toc465771999" class="anchor"><span id="_Toc466534767" class="anchor"><span id="_Toc467143168" class="anchor"><span id="_Toc467678310" class="anchor"><span id="_Toc469902452" class="anchor"><span id="_Toc470163245" class="anchor"><span id="_Toc471907812" class="anchor"><span id="_Toc472076039" class="anchor"><span id="_Toc472088044" class="anchor"><span id="_Toc473189392" class="anchor"><span id="_Toc473886317" class="anchor"><span id="_Toc474327112" class="anchor"><span id="_Toc474339805" class="anchor"><span id="_Toc479158113" class="anchor"><span id="_Toc479847258" class="anchor"><span id="_Toc487470297" class="anchor"><span id="_Toc492476243" class="anchor"><span id="_Toc493059929" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336586" class="anchor"><span id="_Toc461094166" class="anchor"><span id="_Toc461197693" class="anchor"><span id="_Toc461617520" class="anchor"><span id="_Toc462231169" class="anchor"><span id="_Toc462843658" class="anchor"><span id="_Toc465694897" class="anchor"><span id="_Toc465754911" class="anchor"><span id="_Toc465772000" class="anchor"><span id="_Toc466534768" class="anchor"><span id="_Toc467143169" class="anchor"><span id="_Toc467678311" class="anchor"><span id="_Toc469902453" class="anchor"><span id="_Toc470163246" class="anchor"><span id="_Toc471907813" class="anchor"><span id="_Toc472076040" class="anchor"><span id="_Toc472088045" class="anchor"><span id="_Toc473189393" class="anchor"><span id="_Toc473886318" class="anchor"><span id="_Toc474327113" class="anchor"><span id="_Toc474339806" class="anchor"><span id="_Toc479158114" class="anchor"><span id="_Toc479847259" class="anchor"><span id="_Toc487470298" class="anchor"><span id="_Toc492476244" class="anchor"><span id="_Toc493059930" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| &lt;------ ACK [MID=1], 2.05 Content, 2:0/1/128 |</p>
<p><span id="_Toc460336587" class="anchor"><span id="_Toc461094167" class="anchor"><span id="_Toc461197694" class="anchor"><span id="_Toc461617521" class="anchor"><span id="_Toc462231170" class="anchor"><span id="_Toc462843659" class="anchor"><span id="_Toc465694898" class="anchor"><span id="_Toc465754912" class="anchor"><span id="_Toc465772001" class="anchor"><span id="_Toc466534769" class="anchor"><span id="_Toc467143170" class="anchor"><span id="_Toc467678312" class="anchor"><span id="_Toc469902454" class="anchor"><span id="_Toc470163247" class="anchor"><span id="_Toc471907814" class="anchor"><span id="_Toc472076041" class="anchor"><span id="_Toc472088046" class="anchor"><span id="_Toc473189394" class="anchor"><span id="_Toc473886319" class="anchor"><span id="_Toc474327114" class="anchor"><span id="_Toc474339807" class="anchor"><span id="_Toc479158115" class="anchor"><span id="_Toc479847260" class="anchor"><span id="_Toc487470299" class="anchor"><span id="_Toc492476245" class="anchor"><span id="_Toc493059931" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336588" class="anchor"><span id="_Toc461094168" class="anchor"><span id="_Toc461197695" class="anchor"><span id="_Toc461617522" class="anchor"><span id="_Toc462231171" class="anchor"><span id="_Toc462843660" class="anchor"><span id="_Toc465694899" class="anchor"><span id="_Toc465754913" class="anchor"><span id="_Toc465772002" class="anchor"><span id="_Toc466534770" class="anchor"><span id="_Toc467143171" class="anchor"><span id="_Toc467678313" class="anchor"><span id="_Toc469902455" class="anchor"><span id="_Toc470163248" class="anchor"><span id="_Toc471907815" class="anchor"><span id="_Toc472076042" class="anchor"><span id="_Toc472088047" class="anchor"><span id="_Toc473189395" class="anchor"><span id="_Toc473886320" class="anchor"><span id="_Toc474327115" class="anchor"><span id="_Toc474339808" class="anchor"><span id="_Toc479158116" class="anchor"><span id="_Toc479847261" class="anchor"><span id="_Toc487470300" class="anchor"><span id="_Toc492476246" class="anchor"><span id="_Toc493059932" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| CON [MID=2], GET, /firmware, 2:1/0/128 ------&gt; |</p>
<p><span id="_Toc460336589" class="anchor"><span id="_Toc461094169" class="anchor"><span id="_Toc461197696" class="anchor"><span id="_Toc461617523" class="anchor"><span id="_Toc462231172" class="anchor"><span id="_Toc462843661" class="anchor"><span id="_Toc465694900" class="anchor"><span id="_Toc465754914" class="anchor"><span id="_Toc465772003" class="anchor"><span id="_Toc466534771" class="anchor"><span id="_Toc467143172" class="anchor"><span id="_Toc467678314" class="anchor"><span id="_Toc469902456" class="anchor"><span id="_Toc470163249" class="anchor"><span id="_Toc471907816" class="anchor"><span id="_Toc472076043" class="anchor"><span id="_Toc472088048" class="anchor"><span id="_Toc473189396" class="anchor"><span id="_Toc473886321" class="anchor"><span id="_Toc474327116" class="anchor"><span id="_Toc474339809" class="anchor"><span id="_Toc479158117" class="anchor"><span id="_Toc479847262" class="anchor"><span id="_Toc487470301" class="anchor"><span id="_Toc492476247" class="anchor"><span id="_Toc493059933" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336590" class="anchor"><span id="_Toc461094170" class="anchor"><span id="_Toc461197697" class="anchor"><span id="_Toc461617524" class="anchor"><span id="_Toc462231173" class="anchor"><span id="_Toc462843662" class="anchor"><span id="_Toc465694901" class="anchor"><span id="_Toc465754915" class="anchor"><span id="_Toc465772004" class="anchor"><span id="_Toc466534772" class="anchor"><span id="_Toc467143173" class="anchor"><span id="_Toc467678315" class="anchor"><span id="_Toc469902457" class="anchor"><span id="_Toc470163250" class="anchor"><span id="_Toc471907817" class="anchor"><span id="_Toc472076044" class="anchor"><span id="_Toc472088049" class="anchor"><span id="_Toc473189397" class="anchor"><span id="_Toc473886322" class="anchor"><span id="_Toc474327117" class="anchor"><span id="_Toc474339810" class="anchor"><span id="_Toc479158118" class="anchor"><span id="_Toc479847263" class="anchor"><span id="_Toc487470302" class="anchor"><span id="_Toc492476248" class="anchor"><span id="_Toc493059934" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| &lt;------ ACK [MID=2], 2.05 Content, 2:1/1/128 |</p>
<p><span id="_Toc460336591" class="anchor"><span id="_Toc461094171" class="anchor"><span id="_Toc461197698" class="anchor"><span id="_Toc461617525" class="anchor"><span id="_Toc462231174" class="anchor"><span id="_Toc462843663" class="anchor"><span id="_Toc465694902" class="anchor"><span id="_Toc465754916" class="anchor"><span id="_Toc465772005" class="anchor"><span id="_Toc466534773" class="anchor"><span id="_Toc467143174" class="anchor"><span id="_Toc467678316" class="anchor"><span id="_Toc469902458" class="anchor"><span id="_Toc470163251" class="anchor"><span id="_Toc471907818" class="anchor"><span id="_Toc472076045" class="anchor"><span id="_Toc472088050" class="anchor"><span id="_Toc473189398" class="anchor"><span id="_Toc473886323" class="anchor"><span id="_Toc474327118" class="anchor"><span id="_Toc474339811" class="anchor"><span id="_Toc479158119" class="anchor"><span id="_Toc479847264" class="anchor"><span id="_Toc487470303" class="anchor"><span id="_Toc492476249" class="anchor"><span id="_Toc493059935" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336592" class="anchor"><span id="_Toc461094172" class="anchor"><span id="_Toc461197699" class="anchor"><span id="_Toc461617526" class="anchor"><span id="_Toc462231175" class="anchor"><span id="_Toc462843664" class="anchor"><span id="_Toc465694903" class="anchor"><span id="_Toc465754917" class="anchor"><span id="_Toc465772006" class="anchor"><span id="_Toc466534774" class="anchor"><span id="_Toc467143175" class="anchor"><span id="_Toc467678317" class="anchor"><span id="_Toc469902459" class="anchor"><span id="_Toc470163252" class="anchor"><span id="_Toc471907819" class="anchor"><span id="_Toc472076046" class="anchor"><span id="_Toc472088051" class="anchor"><span id="_Toc473189399" class="anchor"><span id="_Toc473886324" class="anchor"><span id="_Toc474327119" class="anchor"><span id="_Toc474339812" class="anchor"><span id="_Toc479158120" class="anchor"><span id="_Toc479847265" class="anchor"><span id="_Toc487470304" class="anchor"><span id="_Toc492476250" class="anchor"><span id="_Toc493059936" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| ... 637 exchanges ... |</p>
<p><span id="_Toc460336593" class="anchor"><span id="_Toc461094173" class="anchor"><span id="_Toc461197700" class="anchor"><span id="_Toc461617527" class="anchor"><span id="_Toc462231176" class="anchor"><span id="_Toc462843665" class="anchor"><span id="_Toc465694904" class="anchor"><span id="_Toc465754918" class="anchor"><span id="_Toc465772007" class="anchor"><span id="_Toc466534775" class="anchor"><span id="_Toc467143176" class="anchor"><span id="_Toc467678318" class="anchor"><span id="_Toc469902460" class="anchor"><span id="_Toc470163253" class="anchor"><span id="_Toc471907820" class="anchor"><span id="_Toc472076047" class="anchor"><span id="_Toc472088052" class="anchor"><span id="_Toc473189400" class="anchor"><span id="_Toc473886325" class="anchor"><span id="_Toc474327120" class="anchor"><span id="_Toc474339813" class="anchor"><span id="_Toc479158121" class="anchor"><span id="_Toc479847266" class="anchor"><span id="_Toc487470305" class="anchor"><span id="_Toc492476251" class="anchor"><span id="_Toc493059937" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336594" class="anchor"><span id="_Toc461094174" class="anchor"><span id="_Toc461197701" class="anchor"><span id="_Toc461617528" class="anchor"><span id="_Toc462231177" class="anchor"><span id="_Toc462843666" class="anchor"><span id="_Toc465694905" class="anchor"><span id="_Toc465754919" class="anchor"><span id="_Toc465772008" class="anchor"><span id="_Toc466534776" class="anchor"><span id="_Toc467143177" class="anchor"><span id="_Toc467678319" class="anchor"><span id="_Toc469902461" class="anchor"><span id="_Toc470163254" class="anchor"><span id="_Toc471907821" class="anchor"><span id="_Toc472076048" class="anchor"><span id="_Toc472088053" class="anchor"><span id="_Toc473189401" class="anchor"><span id="_Toc473886326" class="anchor"><span id="_Toc474327121" class="anchor"><span id="_Toc474339814" class="anchor"><span id="_Toc479158122" class="anchor"><span id="_Toc479847267" class="anchor"><span id="_Toc487470306" class="anchor"><span id="_Toc492476252" class="anchor"><span id="_Toc493059938" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| CON [MID=640], GET, /firmware, 2:639/0/128 ------&gt;|</p>
<p><span id="_Toc460336595" class="anchor"><span id="_Toc461094175" class="anchor"><span id="_Toc461197702" class="anchor"><span id="_Toc461617529" class="anchor"><span id="_Toc462231178" class="anchor"><span id="_Toc462843667" class="anchor"><span id="_Toc465694906" class="anchor"><span id="_Toc465754920" class="anchor"><span id="_Toc465772009" class="anchor"><span id="_Toc466534777" class="anchor"><span id="_Toc467143178" class="anchor"><span id="_Toc467678320" class="anchor"><span id="_Toc469902462" class="anchor"><span id="_Toc470163255" class="anchor"><span id="_Toc471907822" class="anchor"><span id="_Toc472076049" class="anchor"><span id="_Toc472088054" class="anchor"><span id="_Toc473189402" class="anchor"><span id="_Toc473886327" class="anchor"><span id="_Toc474327122" class="anchor"><span id="_Toc474339815" class="anchor"><span id="_Toc479158123" class="anchor"><span id="_Toc479847268" class="anchor"><span id="_Toc487470307" class="anchor"><span id="_Toc492476253" class="anchor"><span id="_Toc493059939" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Toc460336596" class="anchor"><span id="_Toc461094176" class="anchor"><span id="_Toc461197703" class="anchor"><span id="_Toc461617530" class="anchor"><span id="_Toc462231179" class="anchor"><span id="_Toc462843668" class="anchor"><span id="_Toc465694907" class="anchor"><span id="_Toc465754921" class="anchor"><span id="_Toc465772010" class="anchor"><span id="_Toc466534778" class="anchor"><span id="_Toc467143179" class="anchor"><span id="_Toc467678321" class="anchor"><span id="_Toc469902463" class="anchor"><span id="_Toc470163256" class="anchor"><span id="_Toc471907823" class="anchor"><span id="_Toc472076050" class="anchor"><span id="_Toc472088055" class="anchor"><span id="_Toc473189403" class="anchor"><span id="_Toc473886328" class="anchor"><span id="_Toc474327123" class="anchor"><span id="_Toc474339816" class="anchor"><span id="_Toc479158124" class="anchor"><span id="_Toc479847269" class="anchor"><span id="_Toc487470308" class="anchor"><span id="_Toc492476254" class="anchor"><span id="_Toc493059940" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| &lt;------ ACK [MID=640], 2.05 Content, 2:639/0/128 |</p>
<p><span id="_Toc460336597" class="anchor"><span id="_Toc461094177" class="anchor"><span id="_Toc461197704" class="anchor"><span id="_Toc461617531" class="anchor"><span id="_Toc462231180" class="anchor"><span id="_Toc462843669" class="anchor"><span id="_Toc465694908" class="anchor"><span id="_Toc465754922" class="anchor"><span id="_Toc465772011" class="anchor"><span id="_Toc466534779" class="anchor"><span id="_Toc467143180" class="anchor"><span id="_Toc467678322" class="anchor"><span id="_Toc469902464" class="anchor"><span id="_Toc470163257" class="anchor"><span id="_Toc471907824" class="anchor"><span id="_Toc472076051" class="anchor"><span id="_Toc472088056" class="anchor"><span id="_Toc473189404" class="anchor"><span id="_Toc473886329" class="anchor"><span id="_Toc474327124" class="anchor"><span id="_Toc474339817" class="anchor"><span id="_Toc479158125" class="anchor"><span id="_Toc479847270" class="anchor"><span id="_Toc487470309" class="anchor"><span id="_Toc492476255" class="anchor"><span id="_Toc493059941" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>| |</p>
<p><span id="_Ref467138952" class="anchor"><span id="_Ref460334042" class="anchor"><span id="_Toc492474263" class="anchor"></span></span></span>Figure 31: Example of a client fetching a firmware image</p>
<ol style="list-style-type: upper-alpha">
<li><p><span id="_Toc471907825" class="anchor"><span id="_Toc492476256" class="anchor"><span id="_Toc493059942" class="anchor"></span></span></span>Firmware Update Consideration</p></li>
</ol>
<p>If some Objects are not supported after firmware update, the LwM2M Client MUST delete all Object Instances of the Objects that are not supported.</p></td>
<td></td>
</tr>
</tbody>
</table></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc361854658" class="anchor"><span id="_Toc361855382" class="anchor"><span id="_Toc361854659" class="anchor"><span id="_Toc361855383" class="anchor"><span id="_Toc361854660" class="anchor"><span id="_Toc361855384" class="anchor"><span id="_Toc347941175" class="anchor"><span id="_Ref368312958" class="anchor"><span id="_Ref368313273" class="anchor"><span id="_Toc370916162" class="anchor"><span id="_Toc370922984" class="anchor"><span id="_Toc471907826" class="anchor"><span id="_Toc492476257" class="anchor"><span id="_Toc493059943" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span>LwM2M Object: Location

| | <span id="_Toc370916163" class="anchor"><span id="_Toc370922985" class="anchor"></span></span>**Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |     | 
 |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|  
 | The LwM2M Location Object provides the ability to express a point (in 2d, and in 3d), a circle (in 2d) and a sphere (in 3d). This location information is used to indicate where the LwM2M Client is located at the indicated point in time. A point is used when there is no known uncertainty and it forms part of a number of other geometries. A point may be specified using either world geodetic system (WGS) 84 (latitude, longitude) or WGS 84 (latitude, longitude, altitude). The circular area is used for coordinates in two-dimensional coordinate reference systems (CRSs) to describe uncertainty about a point. It is specified using a two-dimensional CRS (using latitude, longitude). The sphere is a volume that provides the same information as a circle in three dimensions. It is specified using a three-dimensional CRS (using latitude, longitude, and altitude). The use of the world geodetic system 1984 (WGS84) coordinate reference system and the usage of European petroleum survey group (EPSG) code 4326 for two-dimensional (2d) shape representations and EPSG 4979 for three-dimensional (3d) volume representations is mandated. For the circle and the sphere a confidence value of 95% is assumed \[RFC7459\]. Finally, the ability to convey information about moving objects is enabled by expression of speed and velocity. |     |  
 | **Object definition**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |     |  
 | | **Name** | **Object ID** | **Instances** | **Mandatory** | **Object URN**      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 
  |----------|---------------|---------------|---------------|---------------------|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
  | Location | 6             | Single        | Optional      | urn:oma:lwm2m:oma:6 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |     |  
 | **Resource definitions**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |     |  
 | | **ID** | **Name**  | **Operations** | **Instances** | **Mandatory** | **Type** | **Range or Enumeration** | **Units**         | **Description**                                                                                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 
  |--------|-----------|----------------|---------------|---------------|----------|--------------------------|-------------------|--------------------------------------------------------------------------------------------------------------------------------|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
  | 0      | Latitude  | R              | Single        | Mandatory     | Float    |                          | Deg               | The decimal notation of latitude, e.g., -43.5723 \[World Geodetic System 1984\].                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
  | 1      | Longitude | R              | Single        | Mandatory     | Float    |                          | Deg               | The decimal notation of longitude, e.g., 153.21760 \[World Geodetic System 1984\].                                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
  | 2      | Altitude  | R              | Single        | Optional      | Float    |                          | m                 | The decimal notation of altitude in meters above sea level.                                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
  | 3      | Radius    | R              | Single        | Optional      | Float    |                          | m                 | The value in the Radius Resource indicates the size in meters of a circular area around a point geometry.                      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
  | 4      | Velocity  | R              | Single        | Optional      | Opaque   |                          |                   | The velocity of the LwM2M Client is defined in \[3GPP-TS\_23.032\].                                                            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
  | 5      | Timestamp | R              | Single        | Mandatory     | Time     |                          |                   | The timestamp of when the location measurement was performed.                                                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
  | 6      | Speed     | R              | Single        | Optional      | Float    |                          | Meters per second | Speed is the time rate of change in position of a LwM2M Client without regard for direction: the scalar component of velocity. |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |     |  |     |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |     |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |     |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |     |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |     |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |     |

1.  <span id="_Ref368312961" class="anchor"><span id="_Ref368313279" class="anchor"><span id="_Toc370916166" class="anchor"><span id="_Toc370922988" class="anchor"><span id="_Toc471907827" class="anchor"><span id="_Toc492476258" class="anchor"><span id="_Toc351033860" class="anchor"><span id="_Toc493059944" class="anchor"></span></span></span></span></span></span></span></span>LwM2M Object: Connectivity Statistics

| | <span id="_Toc370916167" class="anchor"><span id="_Toc370922989" class="anchor"></span></span>**Description**                                                                                                                                                                                                                                                                                                         |     | 
 |-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|  
 | This LwM2M Objects enables client to collect statistical information and enables the LwM2M Server to retrieve these information, set the collection duration and reset the statistical parameters.                                                                                                                                                                                                                    |     |  
 | **Object definition**                                                                                                                                                                                                                                                                                                                                                                                                 |     |  
 | | **Name**                | **Object ID** | **Instances** | **Mandatory** | **Object URN**      |                                                                                                                                                                                                                                                                                                                              
  |-------------------------|---------------|---------------|---------------|---------------------|                                                                                                                                                                                                                                                                                                                               
  | Connectivity Statistics | 7             | Single        | Optional      | urn:oma:lwm2m:oma:7 |                                                                                                                                                                                                                                                                                                                      |     |  
 | **Resource definitions**                                                                                                                                                                                                                                                                                                                                                                                              |     |  
 | | **ID** | **Name**             | **Operations** | **Instances** | **Mandatory** | **Type** | **Range or Enumeration** | **Units**  | **Description**                                                                                                                                                                                                                                                               |          
  |--------|----------------------|----------------|---------------|---------------|----------|--------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|           
  | 0      | SMS Tx Counter       | R              | Single        | Optional      | Integer  |                          |            | Indicate the total number of SMS successfully transmitted during the collection period.                                                                                                                                                                                       |           
  | 1      | SMS Rx Counter       | R              | Single        | Optional      | Integer  |                          |            | Indicate the total number of SMS successfully received during the collection period.                                                                                                                                                                                          |           
  | 2      | Tx Data              | R              | Single        | Optional      | Integer  |                          | Kilo-Bytes | Indicate the total amount of IP data transmitted during the collection period.                                                                                                                                                                                                |           
  | 3      | Rx Data              | R              | Single        | Optional      | Integer  |                          | Kilo-Bytes | Indicate the total amount of IP data received during the collection period.                                                                                                                                                                                                   |           
  | 4      | Max Message Size     | R              | Single        | Optional      | Integer  |                          | Byte       | The maximum IP message size that is used during the collection period.                                                                                                                                                                                                        |           
  | 5      | Average Message Size | R              | Single        | Optional      | Integer  |                          | Byte       | The average IP message size that is used during the collection period.                                                                                                                                                                                                        |           
  | 6      | Start                | E              | Single        | Mandatory     |          |                          |            | Reset resources 0-5 to 0 and start to collect information, If resource 8 (Collection Period) value is 0, the client will keep collecting information until resource 7 (Stop) is executed, otherwise the client will stop collecting information after specified period ended. |           
  | 7      | Stop                 | E              | Single        | Mandatory     |          |                          |            | Stop collecting information, but do not reset resources 0-5.                                                                                                                                                                                                                  |           
  | 8      | Collection Period    | RW             | Single        | Optional      | Integer  |                          | Seconds    | The default collection period in seconds. The value 0 indicates that the collection period is not set.                                                                                                                                                                        |  |     |  |                                                                                                |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|
|                                                                                                                                                                                                                                                                                                                                                                                                                                 |                                                                                                |
|                                                                                                                                                                                                                                                                                                                                                                                                                                 | <span id="_Toc370916169" class="anchor"><span id="_Toc370922991" class="anchor"></span></span> |
|                                                                                                                                                                                                                                                                                                                                                                                                                                 |                                                                                                |
|                                                                                                                                                                                                                                                                                                                                                                                                                                 | <span id="_Toc370916171" class="anchor"><span id="_Toc370922993" class="anchor"></span></span> |
| Note: When reporting the Tx Data or Rx Data, the LwM2M Client reports the total KB transmitted/received over IP bearer(s), including all protocol header bytes up to and including the IP header. This does not include lower level retransmissions/optimizations (e.g. RAN, header compression) or SMS messages.                                                                                                               |                                                                                                |

1.  <span id="_Ref231282105" class="anchor"><span id="_Ref231283174" class="anchor"><span id="_Toc370916172" class="anchor"><span id="_Toc370922994" class="anchor"><span id="_Toc471907828" class="anchor"><span id="_Toc492476259" class="anchor"><span id="_Toc493059945" class="anchor"></span></span></span></span></span></span></span>Example LwM2M Client (Informative)

This appendix defines an example LwM2M Client for a simple imaginary device with a Cellular interface including instantiated Objects and their values, which is used throughout this specification in examples. The example client has the Endpoint Name “example-client”. The example device has two Server Objects (it is configured to register with two different LwM2M Servers), five accompanying Access Control Object Instances for those servers, a Device Object, a Connectivity Monitoring Object for a Cellular interface and a Firmware Update Object with no instance. The first Server controls the access control rights for both servers.

The Short Server ID 101 & 102, are respectively associated to the Server 1 and Server 2;

|                                    |                |                        |
|------------------------------------|----------------|------------------------|
| **Object**                         | **Object ID ** | **Object Instance ID** |
| **LwM2M Security Object\[0\]**     | 0              | 0                      |
| **LwM2M Security Object\[1\]**     | 0              | 1                      |
| **LwM2M Security Object\[2\]**     | 0              | 2                      |
| **LwM2M Server Object \[1\]**      | 1              | 0                      |
| **LwM2M Server Object \[2\]**      | 1              | 1                      |
| **Access Control Object \[0\]**    | 2              | 0                      |
| **Access Control Object \[1\]**    | 2              | 1                      |
| **Access Control Object \[2\]**    | 2              | 2                      |
| **Access Control Object \[3\]**    | 2              | 3                      |
| **Access Control Object \[4\]**    | 2              | 4                      |
| **Device Object **                 | 3              | 0                      |
| **Connectivity Monitoring Object** | 4              | 0                      |
| **Firmware Update Object**         | 5              | -                      |

<span id="_Toc492475277" class="anchor"></span>Table 29: Object Instances of the example

|                            |                 |                          |                                  |                                                           |
|----------------------------|-----------------|--------------------------|----------------------------------|-----------------------------------------------------------|
| **Resource Name**          | **Resource ID** | **Resource Instance ID** | **Value**                        | **Notes**                                                 |
| **LwM2M Server URI**       | 0               |                          | coaps://bootstrap.example.com    | Example LwM2M Bootstrap-Server                            |
| **Bootstrap-Server**       | 1               |                          | true                             |                                                           |
| **Security Mode**          | 2               |                          | 0                                | PSK mode                                                  |
| **Public Key or Identity** | 3               |                          | b313cc22-f969-42ec-ad42          | Example of a PSK Identity string                          |
| **Server Public Key**      | 4               |                          |                                  | Unused in PSK mode                                        |
| **Secret Key**             | 5               |                          | e129791359950cbb1c8c3c582913b551 | 128-bit random sequence in hex encoding for use as a PSK. |
| **Client Hold Off Time**   | 11              |                          | 3600                             |                                                           |

<span id="_Toc492475278" class="anchor"></span>Table 30: LwM2M Security Object \[0\]

|                            |                 |                          |                                  |                                                           |
|----------------------------|-----------------|--------------------------|----------------------------------|-----------------------------------------------------------|
| **Resource Name**          | **Resource ID** | **Resource Instance ID** | **Value**                        | **Notes**                                                 |
| **LwM2M Server URI**       | 0               |                          | coaps://server1.example.com      | Example LwM2M Server 1                                    |
| **Bootstrap-Server**       | 1               |                          | false                            |                                                           |
| **Security Mode**          | 2               |                          | 0                                | PSK mode                                                  |
| **Public Key or Identity** | 3               |                          | b313cc22-f969-42ec-ad42          | Example of a PSK Identity string                          |
| **Server Public Key**      | 4               |                          |                                  | Unused in PSK mode                                        |
| **Secret Key**             | 5               |                          | 1ca2028d7197c778e9aef5ef69082bea | 128-bit random sequence in hex encoding for use as a PSK. |
| **Short Server ID**        | 10              |                          | 101                              |                                                           |

<span id="_Toc492475279" class="anchor"></span>Table 31: LwM2M Security Object \[1\]

|                            |                 |                          |                             |                                                                                                                                        |
|----------------------------|-----------------|--------------------------|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Resource Name**          | **Resource ID** | **Resource Instance ID** | **Value**                   | **Notes**                                                                                                                              |
| **LwM2M Server URI**       | 0               |                          | coaps://server2.example.com | Example LwM2M Server 2                                                                                                                 |
| **Bootstrap-Server**       | 1               |                          | false                       |                                                                                                                                        |
| **Security Mode**          | 2               |                          | 1                           | RPK mode                                                                                                                               |
| **Public Key or Identity** | 3               |                          | 3059301306072a8648ce        
                                 
    3d020106082a8648ce3d         
                                 
    03010703420004a09dcb         
                                 
    1bc739e7f19afa9adcb1         
                                 
    944968bfba73efcec29b         
                                 
    50486eb44d1b29c19344         
                                 
    9970a3736830cb2bd5d7         
                                 
    ec05d2bd1fc07b6df5e4         
                                 
    8b54ce77a6a7229c3a91         
                                 
    c2                           | The raw public key of the LwM2M Client in ASN.1 DER format. The textual representation of the key can be found below labelled as \*.   |
| **Server Public Key**      | 4               |                          | 3059301306072a8648ce        
                                 
    3d020106082a8648ce3d         
                                 
    0301070342000482c773         
                                 
    f378d30c2783a48eb811         
                                 
    b96cf6a90694a8564f1e         
                                 
    7f6d366152f11698950f         
                                 
    6f7c40cda585334f8377         
                                 
    50a102f5bf25508ceb9e         
                                 
    55dfc0f12a455199a4c9         
                                 
    60                           | The raw public key of the LwM2M Server in ASN.1 DER format. The textual representation of the key can be found below labelled as \*\*. |
| **Secret Key**             | 5               |                          | 307702010104209f352d        
                                 
    a16495748e146fcb5370         
                                 
    b8e96d292ced5567a8fa         
                                 
    e55a22bb67d91651b8a0         
                                 
    0a06082a8648ce3d0301         
                                 
    07a14403420004a09dcb         
                                 
    1bc739e7f19afa9adcb1         
                                 
    944968bfba73efcec29b         
                                 
    50486eb44d1b29c19344         
                                 
    9970a3736830cb2bd5d7         
                                 
    ec05d2bd1fc07b6df5e4         
                                 
    8b54ce77a6a7229c3a91         
                                 
    c2                           | The private key of the client in PKCS\#8 format. The textual representation of the key can be found below labelled as \*\*\*.          |
| **Short Server ID**        | 10              |                          | 102                         |                                                                                                                                        |

<span id="_Toc492475280" class="anchor"></span>Table 32: LwM2M Security Object \[2\]

> \*: The client public key in text representation:
>
>   0  89: SEQUENCE {
>
>  2  19:   SEQUENCE {
>
>  4   7:     OBJECT IDENTIFIER ecPublicKey (1 2 840 10045 2 1)
>
> 13   8:     OBJECT IDENTIFIER prime256v1 (1 2 840 10045 3 1 7)
>
>       :     }
>
> 23  66:   BIT STRING
>
>       :     04 A0 9D CB 1B C7 39 E7 F1 9A FA 9A DC B1 94 49
>
>       :     68 BF BA 73 EF CE C2 9B 50 48 6E B4 4D 1B 29 C1
>
>       :     93 44 99 70 A3 73 68 30 CB 2B D5 D7 EC 05 D2 BD
>
>       :     1F C0 7B 6D F5 E4 8B 54 CE 77 A6 A7 22 9C 3A 91
>
>       :     C2
>
>       :   }
>
> \*\*: The server public key in text representation:
>
> 0  89: SEQUENCE {
>
>  2  19:   SEQUENCE {
>
>  4   7:     OBJECT IDENTIFIER ecPublicKey (1 2 840 10045 2 1)
>
> 13   8:     OBJECT IDENTIFIER prime256v1 (1 2 840 10045 3 1 7)
>
>       :     }
>
> 23  66:   BIT STRING
>
>       :     04 82 C7 73 F3 78 D3 0C 27 83 A4 8E B8 11 B9 6C
>
>       :     F6 A9 06 94 A8 56 4F 1E 7F 6D 36 61 52 F1 16 98
>
>       :     95 0F 6F 7C 40 CD A5 85 33 4F 83 77 50 A1 02 F5
>
>       :     BF 25 50 8C EB 9E 55 DF C0 F1 2A 45 51 99 A4 C9
>
>       :     60
>
>       :   }
>
> \*\*\*: The client private key in text representation:
>
> 0 119: SEQUENCE {
>
>  2   1:   INTEGER 1
>
>  5  32:   OCTET STRING
>
>       :     9F 35 2D A1 64 95 74 8E 14 6F CB 53 70 B8 E9 6D
>
>       :     29 2C ED 55 67 A8 FA E5 5A 22 BB 67 D9 16 51 B8
>
> 39  10:   \[0\] {
>
> 41   8:     OBJECT IDENTIFIER prime256v1 (1 2 840 10045 3 1 7)
>
>       :     }
>
> 51  68:   \[1\] {
>
> 53  66:     BIT STRING
>
>       :       04 A0 9D CB 1B C7 39 E7 F1 9A FA 9A DC B1 94 49
>
>       :       68 BF BA 73 EF CE C2 9B 50 48 6E B4 4D 1B 29 C1
>
>       :       93 44 99 70 A3 73 68 30 CB 2B D5 D7 EC 05 D2 BD
>
>       :       1F C0 7B 6D F5 E4 8B 54 CE 77 A6 A7 22 9C 3A 91
>
>       :       C2
>
>       :     }
>
>       :   }

|                                                   |                 |                          |           |                        |
|---------------------------------------------------|-----------------|--------------------------|-----------|------------------------|
| **Resource Name**                                 | **Resource ID** | **Resource Instance ID** | **Value** | **Notes**              |
| **Short Server ID**                               | 0               |                          | 101       | Example LwM2M Server 1 |
| **Lifetime**                                      | 1               |                          | 86400     |                        |
| **Default Minimum Period**                        | 2               |                          | 300       |                        |
| **Default Maximum Period**                        | 3               |                          | 6000      |                        |
| **DisableTimeout**                                | 5               |                          | 86400     |                        |
| **Notification Storing When Disabled or Offline** | 6               |                          | True      |                        |
| **Binding Preference**                            | 7               |                          | U         | UDP binding preference |

<span id="_Toc492475281" class="anchor"></span>Table 33: LwM2M Server Object \[0\]

|                                                   |                 |                          |           |                                     |
|---------------------------------------------------|-----------------|--------------------------|-----------|-------------------------------------|
| **Resource Name**                                 | **Resource ID** | **Resource Instance ID** | **Value** | **Notes**                           |
| **Short Server ID**                               | 0               |                          | 102       | Example LwM2M Server 2              |
| **Lifetime**                                      | 1               |                          | 86400     |                                     |
| **Default Minimum Period**                        | 2               |                          | 60        |                                     |
| **Default Maximum Period**                        | 3               |                          | 6000      |                                     |
| **DisableTimeout**                                | 5               |                          | 86400     |                                     |
| **Notification Storing When Disabled or Offline** | 6               |                          | False     |                                     |
| **Binding Preference**                            | 7               |                          | UQ        | UDP with Queuing binding preference |

<span id="_Toc492475282" class="anchor"></span>Table 34: LwM2M Server Object \[1\]

|                          |                 |                          |                    |                                                                                                                                            |
|--------------------------|-----------------|--------------------------|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| **Resource Name**        | **Resource ID** | **Resource Instance ID** | **Value**          | **Notes**                                                                                                                                  |
| **Object ID**            | 0               |                          | 1                  | LwM2M Server Object 0 (Server 1)                                                                                                           |
| **Object Instance ID**   | 1               |                          | 0                  |                                                                                                                                            |
| **ACL**                  | 2               | 101                      | 0b0000000000001111 | For this Object Instance (1:0), Server 1 has access rights (R, W, E, D). Note that the Resource Instance ID indicates the Short Server ID. |
| **Access Control Owner** | 3               |                          | 101                | Server 1 controls this Object Instance’s access rights.                                                                                    |

<span id="_Toc369360019" class="anchor"><span id="_Toc492475283" class="anchor"></span></span>Table 35: Access Control Object \[0\] (for the LwM2M Server Object Instance 0)

|                          |                 |                          |                    |                                                                                                                                            |
|--------------------------|-----------------|--------------------------|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| **Resource Name**        | **Resource ID** | **Resource Instance ID** | **Value**          | **Notes**                                                                                                                                  |
| **Object ID**            | 0               |                          | 1                  | LwM2M Server Object 1                                                                                                                      
                                                                                                                                                 
     (Server 2)                                                                                                                                  |
| **Object Instance ID**   | 1               |                          | 1                  |                                                                                                                                            |
| **ACL**                  | 2               | 102                      | 0b0000000000001111 | For this Object Instance (1:1), Server 2 has access rights (R, W, E, D). Note that the Resource Instance ID indicates the Short Server ID. |
| **Access Control Owner** | 3               |                          | 102                | Server 2 controls this Object Instance’s access rights.                                                                                    |

<span id="_Toc369360020" class="anchor"><span id="_Toc492475284" class="anchor"></span></span>Table 36: Access Control Object \[1\] (for the LwM2M Server Object Instance 1)

|                          |                 |                          |                    |                                                                                                                                            |
|--------------------------|-----------------|--------------------------|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| **Resource Name**        | **Resource ID** | **Resource Instance ID** | **Value**          | **Notes**                                                                                                                                  |
| **Object ID**            | 0               |                          | 3                  | Device Object                                                                                                                              |
| **Object Instance ID**   | 1               |                          | 0                  |                                                                                                                                            |
| **ACL**                  | 2               | 101                      | 0b0000000000001111 | For this Object Instance (3:0), Server 1 has access rights (R, W, E, D). Note that the Resource Instance ID indicates the Short Server ID. |
| **ACL**                  | 2               | 102                      | 0b0000000000000001 | For this Object Instance (3:0), Server 2 has read-only access rights. Note that the Resource Instance ID indicates the Short Server ID.    |
| **Access Control Owner** | 3               |                          | 101                | Server 1 controls this Object Instance’s access rights.                                                                                    |

<span id="_Toc492475285" class="anchor"></span>Table 37: Access Control Object \[2\] (for the Device Object Instance)

|                          |                 |                          |                    |                                                                                                                                                                          |
|--------------------------|-----------------|--------------------------|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Resource Name**        | **Resource ID** | **Resource Instance ID** | **Value**          | **Notes**                                                                                                                                                                |
| **Object ID**            | 0               |                          | 4                  | Connectivity Monitoring Object                                                                                                                                           |
| **Object Instance ID**   | 1               |                          | 0                  |                                                                                                                                                                          |
| **ACL**                  | 2               | 101                      | 0b0000000000000001 | For this Object Instance (4:0), Server 1 has read-only access rights. Note that the Resource Instance ID indicates the Short Server ID.                                  |
| **ACL**                  | 2               | 0                        | 0b0000000000000001 | For this Object Instance (4:0), The other Servers except Server 1 have read-only access rights. Note that this Resource Instance ID indicates the default access rights. |
| **Access Control Owner** | 3               |                          | 101                | Server 1 controls this Object Instance’s access rights.                                                                                                                  |

<span id="_Toc492475286" class="anchor"></span>Table 38: Access Control Object \[3\] (for the Connectivity Monitoring Object Instance)

|                          |                 |                          |                    |                                                             |
|--------------------------|-----------------|--------------------------|--------------------|-------------------------------------------------------------|
| **Resource Name**        | **Resource ID** | **Resource Instance ID** | **Value**          | **Notes**                                                   |
| **Object ID**            | 0               |                          | 5                  | Firmware Update Object                                      |
| **Object Instance ID**   | 1               |                          | 65535              | Irrelevant                                                  |
| **ACL**                  | 2               | 101                      | 0b0000000000010000 | Server 1 can create Firmware Update Object Instance         |
| **Access Control Owner** | 3               |                          | 65535              | This Object Instance must be managed by Bootstrap Interface |

<span id="_Toc492475287" class="anchor"></span>Table 39: Access Control Object \[4\] (for the Firmware Update Object)

|                             |                 |                          |                        |                                          |
|-----------------------------|-----------------|--------------------------|------------------------|------------------------------------------|
| **Resource Name**           | **Resource ID** | **Resource Instance ID** | **Value**              | **Notes**                                |
| Manufacturer                | 0               |                          | Open Mobile Alliance   |                                          |
| Model Number                | 1               |                          | Lightweight M2M Client |                                          |
| Serial Number               | 2               |                          | 345000123              |                                          |
| Firmware version            | 3               |                          | 1.0                    |                                          |
| Available Power Sources     | 6               | 0                        | 1                      | Internal Battery                         |
| Available Power Sources     | 6               | 1                        | 5                      | USB                                      |
| Power Source Voltage        | 7               | 0                        | 3800                   | 3.8V battery                             |
| Power Source Voltage        | 7               | 1                        | 5000                   | USB VBUS                                 |
| Power Source Current        | 8               | 0                        | 125                    | 125mA                                    |
| Power Source Current        | 8               | 1                        | 900                    | USB 900mA                                |
| Battery level               | 9               |                          | 100                    |                                          |
| Memory free                 | 10              |                          | 15                     | 15 kB of free memory                     |
| Error code                  | 11              | 0                        | 0                      | No errors                                |
| Current Time                | 13              |                          | 1367491215             | May 2<sup>nd</sup>, 2013 at 11:42 AM GMT |
| UTC Offset                  | 14              |                          | +02:00                 | UTC+2 (CET)                              |
| Supported Binding and Modes | 16              |                          | U                      | UDP binding                              |

<span id="_Toc492475288" class="anchor"></span>Table 40: Device Object Instance

|                          |                 |                          |               |                 |
|--------------------------|-----------------|--------------------------|---------------|-----------------|
| **Resource Name**        | **Resource ID** | **Resource Instance ID** | **Value**     | **Notes**       |
| Network Bearer           | 0               |                          | 0             | GSM Bearer      |
| Available Network Bearer | 1               |                          | 0             | GSM Bearer      |
| Radio signal strength    | 2               |                          | 92            | RSSI in dBm     |
| Link Quality             | 3               |                          | 2             | RxQual Downlink |
| IP Addresses             | 4               | 0                        | 192.168.0.100 |                 |
| Router IP Addresses      | 5               | 0                        | 192.168.1.1   |                 |
| Link Utilization         | 6               |                          | 5             | %               |
| APN                      | 7               | 0                        | internet      |                 |

<span id="_Toc492475289" class="anchor"></span>Table 41: Connectivity Monitoring Object Instance

1.  <span id="_Ref303177048" class="anchor"><span id="_Toc314837644" class="anchor"><span id="_Toc336982053" class="anchor"><span id="_Ref368263092" class="anchor"><span id="_Ref368310755" class="anchor"><span id="_Ref368312865" class="anchor"><span id="_Toc370916173" class="anchor"><span id="_Toc370922995" class="anchor"><span id="_Toc471907829" class="anchor"><span id="_Toc492476260" class="anchor"><span id="_Toc493059946" class="anchor"></span></span></span></span></span></span></span></span></span></span></span>Storage of LwM2M Bootstrap Information on the Smartcard (Normative)

This appendix aims at specifying the storage mechanism of Bootstrap Information on UICC Smartcard platform type \[ETSI TS 102.221\] activated in 3G mode.

Note: There is no rational to equip LwM2M device with 2G-only Smart Card.

1.  <span id="_Toc314837645" class="anchor"><span id="_Toc336982054" class="anchor"><span id="_Toc370916174" class="anchor"><span id="_Toc370922996" class="anchor"><span id="_Toc471907830" class="anchor"><span id="_Toc492476261" class="anchor"><span id="_Toc493059947" class="anchor"></span></span></span></span></span></span></span>File structure

The information format is based on \[PKCS\#15\] specification. The Bootstrap data is located under the PKCS\#15 directory allowing the card issuer to decide the identifiers and the file locations. The smartcard operations that are relevant include:

-   Application selection

-   Cardholder verification

-   File access (select file, read, write)

The \[PKCS\#15\] specification defines a set of files. Within the PKCS\#15 application, the starting point to access these files is the Object Directory File (ODF). The EF (ODF) contains pointers to other directory files. These directory files contain information on different types of objects (authentication objects, data objects, etc.). For the purpose of Bootstrap data, EF (ODF) MUST contain the EF Record describing the DODF-bootstrap. The EF (ODF) is described in Appendix G.3.1 and \[PKCS\#15\].

EF (ODF) contains pointers to one or more Data Object Directory Files (DODF) in priority order (i.e. the first DODF has the highest priority). Each DODF is regarded as the directory of data objects known to the PKCS\#15 application. For the purposes of LwM2M bootstrapping, EF (DODF-bootstrap) contains pointer to the Bootstrap data, namely LwM2M\_Bootstrap File. The EF (DODF-bootstrap) is described in Appendix G.3.2 and \[PKCS\#15\].

The provisioning files are stored as PKCS\#15 opaque data objects.<span id="_Object_Directory_File," class="anchor"></span>

The support of smartcard Bootstrap data will be indicated by the presence in the EF DIR (see \[ETSI TS 102.221\]) of an application template as defined here after.

The RECOMMENDED format of EF (DIR) is a linear fixed record in order to be in line with \[ETSI TS 102.221\].

EF (DIR) MUST contain the application template used for a PKCS\#15 application as defined in \[PKCS\#15\]. Application template MUST consist of Application identifier (tag 0x4F) and Path (tag 0x51) information.

The EF (ODF) and EF (DODF-bootstrap) MUST be used by the Device to determine the path of the LwM2M\_Bootstrap file.

UICC Smartcard platforms can support two modes of activation: 2G and 3G. In the context of LwM2M, for Device simplification, UICC MUST be activated in 3G Mode

UICC smartcard platform activated in a 3G mode has the physical and logical characteristics according to \[ETSI TS 102.221\]. In that case, smartcard operations for accessing the Bootstrap data are specified in Appendix G.2.

1.  <span id="_Access_Method_1" class="anchor"><span id="_Ref368313790" class="anchor"><span id="_Toc370916175" class="anchor"><span id="_Toc370922997" class="anchor"><span id="_Toc471907831" class="anchor"><span id="_Toc492476262" class="anchor"><span id="_Toc493059948" class="anchor"></span></span></span></span></span></span></span>Bootstrap Information on UICC (Activated in 3G Mode)

2.  <span id="_WAP_provisioning_data_2" class="anchor"><span id="_Toc314837653" class="anchor"><span id="_Ref315802566" class="anchor"><span id="_Toc336982062" class="anchor"><span id="_Toc370916176" class="anchor"><span id="_Toc370922998" class="anchor"><span id="_Toc471907832" class="anchor"><span id="_Toc492476263" class="anchor"><span id="_Toc493059949" class="anchor"></span></span></span></span></span></span></span></span></span>Access to the file structure

To select the PKCS\#15 application, the Device:

-   MUST evaluate the PKCS\#15 application template – i.e. PKCS\#15 AID - present in the EF (DIR),

-   MUST open a logical channel using UICC Command MANAGE CHANNEL as specified in \[ETSI TS 102.221\],

-   MUST select the PKCS\#15 ADF using the PKCS\#15 AID as parameter of the UICC Command SELECT, using direct application selection as defined in \[ETSI TS 102.221\].

LwM2M\_Bootstrap file will be located under the PKCS\#15 ADF.

1.  <span id="_Toc314837654" class="anchor"><span id="_Toc336982063" class="anchor"><span id="_Toc370916177" class="anchor"><span id="_Toc370922999" class="anchor"><span id="_Toc471907833" class="anchor"><span id="_Toc492476264" class="anchor"><span id="_Toc493059950" class="anchor"></span></span></span></span></span></span></span>Files Overview

<span id="_Toc492474264" class="anchor"></span>Figure 32: 3G UICC File Structure and Bootstrap data location

1.  <span id="_Access_Method_2" class="anchor"><span id="_Toc314837655" class="anchor"><span id="_Toc336982064" class="anchor"><span id="_Toc370916178" class="anchor"><span id="_Toc370923000" class="anchor"><span id="_Toc471907834" class="anchor"><span id="_Toc492476265" class="anchor"><span id="_Toc493059951" class="anchor"></span></span></span></span></span></span></span></span>Access Method

UICC Commands Read Binary and Update Binary, as defined in \[ETSI TS 102.221\], are used to access bootstrap data.

1.  <span id="_Toc314837656" class="anchor"><span id="_Toc336982065" class="anchor"><span id="_Toc370916179" class="anchor"><span id="_Toc370923001" class="anchor"><span id="_Toc471907835" class="anchor"><span id="_Toc492476266" class="anchor"><span id="_Toc493059952" class="anchor"></span></span></span></span></span></span></span>Access Conditions<span id="_Ref14062026" class="anchor"><span id="_Toc14064519" class="anchor"><span id="_Ref18840974" class="anchor"><span id="_Toc20227479" class="anchor"><span id="_Toc314837657" class="anchor"><span id="_Toc336982066" class="anchor"></span></span></span></span></span></span>

The Device is informed of the access conditions of provisioning files by evaluating the “private” and “modifiable” flags in the corresponding DODF-bootstrap files structure.

In the case where one of the above mentioned flag is set, cardholder verification is required. The Device must evaluate the PIN references that must be verified as defined in \[ETSI TS 102.221\] (i.e. evaluate FCP)

1.  <span id="_Toc370916180" class="anchor"><span id="_Toc370923002" class="anchor"><span id="_Toc471907836" class="anchor"><span id="_Toc492476267" class="anchor"><span id="_Toc493059953" class="anchor"></span></span></span></span></span>Requirements on the 3G UICC

To retrieve the Bootstrap Information from the 3G UICC, the Device MUST perform the following steps:

-   Select PKCS\#15 file structure as specified in G.2.1.

-   Read ODF to locate the DODF-bootstrap,

-   Read DODF-bootstrap to locate the LwM2M\_Bootstrap file,

-   Read the LwM2M\_Bootstrap file

1.  <span id="_Toc470597947" class="anchor"><span id="_Toc14064508" class="anchor"><span id="_Ref18816318" class="anchor"><span id="_Ref18826404" class="anchor"><span id="_Ref18838600" class="anchor"><span id="_Toc20227468" class="anchor"><span id="_Toc314837658" class="anchor"><span id="_Toc336982067" class="anchor"><span id="_Toc370916181" class="anchor"><span id="_Toc370923003" class="anchor"><span id="_Toc471907837" class="anchor"><span id="_Toc492476268" class="anchor"><span id="_Toc493059954" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span>Files Description

All files defined are binary files as defined in \[**ETSI TS 102.221**\]. These files are read and updated using 3G UICC Commands related to the application they belong to.

1.  <span id="_EF_ODF" class="anchor"><span id="_Ref10622547" class="anchor"><span id="_Ref10622835" class="anchor"><span id="_Ref10623302" class="anchor"><span id="_Ref10624530" class="anchor"><span id="_Ref14003395" class="anchor"><span id="_Ref14057598" class="anchor"><span id="_Toc14064509" class="anchor"><span id="_Toc20227469" class="anchor"><span id="_Toc314837659" class="anchor"><span id="_Toc336982068" class="anchor"><span id="_Toc370916182" class="anchor"><span id="_Toc370923004" class="anchor"><span id="_Toc471907838" class="anchor"><span id="_Toc492476269" class="anchor"><span id="_Toc493059955" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>Object Directory File, EF ODF

The mandatory Object Directory File (ODF) (\[PKCS\#15\], Section 5.5.1) contains pointers to other EFs, each one containing a directory of PKCS\#15 objects of a particular class (e.g., DODF-bootstrap). The File ID is specified in \[PKCS\#15\]. The card issuer decides the file size. The EF (ODF) can be read but it MUST NOT be modifiable by the user.

The EF (ODF) is described below:

|                                              |                      |           |
|----------------------------------------------|----------------------|-----------|
| Identifier: default 0x5031, see \[PKCS\#15\] | Structure: Binary    | Mandatory |
| File size: decided by the card issuer        | Update activity: low |
| Access Conditions:                           
                                               
 > READ ALW                                    
                                               
 UPDATE ADM                                    
                                               
 INVALIDATE ADM                                
                                               
 REHABILITATE ADM                              |
| Description                                  |
| See \[PKCS\#15\]                             |

1.  <span id="_EF_CDF" class="anchor"><span id="_EF_DODF-prov" class="anchor"><span id="_Ref10622536" class="anchor"><span id="_Ref10622827" class="anchor"><span id="_Ref10623388" class="anchor"><span id="_Ref14003639" class="anchor"><span id="_Ref14057660" class="anchor"><span id="_Toc14064489" class="anchor"><span id="_Toc20227449" class="anchor"><span id="_Ref10622526" class="anchor"><span id="_Ref10622813" class="anchor"><span id="_Ref10623369" class="anchor"><span id="_Ref14003650" class="anchor"><span id="_Ref14057671" class="anchor"><span id="_Toc14064511" class="anchor"><span id="_Toc20227471" class="anchor"><span id="_Toc314837660" class="anchor"><span id="_Toc336982069" class="anchor"><span id="_Ref368313748" class="anchor"><span id="_Toc370916183" class="anchor"><span id="_Toc370923005" class="anchor"><span id="_Toc471907839" class="anchor"><span id="_Toc492476270" class="anchor"><span id="_Toc493059956" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>Bootstrap Data Object Directory File, EF DODF-bootstrap

This Data Object Directory File provisioning contains directories of provisioning data objects (\[PKCS\#15\], Section 6.7) known to the \[PKCS\#15\] application.

The File ID is described in the EF (ODF). The file size depends on the number of provisioning objects stored in the smartcard. Thus, the card issuer decides the file size.

|                                                                   |                      |           |
|-------------------------------------------------------------------|----------------------|-----------|
| Identifier: 0x6430, See ODF                                       | Structure: Binary    | Mandatory |
| File size: decided by the card issuer                             | Update activity: low |
| Access Conditions:                                                
 >                                                                  
 > READ ALW                                                         
 >                                                                  
 > or Universal / application / Local PIN (UICC, See Appendix G.2)  
                                                                    
 UPDATE ADM                                                         
                                                                    
 INVALIDATE ADM                                                     
                                                                    
 REHABILITATE ADM                                                   |
| Description                                                       |
| See hereafter and \[PKCS\#15\]                                    |

The EF (DODF-bootstrap) MUST contain information on provisioning objects:

-   Readable label describing the provisioning document (CommonObjectAttributes.label). The ME could display this label to the user.

-   Flags indicating whether the provisioning document is private (i.e., is protected with a PIN) and/or modifiable (CommonObjectAttributes.flags). The card issuer decides whether or not a file is private (it does not need to be if it does not contain any sensitive information)

-   Object identifier indicating a LwM2M boostrap Object and the type of the provisioning object (CommonDataObjectAttributes.applicationOID)

-   Pointer to the contents of the provisioning document (Path.path)

1.  <span id="_EF_Bootstrap" class="anchor"><span id="_Toc470597948" class="anchor"><span id="_Ref10622506" class="anchor"><span id="_Ref10622772" class="anchor"><span id="_Ref10623422" class="anchor"><span id="_Ref14056801" class="anchor"><span id="_Ref14057709" class="anchor"><span id="_Toc14064512" class="anchor"><span id="_Toc20227472" class="anchor"><span id="_Toc314837661" class="anchor"><span id="_Toc336982070" class="anchor"><span id="_Toc370916184" class="anchor"><span id="_Toc370923006" class="anchor"><span id="_Toc471907840" class="anchor"><span id="_Toc492476271" class="anchor"><span id="_Toc493059957" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>EF LwM2M\_Bootstrap

Only the card issuer can modify EF LwM2M\_Bootstrap

|                                                                   |                      |          |
|-------------------------------------------------------------------|----------------------|----------|
| Identifier: See DODF                                              | Structure: Binary    | Optional |
| File size: decided by the card issuer                             | Update activity: low |
| Access Conditions:                                                
                                                                    
 > READ ALW                                                         
 >                                                                  
 > or Universal / application / Local PIN (UICC, See Appendix G.2)  
 >                                                                  
 > UPDATE ADM                                                       
 >                                                                  
 > INVALIDATE ADM                                                   
 >                                                                  
 > REHABILITATE ADM                                                 |
| Description                                                       |
| Contains Bootstrap data (encapsulated LwM2M Objects)              |

This file size is limited to 32KB; the effective file size, in Bytes, is accessible from the File header.

In this file, the Bootstrap data relies on LwM2M TLV Data format specification.

The LwM2M specification already describes the TLV format for coding multiples instances and Resources of a given Object (§6.4.3), this section will only detailed how to store a collection of LwM2M Objects in this EF LwM2M\_Bootstrap file; each Object is coded with a header containing a LwM2M Object ID and its Object Version coded in one or 2 Bytes, a LwM2M-TLV coding the Object Instances as payload, and a length being the size in bytes of this payload (LwM2M-TLV of the Object Instances). Data are represented in network byte order (big endian).

Additionally, this Bootstrap data will have a 2 Byte header indicating the number of Objects contained in that file and another 2 Bytes for indicating the size of the full payload (size of the collection of LwM2M Objects).

Using a BNF-like description:

&lt;bootstrap\_data&gt; ::= &lt;number of objects&gt; &lt;size&gt; &lt;collection\_of\_lwm2m\_objects&gt;

&lt;number of Objects&gt; ::= HWORD

&lt;size&gt; ::= HWORD

&lt;collection\_of\_lwm2m\_objects&gt; ::= &lt;single\_lwm2m\_object&gt;\*

&lt;single\_lwm2m\_object&gt; ::= &lt;lwm2m\_object\_ID&gt; &lt;object\_version&gt; &lt;length\_of\_object&gt; &lt;lwm2m\_object\_instances&gt;

&lt;lwm2m\_object\_ID&gt; ::= HWORD

&lt;object\_version&gt; ::= IMPLICIT\_VERSION | &lt;other\_version&gt;

&lt;other\_version&gt; ::= MAJOR\_VERSION MINOR\_VERSION ; value %x0205 means version 2.5

&lt;length\_of\_object&gt; ::= HWORD

&lt;lwm2m\_object\_instances&gt; ::= TLV data format as described in §147138816.6.4.3

HWORD ::= %x00-FFFF

IMPLICIT\_VERSION ::= %x00 ; means version 1.0 or the Object is defined in the LwM2M Enabler

MAJOR\_VERSION ::= %x01-FF

MINOR VERSION ::= %x00-FF

In reading and processing the data of this file, the LwM2M Client is then able to be configured with the Bootstrap Information and thus to access the LwM2M Server(s).

1.  <span id="_Toc370916185" class="anchor"><span id="_Toc370923007" class="anchor"></span></span>
    <span id="_Ref467136907" class="anchor"><span id="_Toc471907841" class="anchor"><span id="_Toc492476272" class="anchor"><span id="_Toc493059958" class="anchor"></span></span></span></span>Secure channel between Smartcard and LwM2M Device Storage for secure Bootstrap Data provisioning (Normative)

During LwM2M Bootstrap procedure, sensitive data have to be provisioned in LwM2M Device.

When Bootstrap information comes from Smartcard, a secure channel SHOULD be established. When required this secure channel MUST follow the following procedure based on \[GLOBALPLATFORM\] \[GP SCP03\] which is illustrated below. The Bootstrap information will be retrieved from Smartcard as described in Appendix F of this document but in including the channel securisation.

Pre-requisite: the Smartcard and the LwM2M device have to share the same static Keys KEY\_ENC, KEY\_MAC, KEY\_DEK as specified in \[GLOBALPLATFORM\] \[GP SCP03\]

These keys are provisioned in the devices in using out-of-band methods.

The steps for the secure transfer are the following and are illustrated below (Figure 33):

-   The PKSC\#15 application used for transferring the Bootstrap information is selected

-   Secure channel (mutual authentication) is established

-   PKCS\#15 flow as described in Appendix F takes place for selecting and transferring the Bootstrap file from Smartcard to the device: the sensitive Bootstrap data are transferred crypted.

<span id="_Ref474364852" class="anchor"><span id="_Toc492474265" class="anchor"></span></span>Figure 33: Bootstrap Information transfer from Smartcard to LwM2M Device using Secure channel according to \[GLOBALPLATFORM\] \[GP SCP03\] \[GP AMD\_A\]

Note 1: The INITIALIZE\_UPDATE specifies the logical channel to use (CLA: 80H / 83H)

Note 2: The security level (P1) of the EXTERNAL\_AUTH command is C-DECRYPTION, R-ENCRYPTION, C-MAC and R-MAC (P1=0x33)

1.  <span id="_Toc178566090" class="anchor"><span id="_Toc222822654" class="anchor"></span></span>
    <span id="_Toc471907842" class="anchor"><span id="_Toc492476273" class="anchor"><span id="_Toc493059959" class="anchor"></span></span></span>Media types

2.  <span id="_Toc178566091" class="anchor"><span id="_Toc222822655" class="anchor"><span id="_Toc471907843" class="anchor"><span id="_Toc492476274" class="anchor"><span id="_Toc493059960" class="anchor"></span></span></span></span></span>Media-Type application/vnd.oma.lwm2m+tlv Registration

This section contains the IANA registration for media-type application/vnd.oma.lwm2m+tlv (see <http://www.iana.org/assignments/media-types/media-types.xhtml>).

Type name: application

Subtype name: vnd.oma.lwm2m+tlv

Required parameters: none

Optional parameters: none

Encoding considerations: binary

Security considerations:

> OMA LwM2M data is passive, meaning it does not contain executable or active content which may represent a security threat. The OMA LwM2M TLV format does not contain fields which are confidential. The usage of the LwM2M TLV format may be vulnerable to attacks modifying or spoofing the content of this format. The OMA LwM2M protocol uses source authentication and integrity protection.
>
> This media type inherits the security issues associated with the TLV format.

Interoperability considerations:

> This content type carries OMA LwM2M data model serialization within the scope of the OMA LwM2M enabler. The OMA LwM2M enabler specification includes static conformance requirements for this content.

Published specification:

> OMA LwM2M 1.0 Technical Specification – especially section 6.4.3. Available from <http://www.openmobilealliance.org>

Applications, which use this media type:

> OMA LwM2M

Fragment identifier considerations: none

Additional information:

-   Deprecated alias names for this type: none

-   Magic number(s): none

-   File extension(s): none

-   Macintosh File Type Code(s): none

Intended usage: Limited use. Only for usage with OMA LwM2M, which meet the semantics given in the mentioned specification.

Restriction on usage: no

Person & email address to contact for further information:

> John Mudge
>
> <helpdesk@omaorg.org>

Author/Change controller:

> Open Mobile Naming Authority (OMNA)
>
> <OMA-OMNA@mail.openmobilealliance.org>

Provisional registration (standards tree only): N/A

1.  <span id="_Toc471907844" class="anchor"><span id="_Toc492476275" class="anchor"><span id="_Toc493059961" class="anchor"></span></span></span>Media-Type application/vnd.oma.lwm2m+json Registration

This section contains the IANA registration for media-type application/vnd.oma.lwm2m+json (see <http://www.iana.org/assignments/media-types/media-types.xhtml>).

Type name: application

Subtype name: vnd.oma.lwm2m+json

Required parameters: none

Optional parameters: none

Encoding considerations: Encoding considerations are identical to those specified for the "application/json" media type.

See RFC7159.

Security considerations:

> OMA LwM2M data is passive, meaning it does not contain executable or active content which may represent a security threat. The OMA LwM2M JSON format does not contain fields which are confidential. The usage of the LwM2M JSON format may be vulnerable to attacks modifying or spoofing the content of this format. The OMA LwM2M protocol uses source authentication and integrity protection.

Interoperability considerations:

> This content type carries OMA LwM2M data model serialization within the scope of the OMA LwM2M enabler. The OMA LwM2M enabler specification includes static conformance requirements for this content.

Published specification:

> OMA LwM2M 1.0 Technical Specification – especially section 6.4.4. Available from <http://www.openmobilealliance.org>

Applications which use this media type:

> OMA LwM2M

Fragment identifier considerations: none

Additional information:

-   Deprecated alias names for this type: none

-   Magic number(s): none

-   File extension(s): none

-   Macintosh File Type Code(s): none

Intended usage: Limited use. Only for usage with OMA LwM2M, which meet the semantics given in the mentioned specification.

Restriction on usage: no

Person & email address to contact for further information:

> John Mudge
>
> <helpdesk@omaorg.org>

Author/Change controller:

> Open Mobile Naming Authority (OMNA)
>
> <OMA-OMNA@mail.openmobilealliance.org>

Provisional registration (standards tree only): N/A

1.  <span id="_Ref456013268" class="anchor"><span id="_Toc471907845" class="anchor"><span id="_Toc492476276" class="anchor"><span id="_Ref455994764" class="anchor"><span id="_Ref455995564" class="anchor"><span id="_Toc493059962" class="anchor"></span></span></span></span></span></span>LwM2M Schema and Object Definition File (Informative)

For supporting the LwM2M Enabler version and the Object Version in the Definition file (.xml) of a LwM2M Object, the LwM2M schema (URL: ="<http://openmobilealliance.org/tech/profiles/LWM2M.xsd>") contains 2 optional elements: LwM2MVersion and ObjectVersion (see Appendix K).

The Object definition file (.xml), which describes the resources of a particular Object may contain these two elements:

1.  the “LwM2MVersion” element indicates the minimum version of the LwM2M Enabler supporting that Object,

2.  the “ObjectVersion” element indicates the version of the Object as defined in Section 6.2 “Object Versioning” in this document.

In addition:

-   when the minimum LwM2M version supporting the Object is the Initial Version of the LwM2M Enabler (1.0), this information may be omitted.

-   when the Object version is the Initial Version of that Object (1.0), the Object Version information may be omitted.

-   when the Object definition is part of any LwM2M Enabler, the Object Version information may be omitted.

For example: an Object ID:44 in Version 2.4 for which the minimum LwM2M version supporting this Object Version is 1.1, will have an URN defined as “*urn:oma:lwm2m:oma:44:2.4”* used to name the associate Object definition (.xml) file on the OMNA portal:

*&lt;?xml version="1.0" encoding="UTF-8"?&gt;*

*&lt;LWM2M xmlns:xsi = "<http://www.w3.org/2001/XMLSchema-instance>" xsi:noNamespaceSchemaLocation="<http://openmobilealliance.org/tech/profiles/LWM2M.xsd>" &gt;*

*                &lt;Object ObjectType="MODefinition"&gt;*

*                                &lt;Name&gt;MyDevice&lt;/Name&gt;*

*                                &lt;Description1&gt;&lt; !\[CDATA\[This LWM2M Object is my device\]\]&gt;&lt;/Description1&gt;*

*                                &lt;ObjectID&gt;44&lt;/ObjectID&gt;*

*                                &lt;LWM2MVersion&gt;1.1&lt;/LWM2MVersion&gt;*

*                                &lt;ObjectVersion&gt;2.4&lt;/ObjectVersion&gt;*

*                                &lt;ObjectURN&gt;urn:oma:lwm2m:oma:44:2.4&lt;/ObjectURN&gt;*

*                                &lt;MultipleInstances&gt;Single&lt;/MultipleInstances&gt;*

*                                &lt;Mandatory&gt;Mandatory&lt;/Mandatory&gt;*

*                                &lt;Resources&gt;  *

*                                        .*

*                                       .*

*&lt;/Resources&gt;*

*&lt;/Description2&gt;*

*&lt;/Resources&gt;*

*&lt;/Object&gt;*

*&lt;/LWM2M&gt;*

1.  <span id="_Toc471907846" class="anchor"><span id="_Ref472009887" class="anchor"><span id="_Toc492476277" class="anchor"><span id="_Toc493059963" class="anchor"></span></span></span></span>LwM2M Schema

This appendix provides the content of the LightweightM2M schema.

The schema was created to support the LwM2M Editor Tool.
The following elements and attributes are used by the LwM2M Editor Tool but are not part of the LwM2M protocol:

-   Description1, it is used to insert the definition of the Object

-   Description2, it is used to insert any extra information at the end of the table that contains the Resources

-   ObjectType, used to identify if the file contains an Object and Resources or only Resources

&lt;xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"&gt;
&lt;xs:element name="LWM2M"&gt;
&lt;xs:complexType&gt;
&lt;xs:sequence&gt;
&lt;xs:element minOccurs="1" maxOccurs="unbounded" name="Object"&gt;
&lt;xs:complexType&gt;
&lt;xs:sequence&gt;
&lt;xs:element name="Name" type="xs:string" /&gt;
&lt;xs:element name="Description1" type="xs:string" /&gt;
&lt;xs:element name="ObjectID" type="xs:unsignedShort" /&gt;
&lt;xs:element name="ObjectURN" type="xs:string" /&gt;
&lt;xs:element name="LWM2MVersion" type="xs:string" minOccurs="0"/&gt;
&lt;xs:element name="ObjectVersion" type="xs:string" minOccurs="0"/&gt;
&lt;xs:element name="MultipleInstances" &gt;
&lt;xs:simpleType&gt;
&lt;xs:restriction base="xs:string"&gt;
&lt;xs:enumeration value="Multiple"/&gt;
&lt;xs:enumeration value="Single"/&gt;
&lt;/xs:restriction&gt;
&lt;/xs:simpleType&gt;
&lt;/xs:element&gt;
&lt;xs:element name="Mandatory" &gt;
&lt;xs:simpleType&gt;
&lt;xs:restriction base="xs:string"&gt;
&lt;xs:enumeration value="Mandatory"/&gt;
&lt;xs:enumeration value="Optional"/&gt;
&lt;/xs:restriction&gt;
&lt;/xs:simpleType&gt;
&lt;/xs:element&gt;
&lt;xs:element name="Resources"&gt;
&lt;xs:complexType&gt;
&lt;xs:sequence&gt;
&lt;xs:element maxOccurs="unbounded" name="Item"&gt;
&lt;xs:complexType&gt;
&lt;xs:sequence&gt;
&lt;xs:element name="Name" type="xs:string" /&gt;
&lt;xs:element name="Operations" &gt;
&lt;xs:simpleType&gt;
&lt;xs:restriction base="xs:string"&gt;
&lt;xs:enumeration value="R"/&gt;
&lt;xs:enumeration value="W"/&gt;
&lt;xs:enumeration value="RW"/&gt;
&lt;xs:enumeration value="E"/&gt;
&lt;xs:enumeration value=""/&gt;
&lt;/xs:restriction&gt;
&lt;/xs:simpleType&gt;
&lt;/xs:element&gt;
&lt;xs:element name="MultipleInstances" &gt;
&lt;xs:simpleType&gt;
&lt;xs:restriction base="xs:string"&gt;
&lt;xs:enumeration value="Multiple"/&gt;
&lt;xs:enumeration value="Single"/&gt;
&lt;/xs:restriction&gt;
&lt;/xs:simpleType&gt;
&lt;/xs:element&gt;
&lt;xs:element name="Mandatory" &gt;
&lt;xs:simpleType&gt;
&lt;xs:restriction base="xs:string"&gt;
&lt;xs:enumeration value="Mandatory"/&gt;
&lt;xs:enumeration value="Optional"/&gt;
&lt;/xs:restriction&gt;
&lt;/xs:simpleType&gt;
&lt;/xs:element&gt;
&lt;xs:element name="Type" &gt;
&lt;xs:simpleType&gt;
&lt;xs:restriction base="xs:string"&gt;
&lt;xs:enumeration value="String"/&gt;
&lt;xs:enumeration value="Integer"/&gt;
&lt;xs:enumeration value="Float"/&gt;
&lt;xs:enumeration value="Boolean"/&gt;
&lt;xs:enumeration value="Opaque"/&gt;
&lt;xs:enumeration value="Time"/&gt;
&lt;xs:enumeration value="Objlnk"/&gt;
&lt;xs:enumeration value=""/&gt;
&lt;/xs:restriction&gt;
&lt;/xs:simpleType&gt;
&lt;/xs:element&gt;
&lt;xs:element name="RangeEnumeration" type="xs:string" /&gt;
&lt;xs:element name="Units" type="xs:string" /&gt;
&lt;xs:element name="Description" type="xs:string" /&gt;
&lt;/xs:sequence&gt;
&lt;xs:attribute name="ID" type="xs:unsignedShort" use="required" /&gt;
&lt;/xs:complexType&gt;
&lt;/xs:element&gt;
&lt;/xs:sequence&gt;
&lt;/xs:complexType&gt;
&lt;/xs:element&gt;
&lt;xs:element name="Description2" type="xs:string" /&gt;
&lt;/xs:sequence&gt;
&lt;xs:attribute name="ObjectType" type="xs:string" use="required" /&gt;
&lt;/xs:complexType&gt;
&lt;/xs:element&gt;
&lt;/xs:sequence&gt;
&lt;/xs:complexType&gt;
&lt;/xs:element&gt;
&lt;/xs:schema&gt;

1.  <span id="_Toc58398639" class="anchor"><span id="_Toc199130873" class="anchor"><span id="_Toc492476278" class="anchor"><span id="_Toc493059964" class="anchor"></span></span></span></span>Example of Trigger Message from Server (Informative)

Example WAP Push over SMS containing the trigger information:

|                                           |                                          |                                |
|-------------------------------------------|------------------------------------------|--------------------------------|
| **Binary value**                          | **Meaning**                              | **Description**                |
| 06                                        | User-Data-Header (UDHL) Length = 6 bytes | WDP layer (start WDP headers). |
| 05                                        | UDH IE identifier: Port numbers          |                                |
| 04                                        | UDH port number IE length                |                                |
| 0B                                        | Destination port (high)                  | Port number 2948               |
| 84                                        | Destination port (low)                   |                                |
| C0                                        | Originating port (high)                  | Port number chosen by sender   |
| 02                                        | Originating port (low)                   | WDP layer (end WDP headers)    |
| 01                                        | Transaction ID / Push ID                 | WSP layer (start WSP headers)  |
| 06                                        | PDU type (push)                          |                                |
| 03                                        | Headerslength (content type+headers)     |                                |
| C4                                        | Content type code                        | MIME-Type                      |
| AF                                        | X-WAP-Application-ID                     |                                |
| 9A                                        | Id for urn: x-wap-application:lwm2m.dm   | WSP layer (end WSP headers)    |
| {14-bytes}                                | 112-bit clear value                      | Clear CoAP Text                |
| 44 02 b6 0b 21 61 fb 63 b1 31 01 30 01 38 | PDU length:14                            
                                            
  CoAP Version: 1                           
                                            
  Message Type: Confirmable                 
                                            
  Token length: 4                           
                                            
  Code: 0.02 POST                           
                                            
  Message ID: 34488                         
                                            
  Token length: 4                           
                                            
  Value: 0x301e65ca OPTION (0/3)            
                                            
  Option number (delta): 11(11)             
                                            
  Name: URI\_PATH                           
                                            
  Value length: 1                           
                                            
  Value: "1"                                
                                            
  OPTION (1/3)                              
                                            
  Option number (delta): 11(0)              
                                            
  Name: URI\_PATH                           
                                            
  Value length: 1                           
                                            
  Value: "0"                                
                                            
  OPTION (2/3)                              
                                            
  Option number (delta): 11(0)              
                                            
  Name: URI\_PATH                           
                                            
  Value length: 1                           
                                            
  Value: "8"                                
                                            
  No payload.                               |

[1] The mapping to CoAP Methods of the LwM2M Client Registration Interface operations specified in this section, is detailed in chapter 8 of the present document (Transport Layer Binding and Encodings).

[2] The mapping to CoAP Methods of the LwM2M Client Registration Interface operations specified in this section, is detailed in chapter 8 of the present document (Transport Layer Binding and Encodings).

[3] The mapping to CoAP Methods of the LwM2M Information Reporting Interface operations specified in this section, is detailed in chapter 8 of the present document (Transport Layer Binding and Encodings).
