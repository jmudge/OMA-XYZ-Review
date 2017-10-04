|                                                                          |     |
|--------------------------------------------------------------------------|-----|
| <img src="images/media/image1.jpeg" alt="oma" width="192" height="60" /> |     |
| Enabler Test Specification for Lightweight M2M                           |
| Draft Version 1.0.1 – 30 Aug 2017                                        |
| **Open Mobile Alliance**                                                 |
| OMA-ETS-LightweightM2M-V1\_0\_1-20170830-D                               |
|                                                                          |     |

Use of this document is subject to all of the terms and conditions of the Use Agreement located at <http://www.openmobilealliance.org/UseAgreement.html>.

Unless this document is clearly designated as an approved specification, this document is a work in process, is not an approved Open Mobile Alliance™ specification, and is subject to revision or removal without notice.

You may use this document or any part of the document for internal or educational purposes only, provided you do not modify, edit or take out of context the information in this document in any manner. Information contained in this document may be used, at your sole risk, for any purposes. You may not use this document in any other manner without the prior written permission of the Open Mobile Alliance. The Open Mobile Alliance authorizes you to copy this document, provided that you retain all copyright and other proprietary notices contained in the original materials on any copies of the materials and that you comply strictly with these terms. This copyright permission does not constitute an endorsement of the products or services. The Open Mobile Alliance assumes no responsibility for errors or omissions in this document.

Each Open Mobile Alliance member has agreed to use reasonable endeavors to inform the Open Mobile Alliance in a timely manner of Essential IPR as it becomes aware that the Essential IPR is related to the prepared or published specification. However, the members do not have an obligation to conduct IPR searches. The declared Essential IPR is publicly available to members and non-members of the Open Mobile Alliance and may be found on the “OMA IPR Declarations” list at <http://www.openmobilealliance.org/ipr.html>. The Open Mobile Alliance has not conducted an independent IPR review of this document and the information contained herein, and makes no representations or warranties regarding third party IPR, including without limitation patents, copyrights or trade secret rights. This document may contain inventions for which you must obtain licenses from third parties before making, using or selling the inventions. Defined terms above are set forth in the schedule to the Open Mobile Alliance Application Form.

NO REPRESENTATIONS OR WARRANTIES (WHETHER EXPRESS OR IMPLIED) ARE MADE BY THE OPEN MOBILE ALLIANCE OR ANY OPEN MOBILE ALLIANCE MEMBER OR ITS AFFILIATES REGARDING ANY OF THE IPR’S REPRESENTED ON THE “OMA IPR DECLARATIONS” LIST, INCLUDING, BUT NOT LIMITED TO THE ACCURACY, COMPLETENESS, VALIDITY OR RELEVANCE OF THE INFORMATION OR WHETHER OR NOT SUCH RIGHTS ARE ESSENTIAL OR NON-ESSENTIAL.

THE OPEN MOBILE ALLIANCE IS NOT LIABLE FOR AND HEREBY DISCLAIMS ANY DIRECT, INDIRECT, PUNITIVE, SPECIAL, INCIDENTAL, CONSEQUENTIAL, OR EXEMPLARY DAMAGES ARISING OUT OF OR IN CONNECTION WITH THE USE OF DOCUMENTS AND THE INFORMATION CONTAINED IN THE DOCUMENTS.

© 2017 Open Mobile Alliance All Rights Reserved.
Used with the permission of the Open Mobile Alliance under the terms set forth above.

Contents

1. Scope 6

2. References 7

2.1 Normative References 7

2.2 Informative References 7

3. Terminology and Conventions 8

3.1 Conventions 8

3.2 Definitions 8

3.3 Abbreviations 8

4. Introduction 9

5. LightweightM2M Conformance Test Cases 10

6. LightweightM2M Interoperability Test Cases 11

6.1 LwM2M Core Specification Test cases \[0-999\] 11

6.1.1 Bootstrap Interface: \[0-99\] 11

6.1.1.1 LightweightM2M-1.0-int-0 – Client Initiated Bootstrap 11

6.1.2 Registration Interface \[100-199\] 12

6.1.2.1 LightweightM2M-1.0-int-101 – Initial Registration 12

6.1.2.2 LightweightM2M-1.0-int-102 – Registration Update 13

6.1.2.3 LightweightM2M-1.0-int-103 – Deregistration 15

6.1.2.4 LightweightM2M-1.0-int-104 – Registration Update Trigger 15

6.1.3 Device management & Service Enablement Interface \[200-299\] 17

6.1.3.1 LightweightM2M-1.0-int-201 – Querying basic information in Plain Text format 17

6.1.3.2 LightweightM2M-1.0-int-202 – Querying basic information in Opaque format 18

6.1.3.3 LightweightM2M-1.0-int-203 – Querying basic information in TLV format 19

6.1.3.4 LightweightM2M-1.0-int-204 – Querying basic information in JSON format 20

6.1.3.5 LightweightM2M-1.0-int-205 – Setting basic information in Plain Text format 21

6.1.3.6 LightweightM2M-1.0-int-210 – Setting basic information in Opaque format 22

6.1.3.7 LightweightM2M-1.0-int-215 – Setting basic information in TLV format 22

6.1.3.8 LightweightM2M-1.0-int-220 – Setting basic information in JSON format 23

6.1.3.9 LightweightM2M-1.0-int-241 – Executable Resource: Rebooting the device 24

6.1.3.10 LightweightM2M-1.0-int-260 – Discover Command 24

6.1.3.11 LightweightM2M-1.0-int-270 – Create Object Instance 25

6.1.3.12 LightweightM2M-1.0-int-271 – Create Multiple Resource Instance 25

6.1.3.13 LightweightM2M-1.0-int-290 – Delete Object Instance 25

6.1.4 Information Reporting Interface \[300-399\] 26

6.1.4.1 LightweightM2M-1.0-int-301 – Observation and Notification of parameter values 26

6.1.4.2 LightweightM2M-1.0-int-302 – Cancel Observations using Reset Operation 28

6.1.4.3 LightweightM2M-1.0-int-303 – Cancel observations using Observe with Cancel parameter 29

6.1.5 Security \[400-499\] 31

6.1.5.1 LightweightM2M-1.0-int-401 – UDP Channel Security – Pre-shared Key Mode 31

6.1.6 Core Specific Objects Test cases \[500-999\] 32

6.1.6.1 Security Object (ID 0) \[500-549\] 32

6.1.6.2 Server Object (ID 1) \[550-599\] 32

6.1.6.2.1 LightweightM2M-1.0-int-551 – Access Check to the Resources 33

6.1.6.2.2 LightweightM2M-1.0-int-555 – Check of the Disable (De-Registration) capability 34

6.1.6.2.3 LightweightM2M-1.0-int-556 – Check of the Update Registration capability 35

6.1.6.2.4 LightweightM2M-1.0-int-560 – Delayed Report Notification 35

6.1.6.2.5 LightweightM2M-1.0-int-565 – Create Object Instance 35

6.1.6.2.6 LightweightM2M-1.0-int-566 – Delete Object Instance 35

6.1.6.3 Access Control Object (ID 2) \[600-649\] 35

6.1.6.4 LwM2M Device Object (ID 3) \[650-699\] 35

6.1.6.4.1 LightweightM2M-1.0-int-651 – Check Access to the Resources 36

6.1.6.4.2 LightweightM2M-1.0-int-652 – Querying the firmware version from the client 38

6.1.6.4.3 LightweightM2M-1.0-int-655 – Check of the “Reboot” capability 38

6.1.6.4.4 LightweightM2M-1.0-int-656 – Check of the “Factory Reset” capability 39

6.1.6.4.5 LightweightM2M-1.0-int-657 – Check of the “Error Code” functionality 39

6.1.6.4.6 LightweightM2M-1.0-int-660 – Basic Observation and notification of Device Object Resources 39

6.1.6.4.7 LightweightM2M-1.0-int-661 – Extended Observation and notification of Device Object Resources 40

6.1.6.4.8 LightweightM2M-1.0-int-670 – Create Multiple Resource Instances 40

6.1.6.4.9 LightweightM2M-1.0-int-680 – Create Object Instance 40

6.1.6.4.10 LightweightM2M-1.0-int-685 – Delete Object Instance 40

6.1.6.5 LwM2M Connectivity Monitoring (ID:4) \[700-749\] 41

6.1.6.5.1 LightweightM2M-1.0-int-701 – Querying the readable resources of object 41

6.1.6.5.2 LightweightM2M-1.0-int-705 – Setting the writable resources 42

6.1.6.5.3 LightweightM2M-1.0-int-710 – Basic Observation and notification on Connectivity Monitoring Object Resources 43

6.1.6.5.4 LightweightM2M-1.0-int-711 – Extended Observation and notification of Connectivity Monitoring Object Resources 43

6.1.6.5.5 LightweightM2M-1.0-int-720 – Create Multiple Resource Instances 43

6.1.6.5.6 LightweightM2M-1.0-int-730 – Create Object Instance 43

6.1.6.5.7 LightweightM2M-1.0-int-735 – Delete Object Instance 43

6.1.6.6 Firmware Update Object (ID 5) \[750-799\] 45

6.1.6.6.1 LightweightM2M-1.0-int-751 – Querying the readable resources 45

6.1.6.6.2 LightweightM2M-1.0-int-755 – Setting the writable Resource Package 46

6.1.6.6.3 LightweightM2M-1.0-int-756 – Setting the writable Resource Package URI 47

6.1.6.6.4 LightweightM2M-1.0-int-760 –Basic Observation and notification on Firmware Update Object Resources 47

6.1.6.6.5 LightweightM2M-1.0-int-770 – Successful Firmware update (via COAP) 49

6.1.6.6.6 LightweightM2M-1.0-int-771 – Successful Firmware update (via alternative mechanism) 52

6.1.6.6.7 LightweightM2M-1.0-int-772 – Error Case 1: firmware installation without downloaded package 54

6.1.6.6.8 LightweightM2M-1.0-int-773 – Error Case 2: shortage of storage memory 56

6.1.6.6.9 LightweightM2M-1.0-int-774 – Error Case 3: out of memory 58

6.1.6.6.10 LightweightM2M-1.0-int-775 – Error Case 4: Connection lost during download (package URI) 60

6.1.6.6.11 LightweightM2M-1.0-int-776 – Error Case 5: Package Integrity check failure 62

6.1.6.6.12 LightweightM2M-1.0-int-777 – Error Case 6: unsupported package type 64

6.1.6.6.13 LightweightM2M-1.0-int-778 – Error Case 7: invalid URI (package URI) 66

6.1.6.6.14 LightweightM2M-1.0-int-779 – Error Case 8: Unsuccessful Firmware Update 68

6.1.6.6.15 LightweightM2M-1.0-int-780 – Error Case 9: Unsupported protocol 69

6.1.6.7 LwM2M Location Object (ID:6) \[800-849\] 71

6.1.6.7.1 LightweightM2M-1.0-int-801 – Querying the readable resources of object 71

6.1.6.7.2 LightweightM2M-1.0-int-805 – Setting the writable resources 71

6.1.6.7.3 LightweightM2M-1.0-int-810 – Basic Observation and notification on Location Object Instance 71

6.1.6.7.4 LightweightM2M-1.0-int-811 – Extended Observation and notification of Location Object Instance 72

6.1.6.7.5 LightweightM2M-1.0-int-820 – Create Multiple Resource Instances 72

6.1.6.7.6 LightweightM2M-1.0-int-830 – Create Object Instance 72

6.1.6.7.7 LightweightM2M-1.0-int-835 – Delete Object Instance 72

6.1.6.8 Connectivity Statistics (ID 7) \[900-949\] 73

6.1.6.8.1 LightweightM2M-1.0-int-901 – Querying a Data Collection from Connectivity Object Instance 73

6.1.6.8.2 LightweightM2M-1.0-int-905 – Setting the writable resources 73

6.1.6.8.3 LightweightM2M-1.0-int-910 – Basic Observation and notification on Connectivity Monitoring Object Instance 75

6.1.6.8.4 LightweightM2M-1.0-int-911 – Extended Observation and notification of Connectivity Statistics Object Instance 76

6.1.6.8.5 LightweightM2M-1.0-int-920 – Create Multiple Resource Instances 76

6.1.6.8.6 LightweightM2M-1.0-int-930 – Create Object Instance 76

6.1.6.8.7 LightweightM2M-1.0-int-935 – Delete Object Instance 76

6.2 Multi-Servers Context \[950-999\] 76

6.2.1 LightweightM2M-1.0-int-950 – Multi-Servers Registration 76

6.2.2 LightweightM2M-1.0-int-951 – Multi-Servers & Attributes 76

6.3 LwM2M Additional Objects Test cases \[1000-1999\] 77

6.3.1 Lock and Wipe Object (ID 8) \[1000-1099\] 77

6.3.2 Software Management Object (ID 9) \[1100-1199\] 77

6.3.3 Connectivity Management Objects (ID 10, 11, 12, 13) \[1200-1499\] 78

6.3.3.1 Cellular Network Connectivity ID:10 \[1200-1249\] 78

6.3.3.1.1 LightweightM2M-1.0-int-1200 – Querying the readable resources of Object ID:10 78

6.3.3.1.2 LightweightM2M-1.0-int-1201 – Querying the readable resources of Object ID:10 in version 1.1 78

6.3.3.1.3 LightweightM2M-1.0-int-1210 – Setting the Power Saving Mode Resources of Object ID:10 (version 1.1 only) 79

6.3.3.1.4 LightweightM2M-1.0-int-1230 – Observation and notification on Object ID:0 related to Power Saving Mode Resources (version 1.1 only) 80

6.3.3.2 APN connection profile ID:11 \[1250-1299\] 81

6.3.3.2.1 LightweightM2M-CONMGMT-1.0-int-1250 – APN configuration 81

6.3.3.2.2 WLAN Connectivity ID:12 \[1300-1349\] 82

6.3.3.2.3 Bearer Selection ID:13 \[1350-1399\] 82

6.3.4 Device Capability Management Object (ID 15) \[1500-1599\] 83

6.3.5 Portfolio Object (ID 16) \[1600-1699\] 83

6.3.5.1 LightweightM2M-1.0-int-1600 – Querying the readable resources of object 83

6.3.5.2 LightweightM2M-1.0-int-1605 – Setting the writable resources 83

6.3.5.3 LightweightM2M-1.0-int-1610 – Basic Observation and notification of a Portfolio Object Instance 83

6.3.5.4 LightweightM2M-1.0-int-1611 – Extended Observation and notification of a Portfolio Object Instance 83

6.3.5.5 LightweightM2M-1.0-int-1620 – Create Multiple Resource Instances 83

6.3.5.6 LightweightM2M-1.0-int-1630 – Create Portfolio Object Instance 83

6.3.5.7 LightweightM2M-1.0-int-1635 – Delete Portfolio Object Instance 85

Appendix A. Change History (Informative) 86

A.1 Approved Version History 86

A.2 Draft/Candidate Version 1.0/1.0.1 History 86

Appendix B. Additional Information 89

B.1 Example of Test Configuration and Setup 89

Appendix C. LwM2M Configurations 90

C.1 Basic Configuration 1 90

C.2 Basic Configuration 2 91

C.3 Configuration 3 92

C.4 Configuration 4 93

C.5 Configuration 5 94

C.6 Configuration 6 95

C.7 Configuration 7 96

C.8 Configuration 8 97

C.9 Configuration 9 98

C.10 Basic Connectivity Management Configuration 10 99

C.11 Basic Connectivity Management Configuration 11 supporting Object ID:10 version 1.1 100

C.12 Configuration 12 101

C.13 Bootstrap Server Contact Configuration 102

C.14 Multi-Servers Context Initial Configuration 103

Appendix D. Core Test Coverage 105

Appendix E. Enabler Validation Plan 110

E.1 Entry Criteria for TestFest 110

E.2 Enabler Validation Test Cases 110

Scope
=====

<span id="_Toc51149232" class="anchor"></span>This document describes in detail available test cases for LightweightM2M as specified in OMA-TS-LightweightM2M-V1\_0.

The test cases are split in two categories, conformance and interoperability test cases.

The conformance test cases are aimed to verify the adherence to normative requirements described in the technical specifications.

The interoperability test cases are aimed to verify that implementations of the specifications work satisfactory.

If either conformance or interoperability tests do not exists at the creation of the test specification this part should be marked not available.

References
==========

Normative References
--------------------

|                                                                              |                                                                                                                                                                                            |
|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \[3GPP-TS\_23.003\]                                                          | 3GPP TS 23.003 “Numbering, addressing and identification”                                                                                                                                  |
| \[CoAP\]                                                                     | Shelby, Z., Hartke, K., Bormann, C., and B. Frank, "Constrained Application Protocol (CoAP)", draft-ietf-core-coap-18, Jun 2013.                                                           |
| <span id="reference_TS102_221" class="anchor"></span>**\[ETSI TS 102.221\]** | “Smart Cards; UICC-Terminal interface; Physical and logical characteristics”, (ETSI TS 102 221 release 11), [URL:http://www.etsi.org/](http://www.etsi.org/)                               |
| **\[GlobalPlatform SCP 02\]**                                                | GlobalPlatform  v2.2.1 - January 2011 - Appendix E: Secure Channel Protocol 02 (SCP 02)                                                                                                    |
| \[IOPPROC\]                                                                  | “OMA Interoperability Policy and Process”, Version 1.13, Open Mobile Alliance™, OMA-IOP-Process-V1\_13, <URL:http://www.openmobilealliance.org/>                                           |
| \[LwM2M-AD\]                                                                 | “Lightweight Machine to Machine Architecture”, Open Mobile Alliance™, OMA-AD-LightweightM2M-V1\_0, [URL:http://www.openmobilealliance.org/](http://www.openmobilealliance.org/)            |
| \[LwM2M-TS\]                                                                 | “Lightweight Machine to Machine Technical Specification”, Open Mobile Alliance™, OMA-TS-LightweightM2M-V1\_0, [URL:http://www.openmobilealliance.org/](http://www.openmobilealliance.org/) |
| \[OBSERVE\]                                                                  | <span id="_Toc342064474" class="anchor"></span>Hartke, K. “Observing Resources in CoAP”, draft-ietf-core-observe-11 (work in progress), Oct 2013.                                          |
| <span id="reference_PKCS_15" class="anchor"></span>**\[PKCS\#15\]**          | PKCS \#15 v1.1: Cryptographic Token Information Syntax Standard”, RSA Laboratories, June 6, 2000. <URL:ftp://ftp.rsasecurity.com/pub/pkcs/pkcs-15/pkcs-15v1_1.pdf>                         |
| \[RFC2119\]                                                                  | “Key words for use in RFCs to Indicate Requirement Levels”, S. Bradner, March 1997, <URL:http://www.ietf.org/rfc/rfc2119.txt>                                                              |
| \[RFC2234\]                                                                  | “Augmented BNF for Syntax Specifications: ABNF”. D. Crocker, Ed., P. Overell. November 1997, <URL:http://www.ietf.org/rfc/rfc2234.txt>                                                     |
| <span id="RFC4122" class="anchor"></span>\[RFC4122\]                         | “A Universally Unique Identifier (UUID) URN Namespace”, P. Leach, et al. July 2005, <URL:http://www.ietf.org/rfc/rfc4122.txt>                                                              |
| **\[RFC5246\]**                                                              | The Transport Layer Security (TLS) Protocol Version 1.2                                                                                                                                    |
| **\[RFC5289\]**                                                              | TLS Elliptic Curve Cipher Suites with SHA-256/384 and AES Galois Counter Mode (GCM)                                                                                                        |
| **\[RFC5487\]**                                                              | Pre-Shared Key Cipher Suites for TLS with SHA-256/384 and AES Galois Counter Mode                                                                                                          |
| \[RFC6347\]                                                                  | Rescorla, E. and N. Modadugu, "Datagram Transport Layer Security Version 1.2", [RFC6347](http://tools.ietf.org/html/rfc6347), January 2012.                                                |
| \[RFC6655\]                                                                  | McGrew, D. and D. Bailey, "AES-CCM Cipher Suites for TLS", RFC6655, July 2012.                                                                                                             |
| \[RFC6690\]                                                                  | Shelby, Z. “Constrained RESTful Environments (CoRE) Link Format”, RFC6690, Aug 2012.                                                                                                       |

Informative References
----------------------

<table>
<tbody>
<tr class="odd">
<td><span id="DMREPPRO" class="anchor"></span>[DMREPPRO]</td>
<td>“OMA Device Management Representation Protocol, Version 1.3”.<br />
Open Mobile Alliance. OMA-TS-DM_RepPro-V1_3. <a href="URL:http://www.openmobilealliance.org" class="uri">URL:http://www.openmobilealliance.org</a></td>
</tr>
<tr class="even">
<td>[OMADICT]</td>
<td>“Dictionary for OMA Specifications”, Version 2.9, Open Mobile Alliance™,<br />
OMA-ORG-Dictionary-V2_9, <a href="URL:http://www.openmobilealliance.org/" class="uri">URL:http://www.openmobilealliance.org/</a></td>
</tr>
</tbody>
</table>

Terminology and Conventions
===========================

Conventions
-----------

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in \[RFC2119\].

All sections and appendixes, except “Scope”, are normative, unless they are explicitly indicated to be informative.

The following numbering scheme is used:

> **xxx-y.z-con-number** where:
> xxx Name of enabler, e.g. MMS or Browsing
> y.z Version of enabler release, e.g. 1.2 or 1.2.1
> ’con’ Indicating this test is a conformance test case
> number Leap number for the test case

Or

> **xxx-y.z-int-number** where:
> xxx Name of enabler, e.g. MMS or Browsing
> y.z Version of enabler release, e.g. 1.2 or 1.2.1
> ’int’ Indicating this test is a interoperability test case
> number Leap number for the test case

Definitions
-----------

|             |                                                                                                      |
|-------------|------------------------------------------------------------------------------------------------------|
| Application 
              
 Device       
              
 Module       | 1) The customer's realisation of a service through M2M - e.g. satnav, smart metering                 
                                                                                                        
  2) Individual software components that run on top of the device's operating system.Access Point Name  
                                                                                                        
  The hardware that is realising a function for the customer e.g. a smart meter.                        
                                                                                                        
  A modular component of a device e.g. the radio module housing the SIM                                 |

Abbreviations
-------------

|        |                                                             |
|--------|-------------------------------------------------------------|
| API    
         
 APN     
         
 CoAP    
         
 CON     
         
 DM      
         
 GDSP    
         
 GUI     
         
 IMEI    
         
 IMSI    
         
 IOP     
         
 LwM2M   
         
 M2M     
         
 MSISDN  
         
 OMA     
         
 OpCo    
         
 OS      
         
 SIM     
         
 UI      | Application Programming Interface                           
                                                               
  Access Point Name                                            
                                                               
  Constrained Application Protocol                             
                                                               
  Conformance                                                  
                                                               
  Device Management                                            
                                                               
  Global Data Service Platform                                 
                                                               
  Graphical User Interface                                     
                                                               
  International Mobile Equipment Identity                      
                                                               
  International Mobile Subscriber Identity                     
                                                               
  Interoperability                                             
                                                               
  Lightweight Machine to Machine (refers to this OMA enabler)  
                                                               
  Machine to Machine                                           
                                                               
  Mobile Station International Subscriber Directory Number     
                                                               
  Open Mobile Alliance                                         
                                                               
  Operating Company                                            
                                                               
  Operating System                                             
                                                               
  Subscriber Interface Module                                  
                                                               
  User Interface                                               |

Introduction
============

<span id="_Toc51149240" class="anchor"></span>The purpose of this document is to provide test cases for LightweightM2M Enabler Release V1.0.

The implementation of some features is optional for the Clients and/or the Servers in the LightweightM2M Enabler. The tests associated with these optional features are marked as "(Includes Optional Features)" in the test specification.

The following items on an overall level are needed to adequately test the LwM2M enabler:

-   A LwM2M Server

-   A LwM2M client e.g. embedded in a M2M device or module connected via UDP and SMS with the LwM2M Server

The LwM2M enabler tests are carried out using the LwM2M protocol and objects, and using the underlying protocols such as \[CoAP\].

The four data formats used in that document, namely Plain Text, Opaque, TLV and JSON data formats are respectively associated to the text/plain, application/octet-stream, application/vnd.oma.lwm2m+tlv, application/vnd.oma.lwm2m+json Media Types referred by LwM2M TS 1.0 and registered in IANA.

LightweightM2M Conformance Test Cases
=====================================

None.

LightweightM2M Interoperability Test Cases
==========================================

LwM2M Core Specification Test cases \[0-999\]
---------------------------------------------

### Bootstrap Interface: \[0-99\]

#### LightweightM2M-1.0-int-0 – Client Initiated Bootstrap 

|                           |                                                                                                                                                                                                                                                                                       |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int- 0                                                                                                                                                                                                                                                             |
| **Test Object**           | Client and Server                                                                                                                                                                                                                                                                     |
| **Test Case Description** | Test the Client capability to connect the Bootstrap Server according to the Client Initiated Bootstrap Mode                                                                                                                                                                           |
| **Tool**                  | n/a                                                                                                                                                                                                                                                                                   |
| **Test code**             | n/a                                                                                                                                                                                                                                                                                   |
| **Preconditions**         | -   The Client supports the minimum Configuration C.14 as defined in Annex C                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                                         
  -   The Client is supporting the Client Initiated Bootstrap Mode                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                         
  -   The Client doesn’t contain any Instance of LwM2M Server Object ID:1 (minimum condition to trigger a Bootstrap request message when the device is on)                                                                                                                               |
| **Test Procedure**        | The Client requests the Bootstrap Server to setup a configuration enabling the Client to contact a LwM2M Server.                                                                                                                                                                      
                                                                                                                                                                                                                                                                                         
  Normal flow:                                                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                                         
  1.  Without Instance of Server Object, the Client performs a BOOTSTRAP-REQUEST (CoAP POST /bs?ep{Endpoint Client Name}) in using the Resource values of the Instance 1 of Security Object ID:0 to contact the Bootstrap Server                                                         
                                                                                                                                                                                                                                                                                         
  2.  The Bootstrap Server uploads the Configuration C.1 in the Client in performing two BOOTSTRAP-WRITE (CoAP PUT /0, CoAP PUT /1) in using the set of values defined in 0-SetOfValue\_1 and 0-SetOfValue\_2 (Object Device ID:3,is automatically created and filled-up by the Client)  
                                                                                                                                                                                                                                                                                         
  3.  The Bootstrap Server performs a BOOTSTRAP-DISCOVER operation (CoAP GET Accept:40 / ) to verify the Client setup                                                                                                                                                                    
                                                                                                                                                                                                                                                                                         
  4.  The Bootstrap Server performs a BOOTSTRAP-FINISH operation (CoAP POST /bs) to end-up that BS phase                                                                                                                                                                                 |
| **Pass-Criteria**         | 1.  In test step 1., the Bootstrap Server received a Success Message (“2.04” Changed) related to the BOOTSTRAP-REQUEST of the Client                                                                                                                                                  
                                                                                                                                                                                                                                                                                         
  2.  In test step 2., Client received WRITE operation(s) to setup the C.1 configuration (0-SetOfValue)                                                                                                                                                                                  
                                                                                                                                                                                                                                                                                         
  3.  In test step 2., Server received Success (“2.04” Changed) message(s) from Server related to WRITE operation(s)                                                                                                                                                                     
                                                                                                                                                                                                                                                                                         
  4.  In test step 3., the Bootstrap Server received the Success message (“2.05” Content) along with the payload related to the BOOTSTRAP-DISCOVER request and containing :                                                                                                              
                                                                                                                                                                                                                                                                                         
  > lwm2m="1.0",&lt;/0/0&gt;;ssid=1,&lt;/0/1&gt;, &lt;/1/0&gt;;ssid=1,&lt;/3/0&gt;                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                         
  1.  In test step 4., the Bootstrap Server received the Success message (“2.04” Changed) : no inconsistency detected                                                                                                                                                                    |

### Registration Interface \[100-199\]

#### LightweightM2M-1.0-int-101 – Initial Registration

|                           |                                                                                                                         |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-101                                                                                              |
| **Test Object**           | Client and Server                                                                                                       |
| **Test Case Description** | Test that the Client registers with the Server.                                                                         |
| **Tool**                  | n/a                                                                                                                     |
| **Test code**             | n/a                                                                                                                     |
| **Preconditions**         | -   The Client supports the minimum Configuration C.1 as defined in Annex C.                                            
                                                                                                                           
  -   Device is turned on.                                                                                                 
                                                                                                                           
  -   The bootstrap procedure has been completed or the required bootstrap information is available to the Client.         |
| **Test Procedure**        | The Client automatically registers at the Server, once this information is available.                                   
                                                                                                                           
  Normal flow:                                                                                                             
                                                                                                                           
  1.  Registration message (CoAP POST) is sent from Client to Server.                                                      |
| **Pass-Criteria**         | 1.  In test step 1. , the Server receives the REGISTER command along with the following information:                    
                                                                                                                           
  -   Endpoint Client Name                                                                                                 
                                                                                                                           
  -   registration lifetime                                                                                                
                                                                                                                           
  -   LwM2M version                                                                                                        
                                                                                                                           
  -   binding mode (optional)                                                                                              
                                                                                                                           
  -   SMS number (optional)                                                                                                
                                                                                                                           
  -   Objects and Object Instances (mandatory and optional objects / object instances) ; possibly with Version of Objects  
                                                                                                                           
  1.  In test step 1. , Client received “Success” message from Server (2.01 Created) related to the REGISTER command.      |

#### LightweightM2M-1.0-int-102 – Registration Update

|                           |                                                                                                                                                               |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-102                                                                                                                                    |
| **Test Object**           | Client and Server                                                                                                                                             |
| **Test Case Description** | Test that the client updates the registration information on the Server.                                                                                      |
| **Tool**                  | n/a                                                                                                                                                           |
| **Test code**             | n/a                                                                                                                                                           |
| **Preconditions**         | -   The Client supports the minimum Configuration C.1 as defined in Annex C                                                                                   
                                                                                                                                                                 
  -   Client is registered with the Server                                                                                                                       
                                                                                                                                                                 
  -   The Server will be prepared to change the Client lifetime registration to 20 sec to set the conditions for a Client UPDATE operation.                      
                                                                                                                                                                 
  -   On option, the Client will be prepared to update its registration before the registration time expires.                                                    |
| **Test Procedure**        | The Client is registered with the Server and updates its registration according to the change of its registration information (Lifetime) (UPDATE Operation)   
                                                                                                                                                                 
  Normal flow:                                                                                                                                                   
                                                                                                                                                                 
  1.  The Server set the lifetime resource of the Server Object Instance to 20 sec (CoAP PUT /1/0/1)                                                             
                                                                                                                                                                 
  2.  UPDATE (Registration) message (CoAP POST) is sent from Client to Server with Lifetime parameter set to 20 sec                                              
                                                                                                                                                                 
  3.  On option, before the registration expires (20 sec) the Client send a new UPDATE message without parameter to the Server                                   |
| **Pass-Criteria**         | 1.  In test step 1., the Server received a Success Message (2.04 Changed) related to its setting request                                                      
                                                                                                                                                                 
  2.  In test step 2., Server has received UPDATE operation with lifetime parameter = 20 sec                                                                     
                                                                                                                                                                 
  3.  In test step 2., Client has received “Success” (2.04) message from Server related to the UPDATE command                                                    
                                                                                                                                                                 
  4.  In test step 3., either the Server received an UPDATE operation with no parameter or a de\_registratoin occurs in the Server after the 20s                 |

#### LightweightM2M-1.0-int-103 – Deregistration

|                           |                                                                                                    |
|---------------------------|----------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-103                                                                         |
| **Test Object**           | Client and Server                                                                                  |
| **Test Case Description** | Test that the client is able to deregister at the Server.                                          |
| **Tool**                  | n/a                                                                                                |
| **Test code**             | n/a                                                                                                |
| **Preconditions**         | -   The Client supports the minimum Configuration C.3 as defined in Annex C                        
                                                                                                      
  -   Client is registered with the Server                                                            |
| **Test Procedure**        | Client will no longer be available, thus, it should de-register                                    
                                                                                                      
  Normal flow:                                                                                        
                                                                                                      
  1.  The Server sends EXECUTE command on the Disable Resource of the Server Object (ID:1) Instance.  
                                                                                                      
  2.  Deregistration message (CoAP DELETE) is sent from Client to Server.                             |
| **Pass-Criteria**         | 1.  In test step 1., the Server receives the “Success” message (2.04 Changed) from the Client      
                                                                                                      
  2.  In test step 2., the Client receives “Success” message (2.02 Deleted) from the Server           
                                                                                                      
  3.  Client is removed from the servers registration database                                        |

#### LightweightM2M-1.0-int-104 – Registration Update Trigger

|                           |                                                                                                                                                                                                              |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-104                                                                                                                                                                                   |
| **Test Object**           | Client and Server                                                                                                                                                                                            |
| **Test Case Description** | Test that the Client updates its registration with the Server when triggered with the Registration Update Trigger (see LwM2M Server object)                                                                  |
| **Tool**                  | n/a                                                                                                                                                                                                          |
| **Test code**             | n/a                                                                                                                                                                                                          |
| **Preconditions**         | -   The Client supports the minimum Configuration C.1 as defined in Annex C                                                                                                                                  
                                                                                                                                                                                                                
  -   Device is turned on                                                                                                                                                                                       
                                                                                                                                                                                                                
  -   The bootstrap procedure has been completed or the required bootstrap information is available to the client                                                                                               
                                                                                                                                                                                                                
  -   The Client is registered with the Server with a Lifetime of 20 sec (LightweightM2M-1.0-int-102)                                                                                                           |
| **Test Procedure**        | Before Client Registration lifetime expired (lifetime is 20 sec) the Server sends Registration Update Trigger and the Client updates its registration via the UPDATE Operation                               
                                                                                                                                                                                                                
  Normal flow:                                                                                                                                                                                                  
                                                                                                                                                                                                                
  1.  Before Client registration expires on the Server (for test purposes a short registration lifetime is chosen 20 sec) a Registration Update Trigger message CoAP POST /1/0/8 is sent from Server to Client  
                                                                                                                                                                                                                
  2.  UPDATE (Registration) message (CoAP POST) is sent from Client to Server                                                                                                                                   |
| **Pass-Criteria**         | 1.  In test step 1., Client received a Registration Update Trigger                                                                                                                                           
                                                                                                                                                                                                                
  2.  In test step 1., Server received a “Success” message (2.04 Changed) related to the EXECUTE command (Registration Update Trigger).                                                                         
                                                                                                                                                                                                                
  3.  In test step 2., Server received UPDATE operation without parameter                                                                                                                                       
                                                                                                                                                                                                                
  4.  In test step 2., Client has received “Success” message (2.04 Changed) from Server related to its UPDATE message                                                                                           
                                                                                                                                                                                                                
  5.  After test step 2., the Client is still registered in the Server while the initial Registration lifetime expired                                                                                          |

### Device management & Service Enablement Interface \[200-299\]

#### LightweightM2M-1.0-int-201 – Querying basic information in Plain Text format

|                           |                                                                                                                                                                                                       |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-201                                                                                                                                                                            |
| **Test Object**           | Client and Server                                                                                                                                                                                     |
| **Test Case Description** | Querying the following data on the client (Device Object: ID 3) using Plain Text data format                                                                                                          
                                                                                                                                                                                                         
  -   Manufacturer Name                                                                                                                                                                                  
                                                                                                                                                                                                         
  -   Model number                                                                                                                                                                                       
                                                                                                                                                                                                         
  -   Serial number                                                                                                                                                                                      |
| **Tool**                  | n/a                                                                                                                                                                                                   |
| **Test code**             | n/a                                                                                                                                                                                                   |
| **Preconditions**         | -   The Client supports the Configuration C.1 as defined in Annex C                                                                                                                                   
                                                                                                                                                                                                         
  -   Client is registered with the LwM2M Server                                                                                                                                                         
                                                                                                                                                                                                         
  -   Client is supporting Plain Text data format (0)                                                                                                                                                    |
| **Test Procedure**        | READ operations from Server on the targeted Resources have been received by the client.                                                                                                               
                                                                                                                                                                                                         
  Normal flow:                                                                                                                                                                                           
                                                                                                                                                                                                         
  1.  Successive READ (CoAP GET) operations are performed on the targeted Resources of the Device Object (ID:3) Instance, with the CoAP Accept option set to Plain Text data format (0)                  |
| **Pass-Criteria**         | 1.  In test step 1, Server has received all the expected “Success” messages (2.05 Content) along with the requested information with the expected values and according to the Plain Text data format: 
                                                                                                                                                                                                         
  -   Manufacturer Name (ID:0)                                                                                                                                                                           
                                                                                                                                                                                                         
  -   Model number (ID:1)                                                                                                                                                                                
                                                                                                                                                                                                         
  -   Serial number (ID:2)                                                                                                                                                                               |

#### LightweightM2M-1.0-int-202 – Querying basic information in Opaque format

*&lt;Test Cases to fill-up&gt;*

#### LightweightM2M-1.0-int-203 – Querying basic information in TLV format

|                           |                                                                                                                                                                                                  |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-203                                                                                                                                                                       |
| **Test Object**           | Client and Server                                                                                                                                                                                |
| **Test Case Description** | Querying the Resources Values of Device Object ID:3 on the Client Resources Values of Device Object ID:3                                                                                         |
| **Tool**                  | n/a                                                                                                                                                                                              |
| **Test code**             | n/a                                                                                                                                                                                              |
| **Preconditions**         | -   The client supports the Configuration C.1 as defined in Annex C                                                                                                                              
                                                                                                                                                                                                    
  -   Client is registered with the LwM2M Server                                                                                                                                                    |
| **Test Procedure**        | A READ operation from Server on the Device Object Instance has been received by the Client.                                                                                                      
                                                                                                                                                                                                    
  Normal flow:                                                                                                                                                                                      
                                                                                                                                                                                                    
  1.  READ (CoAP GET) operation on Device Object Instance (/3/0), with the CoAP Accept option set to TLV data format (11542)                                                                        
                                                                                                                                                                                                    
  2.  Bits 7-6=00= Object Instance in which case the Value contains one or more Resource TLVs                                                                                                       
                                                                                                                                                                                                    
  3.  Bits 7-6=11= Resource with Value                                                                                                                                                              |
| **Pass-Criteria**         | 1.  In test step 1. Server has received the “Success” message (2.05 Content), along with the requested information in the TLV data format (11542) and containing the expected values concerning: 
                                                                                                                                                                                                    
  -   Manufacturer Name (ID:0)                                                                                                                                                                      
                                                                                                                                                                                                    
  -   Model number (ID:1)                                                                                                                                                                           
                                                                                                                                                                                                    
  -   Serial number (ID:2)                                                                                                                                                                          
                                                                                                                                                                                                    
  -   Firmware Version (ID:3)                                                                                                                                                                       
                                                                                                                                                                                                    
  -   Error Code (ID:11)                                                                                                                                                                            
                                                                                                                                                                                                    
  -   Supported Binding and Modes (ID:16) (“U”)                                                                                                                                                     |

#### 

#### LightweightM2M-1.0-int-204 – Querying basic information in JSON format

|                           |                                                                                                                                                                                            |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-204                                                                                                                                                                 |
| **Test Object**           | Client and Server                                                                                                                                                                          |
| **Test Case Description** | Querying the Resources Values of Device Object ID:3 on the Client using JSON data format                                                                                                   |
| **Tool**                  | n/a                                                                                                                                                                                        |
| **Test code**             | n/a                                                                                                                                                                                        |
| **Preconditions**         | -   The Client supports the Configuration C.1 as defined in Annex C                                                                                                                        
                                                                                                                                                                                              
  -   Client is supporting JSON data format (11543)                                                                                                                                           
                                                                                                                                                                                              
  -   Client is registered with the LwM2M Server                                                                                                                                              |
| **Test Procedure**        | A READ operation from Server on the Device Object Instance has been received by the Client.                                                                                                
                                                                                                                                                                                              
  Normal flow:                                                                                                                                                                                
                                                                                                                                                                                              
  1.  READ (CoAP GET) operation on the Device Object Instance (/3/0), with the CoAP Accept option set to JSON data format (11543)                                                             |
| **Pass-Criteria**         | 1.  In test step 1. Server has received the success message (2.05 Content) along with the requested information in JSON data format (11543) and containing the expected values concerning: 
                                                                                                                                                                                              
  -   Manufacturer Name (ID:0)                                                                                                                                                                
                                                                                                                                                                                              
  -   Model number (ID:1)                                                                                                                                                                     
                                                                                                                                                                                              
  -   Serial number (ID:2)                                                                                                                                                                    
                                                                                                                                                                                              
  -   Firmware Version (ID:3)                                                                                                                                                                 
                                                                                                                                                                                              
  -   Error Code (ID:11)                                                                                                                                                                      
                                                                                                                                                                                              
  -   Supported Binding and Modes (ID:16) (“U”)                                                                                                                                               |

#### 

#### LightweightM2M-1.0-int-205 – Setting basic information in Plain Text format

| Test Case Id              | LightweightM2M-1.0-int-205                                                                                                                                                                         |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                  |
| **Test Case Description** | Setting writable Resources of Server Object (ID:1) Instance 0 using Plain Text data format (0)                                                                                                     |
| **Preconditions**         | -   The Client supports the Configuration C.3 as defined in Annex C                                                                                                                                
                                                                                                                                                                                                      
  -   Client is supporting Plain Text data format (0)                                                                                                                                                 
                                                                                                                                                                                                      
  -   Client is registered with the Server                                                                                                                                                            |
| **Test Procedure**        | Successive WRITE operations from Server on the Resources of the Server Object (ID:1) Instance have been received by the client. This test has to set the following resources with specific values: 
                                                                                                                                                                                                      
  -   Default minimum period (ID:2) : 0101 sec                                                                                                                                                        
                                                                                                                                                                                                      
  -   Default maximum period (ID:3) : 1010 sec                                                                                                                                                        
                                                                                                                                                                                                      
  -   Disable timeout (ID:5) : 2000 sec                                                                                                                                                               
                                                                                                                                                                                                      
  Normal flow:                                                                                                                                                                                        
                                                                                                                                                                                                      
  1.  Successive WRITE (CoAP PUT) operations are performed on the Resources of the Instance 0 of the Server Object in using the predefined values above. The Plain Text data format (0) is used       
                                                                                                                                                                                                      
  2.  The Server verifies (READs/CoAP GET) the result of the WRITE operations by querying the Instance 0 of the Server Object in using the TLV data format.                                           
                                                                                                                                                                                                      
  3.  The steps 1., 2. of the test are re-played with the initial values of the Configuration 3                                                                                                       |
| **Pass-Criteria**         | 1.  In test step 1. the Server receives a “Sucesss” message (2.04 Changed) for each WRITE operation                                                                                                
                                                                                                                                                                                                      
  2.  In test step 2, Server received the “Success” message (2.05 Content), along with the requested information in the TLV data format and containing the expected values defined for this test      
                                                                                                                                                                                                      
  3.  In test step 3, the final stage confirms that the initial Configuration C.3 has been restored in the Client.                                                                                    |

#### LightweightM2M-1.0-int-210 – Setting basic information in Opaque format

&lt;Test Cases to fill-up&gt;

#### LightweightM2M-1.0-int-215 – Setting basic information in TLV format

| **Test Case Id**          | LightweightM2M-1.0-int-215                                                                                                                                                                                        |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                 |
| **Test Case Description** | Setting writable Resources of Server Object (ID:1) Instance 0 in using the TLV data format (11542) and restoring these Resources to their initial values                                                          |
| **Preconditions**         | The Client supports the Configuration C.3 as defined in Annex C                                                                                                                                                   
                                                                                                                                                                                                                     
  The Client is registered with the Server                                                                                                                                                                           
                                                                                                                                                                                                                     
  The current values of the Server Object (ID:1) Instance 0, are saved on the Server                                                                                                                                 |
| **Test Procedure**        | A WRITE operation from Server on the Server Object (ID:1) Instance 0 has been received by the client using TLV data format (11542). The set of values to write is given in the sample below (215-SetOfValues)     
                                                                                                                                                                                                                     
  Normal flow:                                                                                                                                                                                                       
                                                                                                                                                                                                                     
  1.  A 1<sup>st</sup> WRITE (CoAP POST) operation on the Server Object (ID:1) Instance 0 is performed in using the set of values contains in the 215-SetOfValues sample below.The data format TLV is used. (11542)  
                                                                                                                                                                                                                     
  2.  The Server READs the result of the WRITE operation by querying the Server Object (ID:1) Instance 0.                                                                                                            
                                                                                                                                                                                                                     
  3.  A 2<sup>nd</sup> WRITE (CoAP PUT) operation on the Server Object (ID:1) Instance 0 is performed in using the Initial values preserved on the Server in conformance to the test pre-conditions.                 
                                                                                                                                                                                                                     
  4.  The Server READs the result of the previous WRITE operation by querying the Server Object (ID:1) Instance 0.                                                                                                   |
| **Pass-Criteria**         | 1.  The Server receives the success messages for the steps 1.(2.04), 2. (2.05), 3. (2.04) and 4. (2.05) of the test                                                                                               
                                                                                                                                                                                                                     
  2.  In test step 4. , the received values are consistent with the pre-defined values of the 215-SetOfValues sample                                                                                                 
                                                                                                                                                                                                                     
  3.  In test step 6, the received values are consistent with the values present in the initial Configuration C.3                                                                                                    |

#### LightweightM2M-1.0-int-220 – Setting basic information in JSON format 

| **Test Case Id**          | LightweightM2M-1.0-int-220                                                                                                                                                                                         |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                  |
| **Test Case Description** | Setting writable Resources of Server Object (ID:1) Instance 0 in using the JSON data format (11543) and restoring these Resources to their initial values                                                          |
| **Preconditions**         | The Client supports the Configuration C.3 as defined in Annex C                                                                                                                                                    
                                                                                                                                                                                                                      
  The Client is registered with the Server                                                                                                                                                                            
                                                                                                                                                                                                                      
  The current values of the Server Object (ID:1) Instance 0, are saved on the Server                                                                                                                                  |
| **Test Procedure**        | A WRITE operation from Server on the Server Object (ID:1) Instance 0 has been received by the client using JSON data format (11543). The set of values to write is given in the sample below (220-SetOfValues)     
                                                                                                                                                                                                                      
  Normal flow:                                                                                                                                                                                                        
                                                                                                                                                                                                                      
  1.  A 1<sup>st</sup> WRITE (CoAP POST) operation on the Server Object (ID:1) Instance 0 is performed in using the set of values contains in the 220-SetOfValues sample below.The data format JSON is used. (11543)  
                                                                                                                                                                                                                      
  2.  The Server READs the result of the WRITE operation by querying the the previously targeted Resources of the Server Object (ID:1) Instance 0.                                                                    
                                                                                                                                                                                                                      
  3.  A 2<sup>nd</sup> WRITE (CoAP PUT) operation on the Server Object (ID:1) Instance 0 is performed in using the Initial values which have been preserved (pre-conditions).                                         
                                                                                                                                                                                                                      
  4.  The Server READs the result of the previous WRITE operation by querying the Server Object (ID:1) Instance 0.                                                                                                    |
| **Pass-Criteria**         | 1.  The Server receives the correct status codes for the steps 1. (2.04), 2.(2.05), 3. (2.04) and 4. (2.05) of the test.                                                                                           
                                                                                                                                                                                                                      
  2.  In test step 2. , the received values are consistent with the 220-SetOfValues sample                                                                                                                            
                                                                                                                                                                                                                      
  3.  In test step 4, the received values are consistent with the values present in the initial Configuration 3                                                                                                       |

#### LightweightM2M-1.0-int-241 – Executable Resource: Rebooting the device

|                           |                                                                                                                                 |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-241                                                                                                      |
| **Test Object**           | Client and Server                                                                                                               |
| **Test Case Description** | Test that the Device can be remotely reboot via the Device Object (ID:3)                                                        |
| **Tool**                  | n/a                                                                                                                             |
| **Test code**             | n/a                                                                                                                             |
| **Preconditions**         | -   The client supports the Configuration C.1 as defined in Annex C                                                             
                                                                                                                                   
  -   Device is switched on                                                                                                        
                                                                                                                                   
  -   Client is registered with the Server. (Client might be in a state that requires a reboot)                                    |
| **Test Procedure**        | An EXECUTE operation from Server on the resource Reboot of the Device Object (ID:3) has been received by the client.            
                                                                                                                                   
  Normal flow:                                                                                                                     
                                                                                                                                   
  1.  Server performs Execute (CoAP POST) operation on the Reboot Resource of Device Object (ID:3) Instance                        
                                                                                                                                   
  2.  Client registers again with the Server as in the test LightweightM2M-1.0-int-101                                             |
| **Pass-Criteria**         | 1.  In test step 1, the Server receives the success message (2.04 Changed) related to the EXECUTE operation on the Client       
                                                                                                                                   
  2.  In test step2., Device reboots and the Client registers successfully with the Server again (see LightweightM2M-1.0-int-101)  |

#### LightweightM2M-1.0-int-260 – Discover Command 

| Test Case Id              | LightweightM2M-1.0-int-260                                                                                                                                                                                                                    |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                             |
| **Test Case Description** | Discovering the implemented Resources of the Device Object as well as reporting the various Attributes attached to Object / Object Instance and Resources                                                                                     |
| **Preconditions**         | -   The Client supports the Configuration C.4 as defined in Annex C                                                                                                                                                                           
                                                                                                                                                                                                                                                 
  -   The Client is registered with the Server                                                                                                                                                                                                   
                                                                                                                                                                                                                                                 
  -   No &lt;NOTIFICATION&gt; Attribute is initially attached to the Object Device                                                                                                                                                               |
| **Test Procedure**        | Various DISCOVER operations are performed by the Server on the Object Device. Several WRITE-ATTRIBUTES commands are interleaved to modify the content of the DISCOVER command replies                                                         
                                                                                                                                                                                                                                                 
  Normal flow:                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                 
  1.  The initial DISCOVER (CoAP GET Accept:40) operation is performed on Objet Device ID:3                                                                                                                                                      
                                                                                                                                                                                                                                                 
  2.  A WRITE-ATTRIBUTES operation set the pmin=10 & pmax=200 &lt;NOTIFICATION&gt; Attributes at the Object Instance level                                                                                                                       
                                                                                                                                                                                                                                                 
  3.  Same DISCOVER command as in test step 1., is performed                                                                                                                                                                                     
                                                                                                                                                                                                                                                 
  4.  The WRITE-ATTRIBUTES operation set the lt=1, gt=6 et st=1 &lt;NOTIFICATION&gt; Attributes of the Resource ID:7 (Power Source Voltage)                                                                                                      
                                                                                                                                                                                                                                                 
  5.  Same DISCOVER command as in test step 1. is performed                                                                                                                                                                                      
                                                                                                                                                                                                                                                 
  6.  DISCOVER operation is performed on Resource ID:7 of the Object Device Instance                                                                                                                                                             |
| **Pass-Criteria**         | 1.  In test step 1, the Success Message (“2.05” Content) is received by the Server along with the payload related to the DISCOVER request and containing :                                                                                    
                                                                                                                                                                                                                                                 
  > &lt; /3&gt;,&lt;/3/0/1&gt;, &lt;/3/0/2&gt;, &lt;/3/0/3&gt;, &lt;/3/0/4&gt;,&lt;/3/0/6&gt;;dim=2, &lt;/3/0/7&gt;;dim=2, &lt;/3/0/8&gt;;dim=2, &lt;/3/0/9&gt;,&lt;/3/0/11&gt;,&lt;/3/0/16&gt;                                                  
                                                                                                                                                                                                                                                 
  1.  In test step 2, a Success message is received by the Server (“2.04” Changed) related to the WRITE-ATTRIBUTES operation                                                                                                                     
                                                                                                                                                                                                                                                 
  2.  In test step 3, the Success message (“2.05” Content) is received by the Server along with the payload related to the DISCOVER request and containing :                                                                                     
                                                                                                                                                                                                                                                 
  > &lt; /3&gt;,&lt;/3/0&gt;;pmin=10;pmax=200,&lt;/3/0/1&gt;, &lt;/3/0/2&gt;, &lt;/3/0/3&gt;, &lt;/3/0/4&gt;, &lt;/3/0/6&gt;;dim=2, &lt;/3/0/7&gt;;dim=2, &lt;/3/0/8&gt;;dim=2, &lt;/3/0/9&gt;,&lt;/3/0/11&gt;,&lt;/3/0/16&gt;                   
                                                                                                                                                                                                                                                 
  1.  In test step 4, a “Success” message is received by the Server (“2.04” Changed) related to the WRITE-ATTRIBUTES operation                                                                                                                   
                                                                                                                                                                                                                                                 
  2.  In test step 5, the Success message (“2.05” Content) is received by the Server along with the same payload received in step 3, except for the Resource 7 :                                                                                 
                                                                                                                                                                                                                                                 
  > &lt; /3&gt;,&lt;/3/0&gt;;pmin=10;pmax=200,&lt;/3/0/1&gt;, &lt;/3/0/2&gt;, &lt;/3/0/3&gt;, &lt;/3/0/4&gt;, &lt;/3/0/6&gt;;dim=2, &lt;/3/0/7&gt;;dim=2, ;lt=1;gt=6;st=1, &lt;/3/0/8&gt;;dim=2,&lt;/3/0/9&gt;, &lt;/3/0/11&gt;,&lt;/3/0/16&gt;  
                                                                                                                                                                                                                                                 
  1.  In test step 6, the Success message (“2.05” Content) is received by the Server along with the payload related to the DISCOVER request and just containing :                                                                                
                                                                                                                                                                                                                                                 
  > &lt;/3/0/7&gt;;pmin=10;pmax=200;dim=2 ;lt=1;gt=6 ;st=1                                                                                                                                                                                       |

#### LightweightM2M-1.0-int-270 – Create Object Instance

As this functionality is not simply available through usage of Core Objects, the result of such Test Case is delegated to the result of any Test Case belonging to the following list:

-   LightweightM2M-1.0-int-1630 – Create Portfolio Object Instance

#### LightweightM2M-1.0-int-271 – Create Multiple Resource Instance

&lt;Test Cases to fill-up&gt;

#### LightweightM2M-1.0-int-290 – Delete Object Instance

As this functionality is not simply available through usage of Core Objects, the result of such Test Case is delegated to the result of any Test Case belonging to the following list:

-   LightweightM2M-1.0-int-1635 – Delete Portfolio Object Instance

### Information Reporting Interface \[300-399\]

#### LightweightM2M-1.0-int-301 – Observation and Notification of parameter values

|                           |                                                                                                                                                                                                                    |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-301                                                                                                                                                                                         |
| **Test Object**           | Client and Server                                                                                                                                                                                                  |
| **Test Case Description** | Sending the observation policy to the device.                                                                                                                                                                      |
| **Tool**                  | n/a                                                                                                                                                                                                                |
| **Test code**             | n/a                                                                                                                                                                                                                |
| **Preconditions**         | -   The Client supports the Configuration C.4 as defined in Annex C                                                                                                                                                
                                                                                                                                                                                                                      
  -   Device is switched on and operational.                                                                                                                                                                          
                                                                                                                                                                                                                      
  -   Client is registered with the LwM2M Server                                                                                                                                                                      |
| **Test Procedure**        | The Server establishes an Observation relationship with the Client to acquire conditional notifications about Resources from the Device Object Instance:                                                           
                                                                                                                                                                                                                      
  -   Power Source Voltage (ID:7)                                                                                                                                                                                     
                                                                                                                                                                                                                      
  -   Power Source Current (ID:8)                                                                                                                                                                                     
                                                                                                                                                                                                                      
  Normal flow:                                                                                                                                                                                                        
                                                                                                                                                                                                                      
  1.  Server Determines which Power Sources are on the Device (READ access to Resource ID:6 of Device Object ID:3)                                                                                                    
                                                                                                                                                                                                                      
  2.  Server communicates with the Device Object ID:3 via WRITE-ATTRIBUTE (CoAP PUT) operations, to set the pmin & pmax Attributes of each targeted Resources (e.g. /3/0/7?pmin=5&pmax=15 and /3/0/8?pmin10&pmax=20)  
                                                                                                                                                                                                                      
  3.  Server sends OBSERVE (CoAP GET operation with Observe Option set to 0) messages for the targeted Resources (ID:7 & ID:8 ) to activate reporting                                                                 
                                                                                                                                                                                                                      
  4.  Client reports requested information with a NOTIFY message (CoAP responses)                                                                                                                                     |
| **Pass-Criteria**         | 1.  The Server regularly receives the requested information and displays “Power Source Voltage” and “Power Source Current” values to the user if possible.                                                         |

#### 

#### LightweightM2M-1.0-int-302 – Cancel Observations using Reset Operation

|                           |                                                                                                                                                                                                                                                    |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-302                                                                                                                                                                                                                         |
| **Test Object**           | Client and Server                                                                                                                                                                                                                                  |
| **Test Case Description** | Cancel the Observation relationship by sending “Cancel Observation” operation.                                                                                                                                                                     |
| **Tool**                  | n/a                                                                                                                                                                                                                                                |
| **Test code**             | n/a                                                                                                                                                                                                                                                |
| **Preconditions**         | -   The client supports the Configuration C.4 as defined in Annex C                                                                                                                                                                                
                                                                                                                                                                                                                                                      
  -   Device is switched on and operational.                                                                                                                                                                                                          
                                                                                                                                                                                                                                                      
  -   Client is registered at the LwM2M Server                                                                                                                                                                                                        
                                                                                                                                                                                                                                                      
  -   Server established a successful Observation relationship with the Client as defined in Test Case Id: LightweightM2M-1.0-int-301                                                                                                                 |
| **Test Procedure**        | The Server removes a pre-established Observation relationship by sending “Cancel Observation”. The Client removes conditional notifications about:                                                                                                 
                                                                                                                                                                                                                                                      
  -   Power Source Voltage                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                      
  <!-- -->                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                      
  -   Power Source Current                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                      
  Normal flow:                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                      
  1.  Client reports requested information with NOTIFY messages (CoAP responses) on Resource ID:7 and ID:8                                                                                                                                            
                                                                                                                                                                                                                                                      
  2.  On receving a NOTIFY message from Resource ID:7, the Server sends a Cancel Observation (CoAP RESET message) to remove the Observation relationship with that Resource .                                                                         
                                                                                                                                                                                                                                                      
  3.  On receving a NOTIFY message from Resource ID:8, the Server sends a Cancel Observation (CoAP RESET message) to remove the Observation relationship with that Resource .                                                                         
                                                                                                                                                                                                                                                      
  4.  Client stops reporting requested information and removes associated entries from the list of observers.                                                                                                                                         |
| **Pass-Criteria**         | 1.  The Server receives regular NOTIFICATION from Device Object ID:3 on Resources Power Source Voltage (ID:7) and Power Source Current (ID:8)                                                                                                      
                                                                                                                                                                                                                                                      
  2.  The Server stops receiving information first on “Power Source Voltage” then on “Power Source Current” after having sent the Cancel Observation (Reset Operation) on that Resources. Associated entries from the list of observers are removed.  |

#### LightweightM2M-1.0-int-303 – Cancel observations using Observe with Cancel parameter

|                           |                                                                                                                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-303                                                                                                                                                                                                                                       |
| **Test Object**           | Client and Server                                                                                                                                                                                                                                                |
| **Test Case Description** | Cancel the Observation relationship by sending an OBSERVE operation with the CANCEL parameter                                                                                                                                                                    |
| **Tool**                  | n/a                                                                                                                                                                                                                                                              |
| **Test code**             | n/a                                                                                                                                                                                                                                                              |
| **Preconditions**         | -   The client supports the Configuration C4 as defined in Annex C                                                                                                                                                                                               
                                                                                                                                                                                                                                                                    
  -   Device is switched on and operational.                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                    
  -   Client is registered at the LwM2M Server                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                    
  -   Server established a successful Observation relationship with the Client as defined in Test Case Id: LightweightM2M-1.0-int-301                                                                                                                               |
| **Test Procedure**        | The Server removes a pre-established Observation relationship by sending “Observe” with Cancel Parameter. The Client removes conditional notifications about:                                                                                                    
                                                                                                                                                                                                                                                                    
  -   Power Source Voltage                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                    
  -   Power Source Current                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                    
  Normal flow:                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                    
  1.  Client reports requested information with a NOTIFY message (CoAP responses)                                                                                                                                                                                   
                                                                                                                                                                                                                                                                    
  2.  After receiving few notifications, Server sends OBSERVE operation with the CANCEL parameter (CoAP GET message with Observe option set to 1) to cancel the Observation relationship with the Instance of the Device Object (/3/0)                              
                                                                                                                                                                                                                                                                    
  <!-- -->                                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                    
  1.  Client stops reporting requested information on both Resources and removes associated entries from the list of observers.                                                                                                                                     |
| **Pass-Criteria**         | 1.  The Server receives regular NOTIFICATION from Device Object ID:3 on Resources Power Source Voltage (ID:7) and Power Source Current (ID:8)                                                                                                                    
                                                                                                                                                                                                                                                                    
  2.  The Server stops receiving information on “Power Source Voltage” and “Power Source Current” after having sent the Cancel Observation (with Cancel parameter) on the Device Object Instance (/3/0).Associated entries from the list of observers are removed.  |

### 

### Security \[400-499\]

#### LightweightM2M-1.0-int-401 – UDP Channel Security – Pre-shared Key Mode

|                           |                                                                                                                                                               |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-401                                                                                                                                    |
| **Test Object**           | Client and Server                                                                                                                                             |
| **Test Case Description** | Establishing a successful DTLS session using UDP pre-shared key mode                                                                                          |
| **Tool**                  | n/a                                                                                                                                                           |
| **Test code**             | n/a                                                                                                                                                           |
| **Preconditions**         | -   The client supports the Configuration C.1 as defined in Annex C                                                                                           
                                                                                                                                                                 
  -   The bootstrap procedure has been completed or the required bootstrap information is available to the client.                                               
                                                                                                                                                                 
  -   The bootstrap information includes the Security Mode resource of the object LwM2M Security set to 0: Pre-Shared Key mode                                   |
| **Test Procedure**        | Device is switched on .                                                                                                                                       
                                                                                                                                                                 
  A DTLS session is established between client and Server and the Client automatically registers with that Server                                                
                                                                                                                                                                 
  > Using this DTLS session, a simple data exchange is performed between the Server and the Client, to verify the encrypted connection is properly established.  
                                                                                                                                                                 
  Normal flow:                                                                                                                                                   
                                                                                                                                                                 
  1.  DTLS Session is established                                                                                                                                
                                                                                                                                                                 
  2.  Registration message (CoAP POST) is sent from LwM2M Client to LwM2M Server.                                                                                
                                                                                                                                                                 
  3.  Client receives Success message (2.01 Created) from the Server.                                                                                            
                                                                                                                                                                 
  4.  READ (CoAP GET) on the Instance of the Device Object is performed using the default TLV data format (cf Test LwM2M-1.0-int-203)                            
                                                                                                                                                                 
  5.  Server receives success message (2.05 Content) and the requested values (encrypted)                                                                        |
| **Pass-Criteria**         | 1.  In test step 2 & 3, Registration command of the Client on the Server is performed successfully over the DTLS session                                      
                                                                                                                                                                 
  2.  In test step 4 & 5 the READ command work successfully over the DTLS session.                                                                               |

### Core Specific Objects Test cases \[500-999\]

#### Security Object (ID 0) \[500-549\]

#### Server Object (ID 1) \[550-599\]

##### LightweightM2M-1.0-int-551 – Access Check to the Resources

LightweightM2M-1.0-int-215 Test Case (Setting basic information in TLV format) is covering the same functional scope than this LightweightM2M-1.0-int-551 Test Case. The Test Status of both Test Cases must be considered as identical.

##### LightweightM2M-1.0-int-555 – Check of the Disable (De-Registration) capability

&lt;Test Case to fill-up&gt;

Note : LightweightM2M-1.0-int-103 Test Case (De-Registration) is partially addressing the scope of this LightweightM2M-1.0-int-555 Test Case.

##### LightweightM2M-1.0-int-556 – Check of the Update Registration capability

LightweightM2M-1.0-int-104 Test Case (Registration Update Trigger) is covering the same functional scope than this LightweightM2M-1.0-int-556 Test Case. The Test Status of both Test Cases must be considered as identical.

##### LightweightM2M-1.0-int-560 – Delayed Report Notification

&lt;Test Cases to fill-up&gt;

##### LightweightM2M-1.0-int-565 – Create Object Instance

&lt;Test Cases to fill-up&gt;

##### LightweightM2M-1.0-int-566 – Delete Object Instance

&lt;Test Cases to fill-up&gt;

#### Access Control Object (ID 2) \[600-649\]

#### LwM2M Device Object (ID 3) \[650-699\]

##### LightweightM2M-1.0-int-651 – Check Access to the Resources

| **Test Case Id**          | LightweightM2M-1.0-int-651                                                                                                                                                                                                               |
|---------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                        |
| **Test Case Description** | Setting writable Resources of Device Object (ID:3) Instance in using the TLV data format (11542), checking the modifications and querying the readable Resources. Then restoring the Resources to their initial values with verification |
| **Preconditions**         | -   The Client supports the Configuration C.6 as defined in Annex C                                                                                                                                                                      
                                                                                                                                                                                                                                            
  -   The Client is registered with the Server                                                                                                                                                                                              
                                                                                                                                                                                                                                            
  -   The Initial values of the Device Object (ID:3) Instance, are saved on the Server                                                                                                                                                      |
| **Test Procedure**        | A WRITE operation from Server on the Device Object (ID:3) Instance has been received by the client using TLV data format (11542). The set of values to write is given in the sample below (651-SetOfValues)                              
                                                                                                                                                                                                                                            
  Normal flow:                                                                                                                                                                                                                              
                                                                                                                                                                                                                                            
  1.  A 1<sup>st</sup> WRITE (CoAP POST) operation on the Device Object (ID:3) Instance is performed in using the set of values contains in the 651-SetOfValues sample below.The data format TLV is used. (11542)                           
                                                                                                                                                                                                                                            
  2.  The Server READs the result of the WRITE operation by querying the Device Object (ID:3) Instance.                                                                                                                                     
                                                                                                                                                                                                                                            
  3.  A 2<sup>nd</sup> WRITE (CoAP PUT) operation on the Device Object (ID:3) Instance is performed in using the Initial values which have been preserved (pre-conditions).                                                                 
                                                                                                                                                                                                                                            
  4.  The Server READs the result of the previous WRITE operation by querying the Server Object (ID:3) Instance.                                                                                                                            |
| **Pass-Criteria**         | 1.  The Server receives the correct status codes for the steps 1. (2.04), 2. (2.05), 3. (2.04), & 4 (2.05) of the test.                                                                                                                  
                                                                                                                                                                                                                                            
  2.  In test step 3., the received values are as expected (readable resources) and consistent with the 651-SetOfValues sample.                                                                                                             
                                                                                                                                                                                                                                            
  3.  In test step 7, the received values are consistent with the values present in the initial Configuration C.3                                                                                                                           |

##### LightweightM2M-1.0-int-652 – Querying the firmware version from the client

|                           |                                                                                                                                  |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-652                                                                                                       |
| **Test Object**           | Client and Server                                                                                                                |
| **Test Case Description** | Querying the version of the firmware present in the LwM2M Client                                                                 |
| **Tool**                  | n/a                                                                                                                              |
| **Test code**             | n/a                                                                                                                              |
| **Preconditions**         | -   The Client supports the Configuration C.6 as defined in Annex C                                                              
                                                                                                                                    
  -   The Client is registered with the Server                                                                                      |
| **Test Procedure**        | A READ operation from Server on the Firmware Version Resource (ID:3) has been received by the Client.                            
                                                                                                                                    
  Normal flow:                                                                                                                      
                                                                                                                                    
  1.  READ (CoAP GET) operation is performed on Device Object Resource “Firmware Version”                                           |
| **lPass-Criteria**        | 1.  In test step 2, the Server received the requested information (Firmware Version ) in the data format preferred by the Client 
                                                                                                                                    
  2.  In test step 2 the Server receives the success message (2.05 Content)                                                         |

##### LightweightM2M-1.0-int-655 – Check of the “Reboot” capability

LightweightM2M-1.0-int-241 Test Case (Executable Resource: Rebooting the Device) is covering the same functional scope than this LightweightM2M-1.0-int-655 Test Case. The Test Status of both Test Cases must be considered as identical.

##### LightweightM2M-1.0-int-656 – Check of the “Factory Reset” capability

> Note : this test should be performed only if the client is able to carry out one of the Bootstrap methods defined in \[LwM2M TS 1.0\] section 5.2.3

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-657 – Check of the “Error Code” functionality

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-660 – Basic Observation and notification of Device Object Resources

LightweightM2M-1.0-int-301 Test Case (Observation and Notification of parameter values) is covering the same functional scope than this LightweightM2M-1.0-int-660 Test Case. The Test Status of both Test Cases must be considered as identical.

##### LightweightM2M-1.0-int-661 – Extended Observation and notification of Device Object Resources

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-670 – Create Multiple Resource Instances

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-680 – Create Object Instance 

Note : This operation is not allowed on this Object since the Device Object is a Mandatory and Single-instance Object.

|                           |                                                                                                                |
|---------------------------|----------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-680                                                                                     |
| **Test Object**           | Client and Server                                                                                              |
| **Test Case Description** | Verifying that Creating an Instance of the Device Object is not allowed                                        |
| **Tool**                  | n/a                                                                                                            |
| **Test code**             | n/a                                                                                                            |
| **Preconditions**         | -   The Client supports the Configuration C.1 as defined in Annex C                                            
                                                                                                                  
  -   The Client is registered with the Server                                                                    |
| **Test Procedure**        | A CREATE operationon targeting the Device Object ID:3 is performed by the Server and received by the Client.   
                                                                                                                  
  Normal flow:                                                                                                    
                                                                                                                  
  1.  CREATE (CoAP POST) operation is performed on Device Object                                                  |
| **Pass-Criteria**         | 1.  In test step 1, the Server receives the failure message (4.05 Method Not Allowed)                          |

##### LightweightM2M-1.0-int-685 – Delete Object Instance

Note : This operation is not allowed on this Object since the Device Object is a Mandatory and Single-instance Object fully maintained by the lwM2M Client. It must be always present when the Client is registered.

|                           |                                                                                                                                  |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-685                                                                                                       |
| **Test Object**           | Client and Server                                                                                                                |
| **Test Case Description** | Verifying that Deleting the Instance of the Device Object is not allowed                                                         |
| **Tool**                  | n/a                                                                                                                              |
| **Test code**             | n/a                                                                                                                              |
| **Preconditions**         | -   The Client supports the Configuration C.1 as defined in Annex C                                                              
                                                                                                                                    
  -   The Client is registered with the Server                                                                                      |
| **Test Procedure**        | A CREATE operationon targeting the Device Object ID:3 is performed by the Server and received by the Client.                     
                                                                                                                                    
  Normal flow:                                                                                                                      
                                                                                                                                    
  1.  DELETE (CoAP DELETE) operation is performed on the Device Object Instance (/3/0)                                              |
| **Pass-Criteria**         | 1.  In test step 1, the Server received the requested information (Firmware Version ) in the data format preferred by the Client 
                                                                                                                                    
  2.  In test step 1 the Server receives the failure message (4.05 Method Not Allowed)                                              |

#### LwM2M Connectivity Monitoring (ID:4) \[700-749\]

##### LightweightM2M-1.0-int-701 – Querying the readable resources of object

| Test Case Id              | LightweightM2M-1.0-int-701                                                                                                                                                                                                  |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                           |
| **Test Case Description** | Querying the readable Resources of the Connectivity Monitoring Object Instance and verifying the received values are as expected and coherent.                                                                              |
| **Preconditions**         | -   The Client supports the Configuration C.5 as defined in Annex C                                                                                                                                                         
                                                                                                                                                                                                                               
  -   Client is registered with the Server                                                                                                                                                                                     |
| **Test Procedure**        | A READ operation from Server on the Connectivity Monitoring Object Instance has been received by the Client.                                                                                                                
                                                                                                                                                                                                                               
  Normal flow:                                                                                                                                                                                                                 
                                                                                                                                                                                                                               
  1.  READ (CoAP GET) operation is performed by the Server on the Connectivity Monitoring Object Instance of the Client                                                                                                        |
| **Pass-Criteria**         | 1.  In test step 1., the Client received a READ (Coap GET) command from the Server on the Connectivity Monitoring Object Instance                                                                                           
                                                                                                                                                                                                                               
  2.  In test step 1., the Server receives the status code “2.05” for READ message success                                                                                                                                     
                                                                                                                                                                                                                               
  3.  In test step 1., along with the success message, the mandatory Resources (ID:0, 1,2, 4) and the optional ones, are received by the Server with expected values in compliance with LwM2M technical specification TS 1.0.  |

##### LightweightM2M-1.0-int-705 – Setting the writable resources

There is no writable resources for this object.

##### LightweightM2M-1.0-int-710 – Basic Observation and notification on Connectivity Monitoring Object Resources

| Test Case Id              | LightweightM2M-1.0-int-710                                                                                                                                                                                          |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                   |
| **Test Case Description** | Sending the observation policy to the Client for resources of Connectivity Monitoring (ID:4)                                                                                                                        |
| **Preconditions**         | -   The Client supports the Configuration C.5 as defined in Annex C                                                                                                                                                 
                                                                                                                                                                                                                       
  -   Device is switched on and operational                                                                                                                                                                            
                                                                                                                                                                                                                       
  -   Client is registered with the LwM2M server                                                                                                                                                                       |
| **Test Procedure**        | The Server establishes an Observation relationship with the Client to acquire condition notifications about the Connectivity Monitoring Object Instance.                                                            
                                                                                                                                                                                                                       
  Normal flow:                                                                                                                                                                                                         
                                                                                                                                                                                                                       
  1.  The Server communicates to the Client the pmin=2 and pmax=10 periods, threshold values with a WRITE ATTRIBUTE (CoAP PUT) operation at the Connectivity Monitoring Object Instance level                          
                                                                                                                                                                                                                       
  2.  The Server sends OBSERVE (CoAP Observe Option) message to activate reporting on the Monitoring Object Instance                                                                                                   
                                                                                                                                                                                                                       
  3.  The Client reports requested information with a NOTIFY message (CoAP response)                                                                                                                                   |
| **Pass-Criteria**         | 1.  In test step 1., the Client has received a WRITE ATTRIBUTE Command (CoAP PUT) targeting the Connectivity Monitoring Object Instance with the proper pmin=2, and pmax=10 parameters                              
                                                                                                                                                                                                                       
  2.  In test step 1, the Server received the success message (2.04 Changed) in response to the WRITE ATTRIBUTE command                                                                                                
                                                                                                                                                                                                                       
  3.  In test step 2. the Client received the OBSERVE operation targeting the Connectivity Monitoring Object Instance                                                                                                  
                                                                                                                                                                                                                       
  4.  In test step 2., in response to its OBSERVE request, the Server receives the success message (Content 2.05) along with the Connectivity Object Instance initial values                                           
                                                                                                                                                                                                                       
  5.  In test step 3., based on pmin/pmax periods parameters received in test step 1., the Client reports Information to the Server with a NOTIFY message containing the Connectivity Object Instance updated values.  
                                                                                                                                                                                                                       
  6.  In test step 3., the values receives by the Server along with the success message (Content 2.05) must be as expected                                                                                             |

##### LightweightM2M-1.0-int-711 – Extended Observation and notification of Connectivity Monitoring Object Resources

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-720 – Create Multiple Resource Instances 

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-730 – Create Object Instance

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-735 – Delete Object Instance

*&lt;Test Cases to fill-up&gt;*

#### 

#### Firmware Update Object (ID 5) \[750-799\]

##### LightweightM2M-1.0-int-751 – Querying the readable resources

1.  <span id="_Toc414291748" class="anchor"><span id="_Ref418006655" class="anchor"><span id="_Toc424318290" class="anchor"></span></span></span>

2.  3.  4.  5.  1.  2.  3.  4.  5.  6.  

| Test Case Id              | LightweightM2M-1.0-int-751                                                                                                                                                                                              |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                       |
| **Test Case Description** | Querying Information on the Firmware Update Object Instance for determining the current states and supported characteristics of the Client for such capability.                                                         |
| **Preconditions**         | -   The Client supports the Configuration C.8 as defined in Annex C                                                                                                                                                     
                                                                                                                                                                                                                           
  -   The Client is registered with the Server                                                                                                                                                                             
                                                                                                                                                                                                                           
  -   The Fw Update Object Instance is in its initial state (State=0)                                                                                                                                                      |
| **Test Procedure**        | A READ operation from the Server on the Firmware Update Object Instance requesting TLV format has been received by the client.                                                                                          
                                                                                                                                                                                                                           
  Normal flow:                                                                                                                                                                                                             
                                                                                                                                                                                                                           
  1.  READ (CoAP GET) operation is performed on the Firmware Update Object Instance                                                                                                                                        |
| **Pass-Criteria**         | 1.  In test step 1, the Server receives the status code “2.05” for READ operation success                                                                                                                               
                                                                                                                                                                                                                           
  2.  In test step 1, the returned values regarding State (ID:3) and Update Result (ID:5) prove the Client FW update Capability is in initial state (State=Idle & Update Result= Initial Value).                           
                                                                                                                                                                                                                           
  3.  In test step 1, the returned values regarding Firmware Update Protocol Support (ID:8) & Firmware Update Delivery Method (ID:9) allow to determine the supported characteristics of the Client FW Update Capability.  |

##### LightweightM2M-1.0-int-755 – Setting the writable Resource Package

| Test Case Id              | LightweightM2M-1.0-int-755                                                                                                                                                                                                                                                                                                    |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                                                                                                             |
| **Test Case Description** | Setting the writable Resource Package (ID:0) of Firmware Update Object Instance and verifying the triggered actions produce the expected results                                                                                                                                                                              |
| **Preconditions**         | -   The Client supports the Configuration C.8 as defined in Appendix C                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                 
  -   The Client is registered with the Server                                                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                                                                 
  -   According to Test LightweightM2M-1.0-int-751, the FW Update Object Instance supports the PUSH Delivery Method                                                                                                                                                                                                              |
| **Test Procedure**        | A WRITE operation from Server to set to NULL value (‘\\0’) the Resource Package (ID:0) has been received by the client. The test verifies the FW Update Object Instance is reset to its Initial state. Then a WRITE operation is performed by the Server to load a valid image in the Client in setting the Package Resource. 
                                                                                                                                                                                                                                                                                                                                 
  The various Resources of this FW Update Objects must be set as expected by the Client.                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                                 
  Normal flow:                                                                                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                                                                 
  1.  A WRITE (CoAP PUT) operation with a NULL value (‘\\0’) is performed by the Server on the Package Resource (ID:0) of the FW Update Object Instance                                                                                                                                                                          
                                                                                                                                                                                                                                                                                                                                 
  2.  The Server READs (CoAP GET) the FW Object Instance to get the values of the State (ID:3) and Update Result (ID:5) Resources                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                 
  3.  A WRITE (CoAP PUT) operation with a valid image is performed by the Server on the Package Resource (ID:0) of the FW Update Object Instance                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                                 
  4.  The Server READs (CoAP GET) the FW Object Instance to get the values of the State (ID:3) and Update Result (ID:5) Resources                                                                                                                                                                                                |
| **Pass-Criteria**         | 1.  In test step 1, the Server receives the success message “2.04” associated with the WRITE operation                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                 
  2.  In test step 2, the Server receives the success message “2.05” along with the value of State and Update Result Resources values.                                                                                                                                                                                           
                                                                                                                                                                                                                                                                                                                                 
  3.  In test step 2, the queried State and Update Result Resources values are both 0 (Idle / Initial value): FW Update Object Instance is in the Initial state.                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                                 
  4.  In test step 3, the Server receives the success message “2.04” associated with the WRITE request for loading the firmware image.                                                                                                                                                                                           
                                                                                                                                                                                                                                                                                                                                 
  5.  In test step 4, the Server receives the success message “2.05” along with the State and Update Result Resources values.                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                                 
  6.  In test step 4, the queried value of State resource is 2 (Downloaded) and the value of Update Result value is still 0 (Initial Value)                                                                                                                                                                                      |

##### LightweightM2M-1.0-int-756 – Setting the writable Resource Package URI

| Test Case Id              | LightweightM2M-1.0-int-756                                                                                                                                                                                                                                                                                                        |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                                                                                                                 |
| **Test Case Description** | Setting the writable Resource Package URI (ID:1) of Firmware Update Object Instance and verifying the triggered actions produce the expected results                                                                                                                                                                              |
| **Preconditions**         | -   The Client supports the Configuration C.8 as defined in Appendix C                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                                     
  -   The Client is registered with the Server                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                     
  -   According to Test LightweightM2M-1.0-int-751, the FW Update Object Instance supports the PULL Delivery Method                                                                                                                                                                                                                  |
| **Test Procedure**        | A WRITE operation from Server to set the empty string to the Resource Package URI (ID:0) has been received by the client. The test verifies the FW Update Object Instance is reset to its Initial state. Then a WRITE operation is performed by the Server to load a valid URI in the Client in setting the Package URI Resource. 
                                                                                                                                                                                                                                                                                                                                     
  The various Resources of this FW Update Objects must be set as expected by the Client.                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                                                     
  Normal flow:                                                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                     
  1.  A WRITE (CoAP PUT) operation with an empty string value is performed by the Server on the Package Resource (ID:0) of the FW Update Object Instance                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                                                     
  2.  The Server READs (CoAP GET) the FW Object Instance to get the values of the State (ID:3) and Update Result (ID:5) Resources                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                                     
  3.  A WRITE (CoAP PUT) operation with a valid image is performed by the Server on the Package Resource (ID:0) of the FW Update Object Instance                                                                                                                                                                                     
                                                                                                                                                                                                                                                                                                                                     
  4.  The Server READs (CoAP GET) the FW Object Instance to get the values of the State (ID:3) and Update Result (ID:5) Resources                                                                                                                                                                                                    |
| **Pass-Criteria**         | 1.  In test step 1, the Server receives the success message “2.04” associated with the WRITE operation                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                                                                     
  2.  In test step 2, the Server receives the success message “2.05” along with the value of State and Update Result Resources values.                                                                                                                                                                                               
                                                                                                                                                                                                                                                                                                                                     
  3.  In test step 2, the queried State and Update Result Resources values are both 0 (Idle / Initial value): FW Update Object Instance is in the Initial state.                                                                                                                                                                     
                                                                                                                                                                                                                                                                                                                                     
  4.  In test step 3, the Server receives the success message “2.04” associated with the WRITE request for the loadded image.                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                     
  5.  In test step 4, the Server receives the success message “2.05” along with the State and Update Result Resources values.                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                     
  6.  In test step 4, the queried value of State resource is 2 (Downloaded) and the value of Update Result value is still 0 (Initial Value)                                                                                                                                                                                          |

##### LightweightM2M-1.0-int-760 –Basic Observation and notification on Firmware Update Object Resources

| Test Case Id              | LightweightM2M-1.0-int-760                                                                                                                               |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                        |
| **Test Case Description** | Sending the observation policy to the Client for State Resource of Firmware Update Object (ID:5)                                                         |
| **Preconditions**         | -   The Client supports the Configuration C.8 as defined in Appendix C                                                                                   
                                                                                                                                                            
  -   Device is switched on and operational                                                                                                                 
                                                                                                                                                            
  -   Client is registered at the LwM2M server                                                                                                              
                                                                                                                                                            
  -   According to Test LightweightM2M-1.0-int-751, the FW Update Object Instance supports the PUSH Delivery Method                                         
                                                                                                                                                            
  -   Test LightweightM2M-1.0-int-755 already passed (an firmware image can be successfully loaded)                                                         
                                                                                                                                                            
      -   The Client is in Initial State regarding the FW Update functionality (State=Idle)                                                                 |
| **Test Procedure**        | The Server establishes an Observation relationship with the Client to acquire notifications about State Resource of the Fw Update Object Instance        
                                                                                                                                                            
  Normal flow:                                                                                                                                              
                                                                                                                                                            
  1.  The Server communicates to the Client pmin=2 and pmax=10 periods with a WRITE-ATTRIBUTE (CoAP PUT) operation at the FW Update Object Instance level.  
                                                                                                                                                            
  2.  The Server Sends OBSERVE (CoAP Observe Option) message to activate reporting on the State Resource (/5/0/3) of the FW Update Object Instance.         
                                                                                                                                                            
  3.  The Server delivers the firmware to the Client through a WRITE (CoAP PUT) operation on the Package Resource (/5/0/0)                                  
                                                                                                                                                            
  4.  The Client reports requested information with a NOTIFY message (CoAP response)                                                                        |
| **Pass-Criteria**         | 1.  In test step 1, the Server receives the success message “2.04” associated with the WRITE-ATTRIBUTE operation.                                        
                                                                                                                                                            
  2.  In test step 2, the Server receives the success message “2.05” associated with the OBSERVE operation, along with the value of State =Idle             
                                                                                                                                                            
  3.  In test step 3, the Server receives the success message “2.04” associated with the WRITE operation delivering the firmaware image.                    
                                                                                                                                                            
  4.  In test step 4, the State Resource value returned by the Client in NOTIFY message is set to “Downloaded”                                              |

##### LightweightM2M-1.0-int-770 – Successful Firmware update (via COAP)

| Test Case Id              | LightweightM2M-1.0-int-770                                                                                                                                                                                                                                    |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                                             |
| **Test Case Description** | Perform a device firmware update remotely triggered by the LWM2M server in using Package Resource (CoAP mechanisms)                                                                                                                                           |
| **Preconditions**         | -   The Client supports the Configuration C.8 as defined in Annex C                                                                                                                                                                                           
                                                                                                                                                                                                                                                                 
  -   According to Test LightweightM2M-1.0-int-751, the FW Update Object Instance supports the PULL Delivery Method                                                                                                                                              
                                                                                                                                                                                                                                                                 
  -   The Client already passed the LightweightM2M-1.0-int-755 test                                                                                                                                                                                              
                                                                                                                                                                                                                                                                 
  -   Device is switched on and operational                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                 
  -   The Client is registered with the LWM2M server                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                 
  -   Firmware Update is available on the Server                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                 
  -   State is “0” (Idle) or “1” (Downloaded)                                                                                                                                                                                                                    |
| **Test Procedure**        | After setting the Client in the Initial stage for supporting Firmware Update process, the Server delivers the Package to the Client before to trigger the installation of the downloaded firmware. Finally, the Server checks the result of the full process. 
                                                                                                                                                                                                                                                                 
  Normal flow:                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                 
  1.  **Step 1 – Package Delivery**                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                 
  <!-- -->                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                 
  1.  The Server places the Client in the initial state of the FW Update process : A WRITE (CoAP PUT) operation with a NULL value (‘\\0’) is performed by the Server on the Package Resource (ID:0) of the FW Update Object Instance                             
                                                                                                                                                                                                                                                                 
  2.  The Server delivers the firmware to the Client through a WRITE (CoAP PUT) operation on the Package Resource (/5/0/0)                                                                                                                                       
                                                                                                                                                                                                                                                                 
  3.  Polling (READ command) or Notification on Update Result and State Resources is performed, up to the time State Resource takes the ‘Downloaded’ value (2)                                                                                                   
                                                                                                                                                                                                                                                                 
  <!-- -->                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                 
  1.  **Step 2 – Firmware Update**                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                 
  <!-- -->                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                 
  1.  When the download is completed (State Resource value is ‘2’ Downloaded) , the Server initiates a firmware update by triggering EXECUTE command on Update Resource (CoAP POST /5/0/2)                                                                       
                                                                                                                                                                                                                                                                 
  2.  Polling (READ command) or Notification on Update Result and State Resources is performed, up to the time State Resource is turned back to Idle value (0) or Update Result Resource contains an other value than the Initial one (0)                        
                                                                                                                                                                                                                                                                 
  <!-- -->                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                 
  1.  **Step 3 – Process verification**                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                 
  <!-- -->                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                 
  1.  The Server READs Update Result (“/5/0/5”) and State (“/5/0/3”) Resources to know the result of the firmware update procedure.                                                                                                                              
                                                                                                                                                                                                                                                                 
  <!-- -->                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                 
  1.  The Server READs the Resource “Firmware Update” from the Object Device Instance (“/3/0/3”)                                                                                                                                                                 |
| **Pass-Criteria**         | 1.  **Step 1 – Package Delivery**                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                 
      1.  In the test step 1.a, the Server receives the status code “2.04” for the WRITE success setting the Client in the FW update initial state.                                                                                                              
                                                                                                                                                                                                                                                                 
      2.  In the test step 1.b, The Server receives success message with either a “2.31” status code (Continue) or a final “2.04” status code.                                                                                                                   
                                                                                                                                                                                                                                                                 
      3.  In the test step 1.c State Resource can take the value “1” (Downloading) during this sub-step and will take the value “2” at the end (Downloaded)                                                                                                      
                                                                                                                                                                                                                                                                 
      4.  Update Result is “0” (Initial Value) during the whole step                                                                                                                                                                                             
                                                                                                                                                                                                                                                                 
  2.  **Step 2 – Firmware Update**                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                 
  <!-- -->                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                 
  1.  In test step 2.a, the Server receives a success message “2.04” (Changed) in response to the EXECUTE command                                                                                                                                                
                                                                                                                                                                                                                                                                 
  2.  In test step 2.b, the Server receives success message(s) “2.05” Contents along with a State Resource value of “3” (Updating) or “0” (Idle) and an Update Ressource value of “0” (Initial Value) or “1” (Firmware updated successfully)                     
                                                                                                                                                                                                                                                                 
  <!-- -->                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                 
  1.  **Step 3 – Process verification**                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                 
  <!-- -->                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                 
  1.  In test step 3.a, the Server receives success message(s) “2.05” Content” along with a State Resource value of “0” (Idle) and an Update Ressource value of “1” (Firmware updated successfully)                                                              
                                                                                                                                                                                                                                                                 
  2.  In test step 3.b, the Server receives success message “2.05” Content” along with the expected value of the Resource Firmware Version from the Object Device Instance                                                                                       |

##### LightweightM2M-1.0-int-771 – Successful Firmware update (via alternative mechanism)

| Test Case Id              | LightweightM2M-1.0-int-771                                                                                                                                                                                                                                                                                              |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                                                                                                       |
| **Test Case Description** | Perform a device firmware update remotely triggered by the LwM2M server in using Package URI Resource                                                                                                                                                                                                                   |
| **Preconditions**         | -   The Client supports the Configuration C.8 as defined in Annex C                                                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                                                                                           
  -   According to Test LightweightM2M-1.0-int-751, the FW Update Object Instance supports the PUSH Delivery Method                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                           
  -   The Client passed the LightweightM2M-1.0-int-755 test                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                           
  -   Device is switched on and operational                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                           
  -   The Client is registered with the LwM2M server                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                           
  -   Firmware Update is available on the Server                                                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                                                                           
  -   State is “0” (Idle) or “1” (Downloaded)                                                                                                                                                                                                                                                                              |
| **Test Procedure**        | After setting the Client in the Initial stage for supporting Firmware Update process, the Server delivers the Package URI to the Client, waits for the firmware to be downloaded and then triggers the installation of the downloaded firmware. Finally, the Server checks the result of the full process. Normal flow: 
                                                                                                                                                                                                                                                                                                                           
  1.  **Step 1 – Package Delivery**                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                           
  <!-- -->                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                           
  1.  The Server places the Client in the initial state of the FW Update process : A WRITE (CoAP PUT) operation with an empty string value is performed by the Server on the Package URI Resource (ID:1) of the FW Update Object Instance                                                                                  
                                                                                                                                                                                                                                                                                                                           
  2.  The Server delivers the Package URI to the Client through a WRITE (CoAP PUT) operation on the Package URI Resource (/5/0/1)                                                                                                                                                                                          
                                                                                                                                                                                                                                                                                                                           
  3.  The Client downloads the firmware from the provided URI via an alternative mechanism (not CoAP)                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                           
  4.  Polling ( successive READ commands) or Notification on Update Result and State Resources is performed, up to the time State Resource takes the ‘Downloaded’ value (2)                                                                                                                                                
                                                                                                                                                                                                                                                                                                                           
  <!-- -->                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                           
  1.  **Step 2 – Firmware Update**                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                           
  <!-- -->                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                           
  1.  When the download is completed (State Resource value is ‘2’ Downloaded) , the Server initiates a firmware update by triggering EXECUTE command on Update Resource (CoAP POST /5/0/2 )                                                                                                                                
                                                                                                                                                                                                                                                                                                                           
  2.  Polling (READ command) or Notification on Update Result and State Resources is performed, up to the time State Resource is turned back to Idle value (0) or Update Result Resource contains an other value than the Initial one (0)                                                                                  
                                                                                                                                                                                                                                                                                                                           
  <!-- -->                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                           
  1.  **Step 3 – Process verification**                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                           
  <!-- -->                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                           
  1.  The Server READs Update Result (“/5/0/5”) and State (“/5/0/3”) Resources to know the result of the firmware update procedure.                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                           
  2.  The Server READs the Resource “Firmware Update” from the Object Device Instance (“/3/0/3”)                                                                                                                                                                                                                           |
| **Pass-Criteria**         | 1.  **Step 1 – Package Delivery**                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                           
      1.  In the test step 1.a, the Server receives the status code “2.04” for the WRITE success setting the Client in the FW update initial state.                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                           
      2.  In the test step 1.b, the Server receives the status code “2.04” for the WRITE success setting the Package URI Client in the FW update Object Instance                                                                                                                                                           
                                                                                                                                                                                                                                                                                                                           
      3.  In the test step 1.c, The Server receives success message with either a “2.31” status code (Continue) or a final “2.04” status code.                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                                           
      4.  In the test step 1.d State Resource can take the value “1” (Downloading) during this sub-step and will take the value “2” at the end (Downloaded)                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                           
      5.  Update Result is “0” (Initial Value) during the whole test step 1                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                           
  2.  **Step 2 – Firmware Update**                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                           
  <!-- -->                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                           
  1.  In test step 2.a, the Server receives a success message “2.04” (Changed) in response to the EXECUTE command                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                                                                           
  2.  In test step 2.b, the Server receives success message(s) “2.05” Contents along with a State Resource value of “3” (Updating) or “0” (Idle) and an Update Ressource value of “0” (Initial Value) or “1” (Firmware updated successfully)                                                                               
                                                                                                                                                                                                                                                                                                                           
  <!-- -->                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                           
  1.  **Step 3 – Process verification**                                                                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                                                           
  <!-- -->                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                           
  1.  In test step 3.a, the Server receives success message(s) “2.05” Content” along with a State Resource value of “0” (Idle) and an Update Ressource value of “1” (Firmware updated successfully)                                                                                                                        
                                                                                                                                                                                                                                                                                                                           
  2.  In test step 3.b, the Server receives success message “2.05” Content” along with the expected value of the Resource Firmware Version from the Object Device Instance                                                                                                                                                 |

##### LightweightM2M-1.0-int-772 – Error Case 1: firmware installation without downloaded package

<table>
<thead>
<tr class="header">
<th>Test Case Id</th>
<th>LightweightM2M-1.0-int-772</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Test Object</strong></td>
<td>Client and Server</td>
</tr>
<tr class="even">
<td><strong>Test Case Description</strong></td>
<td>Try to perform a Device firmware installation when there is no downloaded firmware package</td>
</tr>
<tr class="odd">
<td><strong>Preconditions</strong></td>
<td><ul>
<li><p>The Client supports the Configuration C.8 as defined in Annex C</p></li>
<li><p>Device is switched on and operational</p></li>
<li><p>Client is registered with the LwM2M server</p></li>
<li><p>Firmware Update is available on the Server</p></li>
<li><p>The State Resource (/5/0/3) of the FW Object Instance is different from “2” (Downloaded)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Test Procedure</strong></td>
<td><p>The Server initiates a firmware installation on the Client while this Client has no downloaded package in it.<br />
Normal flow:</p>
<ol style="list-style-type: decimal">
<li><p>The Server send a READ operation (CoAP GET /5/0) to the Client on the FW Update Object Instance to obtain the values of the State and Update Resources.</p></li>
<li><p>the Client receives an EXECUTE operation on the Update Resource (CoAP POST /5/0/2 ) of the FW Update Object Instance</p></li>
<li><p>The Server send a READ operation again (CoAP GET /5/0/3) to the Client on the FW Update Object Instance to obtain the State and the Update Resource values</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>Pass-Criteria</strong></td>
<td><ol style="list-style-type: upper-alpha">
<li><p>In test step 1, the Server receives a success message (“2.05” Content) associated to its READ command along with a State Resource value which is not “2” (Downloaded) and a valid (0..9) Update Resource value</p></li>
<li><p>In test step 2, the Server receives the status code “4.05” for method not allowed associated to its EXECUTE command</p></li>
<li><p>In test step 3, the Server receives a success message (“2.05” Content) associated to its READ command along with a State Resource value and an Update Result Resource value, identical to the ones retrieved in Pass-Criteria A. The firmware has not bee installed.</p></li>
</ol></td>
</tr>
</tbody>
</table>

##### 

##### LightweightM2M-1.0-int-773 – Error Case 2: shortage of storage memory

<table>
<thead>
<tr class="header">
<th>Test Case Id</th>
<th>LightweightM2M-1.0-int-773</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Test Object</strong></td>
<td>Client and Server</td>
</tr>
<tr class="even">
<td><strong>Test Case Description</strong></td>
<td>Try to perform a Device firmware update remotely triggered by the LWM2M Server with a firmware package exceeding the Client storage memory capacity.</td>
</tr>
<tr class="odd">
<td><strong>Preconditions</strong></td>
<td><ul>
<li><p>The Client supports the Configuration C.8 as defined in Annex C</p></li>
<li><p>Prepare a package with a size exceeding the Client storage memory capacity</p></li>
<li><p>Device is switched on and operational</p></li>
<li><p>Client is registered with the LwM2M server</p></li>
<li><p>Firmware Update is available on the Server</p></li>
<li><p>The State Resource (/5/0/3) of the FW Object Instance is set to “0” (Idle)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Test Procedure</strong></td>
<td><p>A Package delivery initiated by a Server in using either PULL or PUSH delivery methods with a firmware package exceeding the Client storage memory capacity, is received by the Client<br />
Normal flow:</p>
<ol style="list-style-type: decimal">
<li><blockquote>
<p>The Server verifies through a READ (CoAP GET) command on /5/0/3 (State) the FW Update Object Instance of the Client is in Idle State</p>
</blockquote></li>
<li><blockquote>
<p>The Server delivers the firmware package to the Client either through a WRITE (CoAP PUT) operation in the Package Resource (/5/0/0) or through a WRITE operation of an URI in the Package URI Resource.</p>
</blockquote></li>
<li><blockquote>
<p>The firmware downloading process is runing The Server sends repeated READs or OBSERVE on State and Update Result Resources (CoAP GET /5/0) of the FW Update Object Instance to determine when the download is completed or if an error occured.Before the end of download, the device runs out of storage and cannot finish the download</p>
</blockquote></li>
<li><blockquote>
<p>When the Package delivery is stopped the server READs Update Result to know the result of the firmware update procedure.</p>
</blockquote></li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>Pass-Criteria</strong></td>
<td><ol style="list-style-type: upper-alpha">
<li><p>In test step 1, the Server receives the status code “2.05 “ (Content) for the READ success command, along with the State Resource value of “0” (Idle)</p></li>
<li><p>In test step 2., the Server receives the status code “2.04” (Changed) for the WRITE command setting either the Package URI Resource or setting the Package Resource, according to the chosen firmware delivery method.</p></li>
<li><p>In test step 3., the State Resource retrieved with a value of “1” from successive Server READs or Client NOTIFY messages, indicates the download stage of the Package Delivery is engaged</p></li>
<li><p>In test step 3., the Update Result Resource (/5/0/5) retrieved from successive Server READs or Client NOTIFY messages will take the value “2” indicating an error occurred during the downloading process related to shortage of storage memory The State Resource value never reaches the Downloaded value (“3”)</p></li>
<li><p>In test step 4., the success READ message(s) (status code “2.05” Content) on State Resource with value “0” (Idle) and Update Result Resource with value “2” indicates the firmware Package Delivery aborted due to shortage of storage memory.</p></li>
</ol></td>
</tr>
</tbody>
</table>

##### LightweightM2M-1.0-int-774 – Error Case 3: out of memory

<table>
<thead>
<tr class="header">
<th>Test Case Id</th>
<th>LightweightM2M-1.0-int-774</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Test Object</strong></td>
<td>Client and Server</td>
</tr>
<tr class="even">
<td><strong>Test Case Description</strong></td>
<td>Try to perform a Device firmware update remotely triggered by the LWM2M Server while the Client runs out of RAM during download</td>
</tr>
<tr class="odd">
<td><strong>Preconditions</strong></td>
<td><ul>
<li><p>The Client supports the Configuration C.8 as defined in Annex C</p></li>
<li><p>Prepare a firmware package to make the Client running out of RAM when downloading it.</p></li>
<li><p>Device is switched on and operational</p></li>
<li><p>Client is registered at the LwM2M server</p></li>
<li><p>Firmware Update is available on the Server</p></li>
<li><p>The State Resource (/5/0/3) of the FW Object Instance is set to “0” (Idle)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Test Procedure</strong></td>
<td><p>A Package delivery initiated by a Server using either PULL or PUSH delivery methods is received by the Client. This firmware package will make the Client to run out of RAM during its download,<br />
Normal flow:</p>
<ol style="list-style-type: decimal">
<li><p>The Server verifies through a READ (CoAP GET) command on /5/0/3 (State) the FW Update Object Instance of the Client is in Idle State</p></li>
<li><p>The Server delivers the firmware package to the Client either through a WRITE (CoAP PUT) operation in the Package Resource (/5/0/0) or through a WRITE operation of an URI in the Package URI Resource.</p></li>
<li><p>The firmware download process is runing The Server sends repeated READs or OBSERVE on State and Update Result Resources (CoAP GET /5/0) of the FW Update Object Instance to determine when the download is completed or if an error occured.Before the end of download, the Client runs out of RAM and cannot finish the download</p></li>
<li><p>When the Package delivery is stopped the server READs Update Result to know the result of the firmware update procedure.</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>Pass-Criteria</strong></td>
<td><ol style="list-style-type: upper-alpha">
<li><p>In test step 1, the Server receives the status code “2.05 “ (Content) for the READ success command, along with the State Resource value of “0” (Idle)</p></li>
<li><p>In test step 2., the Server receives the status code “2.04” (Changed) for the WRITE command setting either the Package URI Resource or setting the Package Resource, according to the chosen firmware delivery method.</p></li>
<li><p>In test step 3., the State Resource retrieved with a value of “1” from successive Server READs or Client NOTIFY messages, indicates the download stage of the Package Delivery is engaged</p></li>
<li><p>In test step 3., the Update Result Resource (/5/0/5) retrieved from successive Server READs or Client NOTIFY messages will take the value “2” indicating an error occurred during the download process related to shortage of RAM The State Resource value never reaches the Downloaded value (“3”)</p></li>
<li><p>In test step 4., the success READ message(s) (status code “2.05” Content) on State Resource with value “0” (Idle) and Update Result Resource with value “2” indicates the firmware Package Delivery aborted due to shortage of RAM.</p></li>
</ol></td>
</tr>
</tbody>
</table>

##### LightweightM2M-1.0-int-775 – Error Case 4: Connection lost during download (package URI)

<table>
<thead>
<tr class="header">
<th>Test Case Id</th>
<th>LightweightM2M-1.0-int-775</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Test Object</strong></td>
<td>Client and Server</td>
</tr>
<tr class="even">
<td><strong>Test Case Description</strong></td>
<td>Try to perform a Device firmware update remotely triggered by the LWM2M server while connection is lost during download</td>
</tr>
<tr class="odd">
<td><strong>Preconditions</strong></td>
<td><ul>
<li><blockquote>
<p>The Client supports the Configuration C.8 as defined in Annex C</p>
</blockquote></li>
<li><blockquote>
<p>Prepare a method for loosing the connection when firmware package download is engaged.</p>
</blockquote></li>
<li><blockquote>
<p>Device is switched on and operational</p>
</blockquote></li>
<li><blockquote>
<p>Client is registered at the LwM2M server</p>
</blockquote></li>
<li><blockquote>
<p>Firmware Update is available on the Server</p>
</blockquote></li>
<li><blockquote>
<p>The State Resource (/5/0/3) of the FW Object Instance is set to “0” (Idle)</p>
</blockquote></li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Test Procedure</strong></td>
<td><p>A Package delivery initiated by a Server in using either the PULL delivery methods is received by the Client<br />
Normal flow:</p>
<ol style="list-style-type: decimal">
<li><p>The Server verifies through a READ (CoAP GET) command on /5/0/3 (State) the FW Update Object Instance of the Client is in Idle State</p></li>
<li><p>The Server delivers the firmware package to the Client through a WRITE operation of an URI in the Package URI Resource.</p></li>
<li><p>The Server sends repeated READs or OBSERVE on State and Update Result Resources (CoAP GET /5/0) of the FW Update Object Instance to determine when the download is completed or if an error occured.Before the end of download, the connection is intentionnaly lost and the download cannot be finished.</p></li>
<li><p>When the Package delivery is stopped the Server READs Update Result to know the result of the firmware update procedure.</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>Pass-Criteria</strong></td>
<td><ol style="list-style-type: upper-alpha">
<li><p>In test step 1., the Server receives the status code “2.05 “ (Content) for the READ success command, along with the State Resource value of “0” (Idle)</p></li>
<li><p>In test step 2., the Server receives the status code “2.04” (Changed) for the WRITE command setting the Package URI Resource according to the PULL firmware delivery method.</p></li>
<li><p>In test step 3., the State Resource value set to “1” retrieved from successive Server READs or Client NOTIFY messages, indicates the Package Delivery process is engaged in a Download stage</p></li>
<li><p>In test step 3., the Update Result Resource (/5/0/5) retrieved from successive Server READs or Client NOTIFY messages will take the value “4” indicating an error occurred during the downloading process related to connection lost</p></li>
<li><p>In test step 4., the success READ message(s) (status code “2.05” Content) on State Resource with value “0” (Idle) and Update Result Resource with value “4” indicates the firmware Package Delivery aborted due to connection lost dur the Package delivery.</p></li>
</ol></td>
</tr>
</tbody>
</table>

##### LightweightM2M-1.0-int-776 – Error Case 5: Package Integrity check failure

<table>
<thead>
<tr class="header">
<th>Test Case Id</th>
<th>LightweightM2M-1.0-int-776</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Test Object</strong></td>
<td>Client and Server</td>
</tr>
<tr class="even">
<td><strong>Test Case Description</strong></td>
<td>Try to perform a device firmware update remotely triggered by the LWM2M Server while the downloaded package does not pass the integrity check</td>
</tr>
<tr class="odd">
<td><strong>Preconditions</strong></td>
<td><ul>
<li><p>The Client supports the Configuration C.8 as defined in Annex C</p></li>
<li><p>Prepare a firmware package with a wrong Data Integrity Check in it.</p></li>
<li><p>Device is switched on and operational</p></li>
<li><p>Client is registered at the LwM2M server</p></li>
<li><p>Firmware Update is available on the Server</p></li>
<li><p>The State Resource (/5/0/3) of the FW Object Instance is set to “0” (Idle)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Test Procedure</strong></td>
<td><p>A Package delivery initiated by a Server in using either PULL or PUSH delivery methods is received by the Client. This firmware package has been generated with a wrong Data Integrity Check,<br />
Normal flow:</p>
<ol style="list-style-type: decimal">
<li><p>The Server verifies through a READ (CoAP GET) command on /5/0/3 (State) the FW Update Object Instance of the Client is in Idle State</p></li>
<li><p>The Server delivers the firmware package to the Client either through a WRITE (CoAP PUT) operation in the Package Resource (/5/0/0) or through a WRITE operation of an URI in the Package URI Resource.</p></li>
<li><p>The Server sends repeated READs or OBSERVE on State and Update Result Resources (CoAP GET /5/0) of the FW Update Object Instance to determine when the download is completed or if an error occured. The firmware package Integry Check failure stopped the download process.</p></li>
<li><p>When the Package delivery is stopped the server READs Update Result to know the result of the firmware update procedure.</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>Pass-Criteria</strong></td>
<td><ol style="list-style-type: upper-alpha">
<li><p>In test step 1, the Server receives the status code “2.05 “ (Content) for the READ success command, along with the State Resource value of “0” (Idle)</p></li>
<li><p>In test step 2., the Server receives the status code “2.04” (Changed) for the WRITE command setting either the Package URI Resource or setting the Package Resource, according to the chosen firmware delivery method.</p></li>
<li><p>In test step 3., the State Resource value set to “1” retrieved from successive Server READs or Client NOTIFY messages, indicates the Package Delivery process is maintained in Downloading stage</p></li>
<li><p>In test step 3., the Update Result Resource (/5/0/5) retrieved from successive Server READs or Client NOTIFY messages will take the value “5” indicating an error occurred during the downloading process related to the failure of the firmware package integrity check</p></li>
<li><p>In test step 4., the success READ message(s) (status code “2.05” Content) on State Resource with value “0” (Idle) and Update Result Resource with value “5” indicates the firmware Package Delivery aborted due to a Firmware Package Integrity failure.</p></li>
</ol></td>
</tr>
</tbody>
</table>

##### LightweightM2M-1.0-int-777 – Error Case 6: unsupported package type

<table>
<thead>
<tr class="header">
<th>Test Case Id</th>
<th>LightweightM2M-1.0-int-777</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Test Object</strong></td>
<td>Client and Server</td>
</tr>
<tr class="even">
<td><strong>Test Case Description</strong></td>
<td>Try to perform a device firmware update remotely triggered by the LWM2M Server with an unsupported package type</td>
</tr>
<tr class="odd">
<td><strong>Preconditions</strong></td>
<td><ul>
<li><p>The Client supports the Configuration C.8 as defined in Annex C</p></li>
<li><p>Prepare a firmware package containing a package type not supported by the Client</p></li>
<li><p>Device is switched on and operational</p></li>
<li><p>Client is registered at the LwM2M server</p></li>
<li><p>Firmware Update is available on the Server</p></li>
<li><p>The State Resource (/5/0/3) of the FW Object Instance is set to “0” (Idle)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Test Procedure</strong></td>
<td><p>A Package delivery initiated by a Server in using either PULL or PUSH delivery methods is received by the Client. The package type is not supported by the Client.<br />
Normal flow:</p>
<ol style="list-style-type: decimal">
<li><p>The Server verifies through a READ (CoAP GET) command on /5/0/3 (State) the FW Update Object Instance of the Client is in Idle State</p></li>
<li><p>The Server delivers the firmware package to the Client either through a WRITE (CoAP PUT) operation in the Package Resource (/5/0/0 ) or through a WRITE operation of an URI in the Package URI Resource.</p></li>
<li><p>The Server sends repeated READs or OBSERVE on State and Update Result Resources (CoAP GET /5/0) of the FW Update Object Instance to determine when the download is completed or if an error occured. The Download cannot be finished since the firmware package type is not supported by the Client</p></li>
<li><p>When the Package delivery is stopped the server READs Update Result to know the result of the firmware update procedure.</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>Pass-Criteria</strong></td>
<td><ol style="list-style-type: upper-alpha">
<li><p>In test step 1, the Server receives the status code “2.05 “ (Content) for the READ success command, along with the State Resource value of “0” (Idle)</p></li>
<li><p>In test step 2., the Server receives the status code “2.04” (Changed) for the WRITE command setting either the Package URI Resource or setting the Package Resource, according to the chosen firmware delivery method.</p></li>
<li><p>In test step 3., the State Resource value set to “1” retrieved from successive Server READs or Client NOTIFY messages, indicates the Package Delivery process is in Downloading stage</p></li>
<li><p>In test step 3., the Update Result Resource (/5/0/5) retrieved from successive Server READs or Client NOTIFY messages will take the value “6” indicating an error occurred during the downloading process related to the firmware package type not supported by the Client.</p></li>
<li><p>In test step 4., the success READ message(s) (status code “2.05” Content) on State Resource with value “1” (Downloading) and Update Result Resource with value “6 indicates the firmware Package Delivery aborted due to a firmware package type not supported by the Client.</p></li>
</ol></td>
</tr>
</tbody>
</table>

##### LightweightM2M-1.0-int-778 – Error Case 7: invalid URI (package URI)

<table>
<thead>
<tr class="header">
<th>Test Case Id</th>
<th>LightweightM2M-1.0-int-778</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Test Object</strong></td>
<td>Client and Server</td>
</tr>
<tr class="even">
<td><strong>Test Case Description</strong></td>
<td>Try to perform a device firmware update remotely triggered by the LWM2M server with an invalid URI</td>
</tr>
<tr class="odd">
<td><strong>Preconditions</strong></td>
<td><ul>
<li><blockquote>
<p>The Client supports the Configuration C.8 as defined in Annex C</p>
</blockquote></li>
<li><blockquote>
<p>According to Test LightweightM2M-1.0-int-751, the FW Update Object Instance supports the PULL Update Delivery Method</p>
</blockquote></li>
<li><blockquote>
<p>Prepare an invalid URI from which the Client will try to fetch a firmware package.</p>
</blockquote></li>
<li><blockquote>
<p>Device is switched on and operational</p>
</blockquote></li>
<li><blockquote>
<p>Client is registered with the LwM2M server</p>
</blockquote></li>
<li><blockquote>
<p>Firmware Update is available on the ServerThe State Resource (/5/0/3) of the FW Object Instance is set to “0” (Idle)</p>
</blockquote></li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Test Procedure</strong></td>
<td><p>A Package delivery initiated by a Server in using the PULL delivery methods is received by the Client. The URI provided is a fake one.<br />
Normal flow:</p>
<ol style="list-style-type: decimal">
<li><p>The Server verifies through a READ (CoAP GET) command on /5/0/3 (State) the FW Update Object Instance of the Client is in Idle State</p></li>
<li><p>The Server initiates a firmware package delivery to the Client through a WRITE operation of an invalid URI in the Package URI Resource.</p></li>
<li><p>The Server sends repeated READs or OBSERVE on State and Update Result Resources (CoAP GET /5/0) of the FW Update Object Instance to determine when the download is completed or if an error occured. The download process is stopped by the Client due to the usage of a bad URI.</p></li>
<li><p>When the Package delivery is stopped the server READs Update Result to know the result of the firmware update procedure.</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>Pass-Criteria</strong></td>
<td><ol style="list-style-type: upper-alpha">
<li><p>In test step 1, the Server receives the status code “2.05 “ (Content) for the READ success command, along with the State Resource value of “0” (Idle)</p></li>
<li><p>In test step 2., the Server receives the status code “2.04” (Changed) for the WRITE command setting the Package URI Resource</p></li>
<li><p>In test step 3., the State Resource value set to “1” retrieved from successive Server READs or Client NOTIFY messages, indicates the Package Delivery process is maintained in Downloading stage</p></li>
<li><p>In test step 3., the Update Result Resource (/5/0/5) retrieved from successive Server READs or Client NOTIFY messages will take the value “7” indicating an error occurred during the downloading process related to the usage of a bad URI</p></li>
<li><p>In test step 4., the success READ message(s) (status code “2.05” Content) on State Resource with value “0” (Idle) and Update Result Resource with value “7” indicates the firmware Package Delivery aborted due to the connection to an Invalid URI for the firmware package delivery.</p></li>
</ol></td>
</tr>
</tbody>
</table>

##### LightweightM2M-1.0-int-779 – Error Case 8: Unsuccessful Firmware Update

<table>
<thead>
<tr class="header">
<th>Test Case Id</th>
<th>LightweightM2M-1.0-int-779</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Test Object</strong></td>
<td>Client and Server</td>
</tr>
<tr class="even">
<td><strong>Test Case Description</strong></td>
<td>Perform a device firmware update remotely triggered by the LWM2M server in using Package Resource (CoAP mechanisms) or but with installation failure</td>
</tr>
<tr class="odd">
<td><strong>Preconditions</strong></td>
<td><ul>
<li><blockquote>
<p>The Client supports the Configuration C.8 as defined in Annex C</p>
</blockquote></li>
<li><blockquote>
<p>Prepare a firmware package which can be downloaded but cannot be successfully installed.</p>
</blockquote></li>
<li><blockquote>
<p>Device is switched on and operational</p>
</blockquote></li>
<li><blockquote>
<p>Client is registered with the LwM2M Server</p>
</blockquote></li>
<li><blockquote>
<p>Firmware Update is available on the Server</p>
</blockquote></li>
<li><blockquote>
<p>The State Resource (/5/0/3) of the FW Object Instance is set to “0” (Idle)</p>
</blockquote></li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Test Procedure</strong></td>
<td><p>A Package delivery initiated by a Server in using either PULL or PUSH delivery methods is received by the Client. But its installation will fail.<br />
Normal flow:</p>
<ol style="list-style-type: decimal">
<li><blockquote>
<p><strong>Step 1 – Package Delivery</strong></p>
</blockquote></li>
</ol>
<ol style="list-style-type: lower-alpha">
<li><p>The Server verifies through a READ (CoAP GET) command on /5/0/3 (State) the FW Update Object Instance of the Client is in Idle State</p></li>
<li><p>The Server retrieves (CoAP GET) the initial value of the Firmware Version Resource from the Object Device Instance for verification in the Pass Criteria (C)</p></li>
<li><p>The Server delivers the firmware package to the Client either through a WRITE (CoAP PUT) operation in the Package Resource (/5/0/0 ) or through a WRITE operation of an URI in the Package URI Resource.</p></li>
<li><p>Polling ( successive READ commands) or Notification on Update Result and State Resources is performed, up to the time State Resource takes the ‘Downloaded’ value (2)</p></li>
</ol>
<ol style="list-style-type: decimal">
<li><blockquote>
<p><strong>Step 2 – Installation Failure</strong></p>
</blockquote></li>
</ol>
<ol style="list-style-type: lower-alpha">
<li><p>When the download is completed (State Resource value is ‘2’ Downloaded) , the Server initiates a firmware update by triggering EXECUTE command on Update Resource (CoAP POST /5/0/2 )</p></li>
<li><p>Polling (READ command) or Notification on Update Result and State Resources is performed, up to the time State Resource is turned back to 2 (Downloaded) or the Update Result Resource contains the value “8” (Firmware update failed )</p></li>
</ol>
<ol style="list-style-type: decimal">
<li><blockquote>
<p><strong>Step 3 – Process Verification </strong></p>
</blockquote></li>
</ol>
<ol style="list-style-type: lower-alpha">
<li><blockquote>
<p>The server READs Update Result &amp; State Resources to know the result of the firmware update procedure.</p>
</blockquote></li>
<li><blockquote>
<p>The Server READs the Firmware Version Resource from the Object Device Instance</p>
</blockquote></li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>Pass-Criteria</strong></td>
<td><ol style="list-style-type: upper-alpha">
<li><blockquote>
<p><strong>Package Delivery </strong></p>
</blockquote></li>
</ol>
<ol style="list-style-type: lower-alpha">
<li><p>In test step 1.a, the Server receives the status code “2.05 “ (Content) for the READ success command, along with the State Resource value of “0” (Idle)</p></li>
<li><p>In test step 1.b, the Server receives the status code “2.05 “ (Content) for the READ success command, along with the initial value of the Firmware version Resource available from the Object Device Instance.</p></li>
<li><p>In test step 1.c, the Server receives the status code “2.04” (Changed) for the WRITE command setting either the Package URI Resource or setting the Package Resource, according to the chosen firmware delivery method.</p></li>
<li><p>In at this end of test step 1.d, the State Resource take the value “2” (Downloaded)</p></li>
</ol>
<ol style="list-style-type: upper-alpha">
<li><blockquote>
<p><strong>Installation failure </strong></p>
</blockquote></li>
</ol>
<ol style="list-style-type: lower-alpha">
<li><blockquote>
<p>In test step 2.a, the Server receives a success message “2.04” (Changed) in response to the EXECUTE command</p>
</blockquote></li>
<li><blockquote>
<p>In test step 2.b, the Server receives success message(s) “2.05” Contents along with a State Resource value of “3” (Updating) or “2” (Downloaded) and an Update Ressource value of “0” (Initial Value) and “8” at the end (Firmware updated failure)</p>
</blockquote></li>
</ol>
<ol style="list-style-type: upper-alpha">
<li><p><strong>Process Verification</strong></p></li>
</ol>
<ol style="list-style-type: lower-alpha">
<li><blockquote>
<p>In test step 3.a, the Server receives success message(s) “2.05” Content” along with a State Resource value of “2” (Downloaded) and an Update Ressource value of “8” (Firmware updated failed)</p>
</blockquote></li>
<li><blockquote>
<p>In test step 3.b the Server receives success message(s) “2.05” Content” along with a Firmware Version Resource value form the Object Device Instance which has not changed compared to the one retrieved in Pass Criteria A.b</p>
</blockquote></li>
</ol></td>
</tr>
</tbody>
</table>

##### LightweightM2M-1.0-int-780 – Error Case 9: Unsupported protocol

##### 

1.  #### LwM2M Location Object (ID:6) \[800-849\]

    1.  ##### LightweightM2M-1.0-int-801 – Querying the readable resources of object

| Test Case Id              | LightweightM2M-1.0-int-801                                                                                                                                                                                                            |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                     |
| **Test Case Description** | Querying the readable resources of Object Location ID:6 Instance and verifying the received values are as expected and coherent.                                                                                                      |
| **Preconditions**         | -   The Client supports the Configuration C.7 as defined in Annex C                                                                                                                                                                   
                                                                                                                                                                                                                                         
  -   Client is registered with the Server                                                                                                                                                                                               |
| **Test Procedure**        | A READ operation from Server on the Location Object Instance has been received by the Client.                                                                                                                                         
                                                                                                                                                                                                                                         
  Normal flow:                                                                                                                                                                                                                           
                                                                                                                                                                                                                                         
  1.  READ (CoAP GET) is performed by the Server on the Location Object Instance of the Client                                                                                                                                           |
| **Pass-Criteria**         | 1.  In test step 1., the Client receives a READ (CoAP GET) command from the Server on the Location Object Instance                                                                                                                    
                                                                                                                                                                                                                                         
  2.  In test step 1., the Server receives the status code “2.05” for READ message success                                                                                                                                               
                                                                                                                                                                                                                                         
  3.  In test step 1., along with the success message, the mandatory Resources (Latitude, Longitude, Timestamp) and optional ones, are received by the Server with expected values in compliance with LwM2M technical specification 1.0  |

1.  ##### LightweightM2M-1.0-int-805 – Setting the writable resources

    There are no writable resources for this object.

2.  ##### LightweightM2M-1.0-int-810 – Basic Observation and notification on Location Object Instance

| Test Case Id              | LightweightM2M-1.0-int-810                                                                                                                                                                                                                 |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                          |
| **Test Case Description** | Sending the observation policy to the device for resources of Object Location ID:6                                                                                                                                                         |
| **Preconditions**         | -   The Client supports the Configuration C.7 as defined in Annex C                                                                                                                                                                        
                                                                                                                                                                                                                                              
  <!-- -->                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                              
  -   Device is switched on and operational                                                                                                                                                                                                   
                                                                                                                                                                                                                                              
      -   Client is registeredwith the LWM2M server                                                                                                                                                                                           |
| **Test Procedure**        | The Server establishes an Observation relationship with the Client to acquire condition notifications about the Location Object Instance observable resources.                                                                             
                                                                                                                                                                                                                                              
  Normal flow:                                                                                                                                                                                                                                
                                                                                                                                                                                                                                              
  1.  The Server communicates to the Client pmin=2 pmax=10 period threshold values with a WRITE ATTRIBUTE (CoAP PUT) operation at the Location Object Instance level                                                                          
                                                                                                                                                                                                                                              
  2.  The Server sends OBSERVE (CoAP Observe Option) message to activate reporting on the Location Object Instance.                                                                                                                           
                                                                                                                                                                                                                                              
  3.  The Client reports requested information with a NOTIFY message (CoAP response)                                                                                                                                                          |
| **Pass-Criteria**         | 1.  In test step 1., the Server received a WRITE ATTRIBUTE command (CoAP PUT) targeting the Location Object Instance with the proper pmin=2 and pmin=10 parameters.                                                                        
                                                                                                                                                                                                                                              
  2.  In test step 1., the Server received the success message (2.04 Changed) in response to the WRITE ATTRIBUTE command                                                                                                                      
                                                                                                                                                                                                                                              
  3.  In test step 2., the Client received the OBSERVE operation targeting the Location Object Instance                                                                                                                                       
                                                                                                                                                                                                                                              
  4.  In test step 2., in response to its OBSERVE operation, the Server receives the success message (Content 2.05) along with the initial values of the Location Object Instance                                                             
                                                                                                                                                                                                                                              
  5.  In test step 3., based on pmin/pmax periods parameters received in test step 1., the Client reports information to the Server with NOTIFY messages containing the Location Object Instance updated values.                              
                                                                                                                                                                                                                                              
  6.  In test step 3., the values received by the Server along with the success message (Content 2.05) must be as expected : at less the Mandatory Timestamp Resource must have admissible values according to the pmin and pmax parameters.  |

##### LightweightM2M-1.0-int-811 – Extended Observation and notification of Location Object Instance

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-820 – Create Multiple Resource Instances 

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-830 – Create Object Instance

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-835 – Delete Object Instance

*&lt;Test Cases to fill-up&gt;*

1.  #### Connectivity Statistics (ID 7) \[900-949\]

    1.  ##### LightweightM2M-1.0-int-901 – Querying a Data Collection from Connectivity Object Instance

| Test Case Id              | LightweightM2M-1.0-int-901                                                                                                                                                                                                                                                                 |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                                                                          |
| **Test Case Description** | Starting and stopping after few seconds a data collection, then querying the readable resources of Connectivity Statistics Object ID:7 Instance and verifying the received values are as expected and coherent                                                                             |
| **Preconditions**         | -   The Client supports the Configuration C.9 as defined in Annex C                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                              
  -   Client is registered with the Server                                                                                                                                                                                                                                                    |
| **Test Procedure**        | A READ operation from Server on the Connectivity Object Instance has been received by the Client after the data collection has been triggered then stopped after few seconds.                                                                                                              
                                                                                                                                                                                                                                                                                              
  Normal flow:                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                              
  1.  EXECUTE operation (CoAP POST) is performed on the Start Resource of the Connectivity Statistics Object Instance                                                                                                                                                                         
                                                                                                                                                                                                                                                                                              
  2.  After few seconds, an EXECUTE operation (CoAP POST) is performed on the Stop Ressource of the Connectivity Statistics Object Instance                                                                                                                                                   
                                                                                                                                                                                                                                                                                              
  3.  A READ (CoAP GET) operation is performed by the Server on the Connectivity Object Instance of the Client                                                                                                                                                                                |
| **Pass-Criteria**         | 1.  In test step 1., the Client receives a Start command for the Connectivity Statistics Object Instance (CoAP POST)                                                                                                                                                                       
                                                                                                                                                                                                                                                                                              
  2.  In test step 1., the Server receives the success message (“2.4” Changed) in response of its EXECUTE command on the Client                                                                                                                                                               
                                                                                                                                                                                                                                                                                              
  3.  In test step2., the Client receives a Stop command for the Connectivity Statistics Object Instance (CoAP POST)                                                                                                                                                                          
                                                                                                                                                                                                                                                                                              
  4.  In test step 2., the Server receives the success message (“2.4” Changed) in response of its EXECUTE command on the Client                                                                                                                                                               
                                                                                                                                                                                                                                                                                              
  5.  In test step 3., the Client receives a READ operation on the Connectivity Object Instance                                                                                                                                                                                               
                                                                                                                                                                                                                                                                                              
  6.  In test step 3., the Server receives the status code “2.05” for the READ message success                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                              
  7.  In test step 3., along with the success message, the Server receives the Connectivity Statistics Object Instance value according to the Client preferred data format.                                                                                                                   
                                                                                                                                                                                                                                                                                              
  8.  In test step 3, the received Connectivity Statistics Object Instance contains expected values in compliance with the LwM2M technical specification 1.0, for the mandatory Resources (Network Bearer, Available Network Bearer, Radio Signal Bearer, IP Address), and the optional ones  |

##### LightweightM2M-1.0-int-905 – Setting the writable resources

| Test Case Id              | LightweightM2M-1.0-int-905                                                                                                                                                                                                                                                |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                                                         |
| **Test Case Description** | Query the readable Resources of the Connectivity Statistics Object ID:7 Instance, before setting the Collection Period to another value than the initial value one. Then query the readable Resources again and verify the Collection Period contains the expected value. |
| **Preconditions**         | -   The Client supports the Configuration C.9 as defined in Annex C                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                             
  -   Client is registered with the Server                                                                                                                                                                                                                                   |
| **Test Procedure**        | A WRITE operation is received by the Client for setting the Collection Period Resource of the Connectivity Statistics Object Instance. This WRITE operation is framed by 2 READ operations on the same Object Instance.                                                   
                                                                                                                                                                                                                                                                             
  Normal flow:                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                             
  1.  A READ (CoAP GET) operation is performed by the Server on the Connectivity Object Instance of the Client                                                                                                                                                               
                                                                                                                                                                                                                                                                             
  2.  A WRITE (CoAP PUT) operation is performed on the Client targeting the Collection Period Resource (ID:8) of the Connectivity Object Instance with a value different of the one collected in step 2.                                                                     
                                                                                                                                                                                                                                                                             
  3.  A new READ (CoAP GET) operation is performed by the Server on the Connectivity Object Instance of the Client                                                                                                                                                           |
| **Pass-Criteria**         | 1.  In test step 1., the Client receives a READ operation on the Connectivity Object Instance                                                                                                                                                                             
                                                                                                                                                                                                                                                                             
  2.  In test step 1., the Server receives the status code “2.05” for the READ success message along with the Connectivity Statistics Object Instance value according to the Client preferred data format.                                                                   
                                                                                                                                                                                                                                                                             
  3.  In step 2, the Client receives a WRITE command (CoAP PUT) targeting the Collection Period of the Connectivity Statistics Object Instance with a value different of the one collected in pass B.                                                                        
                                                                                                                                                                                                                                                                             
  4.  In test step 2, the Server received receives a success message (2.04 Changed) related to its WRITE operation                                                                                                                                                           
                                                                                                                                                                                                                                                                             
  5.  In test step 3., the Client receives a new READ operation on the Connectivity Object Instance                                                                                                                                                                          
                                                                                                                                                                                                                                                                             
  6.  In step 3, the Server receives success message (2.05 Content) and the requested value in the LwM2M Client preferred data format                                                                                                                                        
                                                                                                                                                                                                                                                                             
  7.  The value of the Collection Period Resource value collected in Pass F, correspond to the value which was set in step 2                                                                                                                                                 |

##### LightweightM2M-1.0-int-910 – Basic Observation and notification on Connectivity Monitoring Object Instance

| Test Case Id              | LightweightM2M-1.0-int-910                                                                                                                                                                                          |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                   |
| **Test Case Description** | Sending the observation policy to the device for resources of Connectivity Object ID:7 Instance                                                                                                                     |
| **Preconditions**         | -   The Client supports the Configuration C.9 as defined in Annex C                                                                                                                                                 
                                                                                                                                                                                                                       
  -   Device is switched on and operational                                                                                                                                                                            
                                                                                                                                                                                                                       
  -   Client is registered with the LwM2M server                                                                                                                                                                       |
| **Test Procedure**        | The Server establishes an Observation relationship with the Client to acquire condition notifications about the Connectivity Statistics Instance.                                                                   
                                                                                                                                                                                                                       
  Normal flow:                                                                                                                                                                                                         
                                                                                                                                                                                                                       
  1.  The Server communicates to the Client pmin=2 & pmax=10 periods with a WRITE ATTRIBUTE (CoAP PUT) operation at the Connectivity Statistics Instance level.                                                        
                                                                                                                                                                                                                       
  2.  The Server set (CoAP PUT) the Collection Period Resource to 0 in the Connectivity Statistics Object Instance.                                                                                                    
                                                                                                                                                                                                                       
  3.  The Server sends OBSERVE (CoAP Observe Option) message to activate reporting on the Connectivity Statistics Instance.                                                                                            
                                                                                                                                                                                                                       
  4.  The Server starts the data collection on the Connectivity Staistics Object Instance by triggering the Start Resource of this Object Instance (CoAP POST)                                                         
                                                                                                                                                                                                                       
  5.  The Client reports requested information with NOTIFY messages (CoAP response)                                                                                                                                    
                                                                                                                                                                                                                       
  6.  Several NOTIFY messages are received by the Server related to the Connectivity Statistics Object Instance                                                                                                        
                                                                                                                                                                                                                       
  7.  The Server stops the data collection on the Connectivity Staistics Object Instance by triggering the Stop Resource of this Object Instance (CoAP POST)                                                           
                                                                                                                                                                                                                       
  8.  The Server stops the OBSERVATION process                                                                                                                                                                         |
| **Pass-Criteria**         | 1.  In test step 1., the Server received a WRITE ATTRIBUTE command (CoAP PUT) targeting the Connectivity Statistics Object Instance with the proper pmin=2 and pmin=10 parameters.                                  
                                                                                                                                                                                                                       
  2.  In test step 1., the Server received the success message (2.04 Changed) in response to the WRITE ATTRIBUTE command                                                                                               
                                                                                                                                                                                                                       
  3.  In test step 2 the Client received the OBSERVE operation targeting the Connectivity Statistics Object Instance                                                                                                   
                                                                                                                                                                                                                       
  4.  In test step2, in response to its OBSERVE operation, the Server receives the success message (Content 2.05) along with the initial values of the Connectivity Statistics Object Instance                         
                                                                                                                                                                                                                       
  5.  In test step 3, based on pmin/pmax periods parameters received in test step 1., the Client reports information to the Server with NOTIFY messages containing the updated values of the Connectivity Statistics.  
                                                                                                                                                                                                                       
  6.  In test step 3., the values returned by the Server along with the success message (Content 2.05) must be as expected.                                                                                            |

##### LightweightM2M-1.0-int-911 – Extended Observation and notification of Connectivity Statistics Object Instance

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-920 – Create Multiple Resource Instances 

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-930 – Create Object Instance

*&lt;Test Cases to fill-up&gt;*

##### LightweightM2M-1.0-int-935 – Delete Object Instance

*&lt;Test Cases to fill-up&gt;*

Multi-Servers Context \[950-999\]
---------------------------------

### LightweightM2M-1.0-int-950 – Multi-Servers Registration

|                           |                                                                                                                                                                       |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-950                                                                                                                                            |
| **Test Object**           | Client and Server                                                                                                                                                     |
| **Test Case Description** | Test the Client capability to register 2 and connect 2 different Servers                                                                                              |
| **Tool**                  | n/a                                                                                                                                                                   |
| **Test code**             | n/a                                                                                                                                                                   |
| **Preconditions**         | -   The Client supports the minimum Configuration C.14 as defined in Annex and containing 2 (Registred-)Server accounts                                               
                                                                                                                                                                         
  -   Device is turned-on                                                                                                                                                
                                                                                                                                                                         
  -   The Boostrap Information is available in the Client with 2 Server-Accounts to which the Client is likely to register, and support of the Access Control Object)    |
| **Test Procedure**        | The Client automatically registers with 2 Servers in using the 2 Server Accounts available in the bootstrapped configuration                                          
                                                                                                                                                                         
  Normal flow:                                                                                                                                                           
                                                                                                                                                                         
  1.  Registration message (CoAP POST) is sent from the Client to Server \#1                                                                                             
                                                                                                                                                                         
  2.  Registration message (CoAP POST) is sent from the Client to Server \#2                                                                                             |
| **Pass-Criteria**         | 1.  In test step 1., the Server receives the REGISTER command along with the information related to the Server Account \#1 (see LwM2M-1.0-int-101 Test Case for more) 
                                                                                                                                                                         
  2.  In test step 1., the Client receives the “Success” message from Server \#1 (2.01 Created)                                                                          
                                                                                                                                                                         
  3.  In test step 2., the Server receives the REGISTER command along with the information related to the Server Account \#2 (see LwM2M-1.0-int-101 Test Case for more)  
                                                                                                                                                                         
  4.  In test step 2., the Client receives the “Success” message from Server \#2 (2.01 Created)                                                                          |

### LightweightM2M-1.0-int-951 – Multi-Servers & Attributes

|                           |                                                                                                                                                                                                                                 |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-1.0-int-951                                                                                                                                                                                                      |
| **Test Object**           | Client and Server                                                                                                                                                                                                               |
| **Test Case Description** | Test the Client capability to identify and to report information according to a specific Server context                                                                                                                         |
| **Tool**                  | n/a                                                                                                                                                                                                                             |
| **Test code**             | n/a                                                                                                                                                                                                                             |
| **Preconditions**         | -   The Client supports the minimum Configuration C.14 as defined in Annex and containing 2 (Registred-)Server accounts as well as simple Access Contol Structure                                                               
                                                                                                                                                                                                                                   
  -   Device is turned-on                                                                                                                                                                                                          
                                                                                                                                                                                                                                   
  -   The Boostrap Information is available in the Client with 2 Server-Accounts to which the Client is likely to register                                                                                                         
                                                                                                                                                                                                                                   
  -   The Client pass the test case LightweightM2M-1.0-int-950 and is connected to Server\#1 et Server\#2                                                                                                                          |
| **Test Procedure**        | Server \#1 & Server\#2 set different Observation period values for the Device Object Instance; A check is performed to verify the effective setting                                                                             
                                                                                                                                                                                                                                   
  Normal flow:                                                                                                                                                                                                                     
                                                                                                                                                                                                                                   
  1.  The Server \#1 communicates to the Client pmin=2 and pmax=10 periods with a WRITE-ATTRIBUTE (CoAP PUT) operation at the Device Object Instance level.                                                                        
                                                                                                                                                                                                                                   
  2.  The Server \#2 communicates to the Client pmin=15 and pmax=50 periods with a WRITE-ATTRIBUTE (CoAP PUT) operation at the Device Object Instance level.                                                                       
                                                                                                                                                                                                                                   
  3.  The Server \#1 sends a DISCOVER command to the Client                                                                                                                                                                        
                                                                                                                                                                                                                                   
  4.  The Server \#2 send a DISCOVER command to the Client                                                                                                                                                                         |
| **Pass-Criteria**         | 1.  In test step 1., the Server\#1 receives the “Success” message from the Client (2.04 Changed)                                                                                                                                
                                                                                                                                                                                                                                   
  2.  In test step 2., the Server\#2 receives the “Success” message from the Client (2.04 Changed)                                                                                                                                 
                                                                                                                                                                                                                                   
  3.  In test step 3., the Server\#1 receives the “Success” message from Client (2.05 Content) related to its DISCOVER command along with the payload containing the following information regarding the Device Object Instance :  
                                                                                                                                                                                                                                   
  > &lt;/3/0&gt;;pmin=2;pmax=10,&lt;/3/0/0&gt;,&lt;/3/0/1&gt;,&lt;/3/0/2&gt;,&lt;/3/0/3&gt;,&lt;/3/0/11&gt;,&lt;/3/0/16&gt;                                                                                                        
                                                                                                                                                                                                                                   
  1.  In test step 4., the Server\#2 receives the “Success” message from Client (2.05 Content) related to the DISCOVER command along with the payload containing the following information regarding the Device Object Instance :  
                                                                                                                                                                                                                                   
  > &lt;/3/0&gt;;pmin=15;pmax=50,&lt;/3/0/0&gt;,&lt;/3/0/1&gt;,&lt;/3/0/2&gt;,&lt;/3/0/3&gt;,&lt;/3/0/11&gt;,&lt;/3/0/16&gt;                                                                                                       |

1.  LwM2M Additional Objects Test cases \[1000-1999\]
    -------------------------------------------------

    1.  ### Lock and Wipe Object (ID 8) \[1000-1099\]

&lt;Test Cases to fill-up&gt;

### Software Management Object (ID 9) \[1100-1199\]

&lt;Test Cases to fill-up&gt;

1.  ### 

2.  ### Connectivity Management Objects (ID 10, 11, 12, 13) \[1200-1499\]

    1.  #### Cellular Network Connectivity ID:10 \[1200-1249\]

##### LightweightM2M-1.0-int-1200 – Querying the readable resources of Object ID:10

| Test Case Id              | LightweightM2M-1.0-int-1200                                                                                                                                                         |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                   |
| **Test Case Description** | Querying the readable resources of Cellular network connectivity object ID:10 and verifying the received values are as expected and coherent regarding the Configuration C.10       |
| **Preconditions**         | -   The Client supports the Configuration C.10 as defined in Annex C                                                                                                                
                                                                                                                                                                                       
  -   The Client is registered with the Server                                                                                                                                         |
| **Test Procedure**        | A READ operation from Server on the Cellular Network Connectivity Object Instance requesting TLV format is sent to the Client.                                                      
                                                                                                                                                                                       
  Normal flow:                                                                                                                                                                         
                                                                                                                                                                                       
  1.  READ (CoAP GET /10/0) operation on the Instance of the Object ID:10 is received by the Client and its answer is sent back to the Server                                          |
| **Pass-Criteria**         | 1.  In test step 1 :the Server receives the success message (2.05 Content) associated to its READ request                                                                           
                                                                                                                                                                                       
  2.  In step 1: the values returned by the Client in TLV format is consistent with the Configuration C 10. used for that test (Activated Profine Names, Serving PLMN rate Control…).  |

##### LightweightM2M-1.0-int-1201 – Querying the readable resources of Object ID:10 in version 1.1

| Test Case Id              | LightweightM2M-1.0-int-1201                                                                                                                                                                                                                |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                          |
| **Test Case Description** | Querying the readable resources of Cellular network connectivity object ID:10 version 1.1 and verifying the received values are as expected and coherent regarding the Configuration C.11                                                  |
| **Preconditions**         | -   The Client supports the Configuration C.11 as defined in Annex C                                                                                                                                                                       
                                                                                                                                                                                                                                              
  -   The Client is registered with the Server in indicating the Object ID:10 is in version 1.1                                                                                                                                               |
| **Test Procedure**        | A DISCOVER operation is requested by the Server to verify the Object ID:10 is in version 1.1.                                                                                                                                              
                                                                                                                                                                                                                                              
  A READ operation from Server on the Cellular Network Connectivity Object Instance requesting TLV format is sent to the Client.                                                                                                              
                                                                                                                                                                                                                                              
  Normal flow:                                                                                                                                                                                                                                
                                                                                                                                                                                                                                              
  1.  DISCOVER (CoAP GET Accept:40) operation is performed by the Server on Object ID:10                                                                                                                                                      
                                                                                                                                                                                                                                              
  2.  READ (CoAP GET /10/0) operation on the Instance of the Object ID:10 is received by the Client and its answer is sent back to the Server                                                                                                 |
| **Pass-Criteria**         | 1.  In test step 1, the Server – along with the success message 2.05 – received the information related to Object ID:10 including                                                                                                          
                                                                                                                                                                                                                                              
  ***&lt;/10&gt;;ver=”1.1”,&lt;/10/0/6&gt;,&lt;/10/0/11&gt;, &lt;/10/0/13&gt;, &lt;/10/0/14&gt; ***                                                                                                                                           
                                                                                                                                                                                                                                              
  1.  In test step 2 :the Server receives the success message (2.05 Content) associated to its READ request on Object Instance /10/0                                                                                                          
                                                                                                                                                                                                                                              
  2.  In test step 2: the values returned by the Client in TLV format is consistent with the Configuration C 10. used for that test (Activated Profine Names, Serving PLMN rate Control, Power Saving Modes, Active Power Sa&ving Modes...).  |

##### LightweightM2M-1.0-int-1210 – Setting the Power Saving Mode Resources of Object ID:10 (version 1.1 only)

| Test Case Id              | LightweightM2M-1.0-int-1210                                                                                                                                                                                                                                        |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                                                  |
| **Test Case Description** | Setting the writable Resources of Cellular network connectivity Object ID:10 in version 1.1                                                                                                                                                                        |
| **Preconditions**         | -   The Client supports the Configuration C.11 as defined in Annex C                                                                                                                                                                                               
                                                                                                                                                                                                                                                                      
  -   The Client is registered with the Server in indicating the Object ID:10 is in version 1.1                                                                                                                                                                       
                                                                                                                                                                                                                                                                      
  -   The Power Saving Modes of Device is not 0                                                                                                                                                                                                                       |
| **Test Procedure**        | A DISCOVER operation is requested by the Server to verify the Object ID:10 is in version 1.1.                                                                                                                                                                      
                                                                                                                                                                                                                                                                      
  A WRITE operation from Server on the Cellular Network Connectivity Object Instance requesting TLV format is sent to the Client to set the power saving mode. This test has to be run for the following resources:                                                   
                                                                                                                                                                                                                                                                      
  1.  Active Power Saving Modes                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                      
  Normal flow:                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                      
  1.  DISCOVER (CoAP GET Accept:40) operation is performed by the Server on Object ID:10                                                                                                                                                                              
                                                                                                                                                                                                                                                                      
  2.  A READ (CoAP GET /10/0/13) operation on the Instance 0 of the Object ID:10 is performed by the Server                                                                                                                                                           
                                                                                                                                                                                                                                                                      
  3.  A WRITE operation is performed by the Server on the “Active Power Saving Modes” Resource (CoAP PUT/POST 10/0/14) of the Object ID:10 Instance 0, in using the set of values contains in the 1210-SetOfValues sample below.The data format TLV is used. (11542)  
                                                                                                                                                                                                                                                                      
  4.  A READ (CoAP GET /10/0/14) operation is performed by the Server on the Instance 0 of the Object ID:10                                                                                                                                                           |
| **Pass-Criteria**         | 1.  In test step 1, the Server – along with the success message 2.05 – received the information related to Object ID:10 including                                                                                                                                  
                                                                                                                                                                                                                                                                      
  ***&lt;/10&gt;;ver=”1.1”,&lt;/10/0/6&gt;,&lt;/10/0/11&gt;, &lt;/10/0/13&gt;, &lt;/10/0/14&gt; ***                                                                                                                                                                   
                                                                                                                                                                                                                                                                      
  1.  In test step 2 : the Server receives the success message (2.05 Content) and the requested value of the “Power Saving Modes” Resource (/10/0/13). This value must mach the value present in the C.11 configuration.                                              
                                                                                                                                                                                                                                                                      
  2.  In step 3, the Server receives the success message (2.04 Changed) related to the WRITE command                                                                                                                                                                  
                                                                                                                                                                                                                                                                      
  3.  In test step 4 : the Server receives the success message (2.05 Content) associated to its READ request and the received value for the “Active Power Saving Modes” Resource“ must match the value contains in the 1210-SetOfValues sample.                       |

##### LightweightM2M-1.0-int-1230 – Observation and notification on Object ID:0 related to Power Saving Mode Resources (version 1.1 only)

| Test Case Id              | LightweightM2M-1.0-int-1230                                                                                                                                                                                                     |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                               |
| **Test Case Description** | Sending the observation policy to the device for resources of Cellular network connectivity Object ID:10 in version 1.1                                                                                                         |
| **Preconditions**         | -   The Client supports the Configuration C.11 as defined in Annex C                                                                                                                                                            
                                                                                                                                                                                                                                   
  -   The Client is registered with the Server in indicating the Object ID:10 is in version 1.1                                                                                                                                    |
| **Test Procedure**        | A DISCOVER operation is requested by the Server to verify the Object ID:10 is in version 1.1.                                                                                                                                   
                                                                                                                                                                                                                                   
  The Server establishes an Observation relationship with the Client to acquire conditional notifications about Resources from the Connectivity Mangement Object Instance:                                                         
                                                                                                                                                                                                                                   
  -   Power Saving Modes(ID:13)                                                                                                                                                                                                    
                                                                                                                                                                                                                                   
  -   Active Power Saving Modes (ID:14)                                                                                                                                                                                            
                                                                                                                                                                                                                                   
      Normal flow:                                                                                                                                                                                                                 
                                                                                                                                                                                                                                   
  1.  DISCOVER (CoAP GET Accept:40) operation is performed by the Server on Object ID:10                                                                                                                                           
                                                                                                                                                                                                                                   
  2.  Server communicates with the Object ID:10 in version 1.1 via WRITE-ATTRIBUTE (CoAP PUT) operations, to set the pmin & pmax Attributes of each targeted Resources (e.g. /10/0/13?pmin=5&pmax=15 and /10/0/14?pmin10&pmax=20)  
                                                                                                                                                                                                                                   
  3.  Server sends OBSERVE (CoAP GET operation with Observe Option set to 0) messages for the targeted Resources (ID:13 & ID:14 ) to activate reporting                                                                            
                                                                                                                                                                                                                                   
  4.  Client reports requested information with a NOTIFY message (CoAP responses)                                                                                                                                                  |
| **Pass-Criteria**         | 1.  In test step 1, the Server – along with the success message 2.05 – received the information related to Object ID:10 including                                                                                               
                                                                                                                                                                                                                                   
  ***&lt;/10&gt;;ver=”1.1”,&lt;/10/0/6&gt;,&lt;/10/0/11&gt;, &lt;/10/0/13&gt;, &lt;/10/0/14&gt; ***                                                                                                                                
                                                                                                                                                                                                                                   
  1.  In test step 2, the Server receives success messages (“2.04” Changed) related to the WRITE-ATTRIBUTES operations                                                                                                             
                                                                                                                                                                                                                                   
  2.  In test step 3, the Server receives success messages (“2.05” Content) along with the initial values of Resource ID:13 and ID:14                                                                                              
                                                                                                                                                                                                                                   
  3.  In test step 4, the Server regularly receives consistent information on the targeted Resources ID:13 & ID:14 of the Object ID:10 Instance 0.                                                                                 |

1.  #### APN connection profile ID:11 \[1250-1299\]

    1.  ##### LightweightM2M-CONMGMT-1.0-int-1250 – APN configuration 

|                           |                                                                                                                                                                                                                                                    |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-CONMGMT-1.0-int-1201                                                                                                                                                                                                                |
| **Test Object**           | Client and Server                                                                                                                                                                                                                                  |
| **Test Case Description** | Creating and enabling a new APN profile                                                                                                                                                                                                            |
| **Tool**                  | n/a                                                                                                                                                                                                                                                |
| **Test code**             | n/a                                                                                                                                                                                                                                                |
| **Preconditions**         | -   The Client supports the minimum Configuration C.10 as defined in Annex C                                                                                                                                                                       
                                                                                                                                                                                                                                                      
  -   Test 104 on registration Update Trigger successfully passed                                                                                                                                                                                     
                                                                                                                                                                                                                                                      
  -   Device is switched on and operational                                                                                                                                                                                                           
                                                                                                                                                                                                                                                      
  -   Client is registered at the LwM2M Server                                                                                                                                                                                                        
                                                                                                                                                                                                                                                      
  -   Cellular connectivity is established with the parameters given in the APN Connection Profile Object Instance (/11/0).                                                                                                                           |
| **Test Procedure**        | A new APN Object is created, then activated. The list of the Active APN Connection Profiles is requested by the Server to the Client                                                                                                               
                                                                                                                                                                                                                                                      
  Normal flow:                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                      
  1.  CREATE (COAP POST) operation is performed by the Server targeting APN Connection Profile Object (ID:11) to create a 2<sup>nd</sup> instance of the APN connection profile Object with a new APN which is not active yet.                        
                                                                                                                                                                                                                                                      
  2.  The Server triggers a Registration Update Trigger for forcing an UPDATE registration from the Client                                                                                                                                            
                                                                                                                                                                                                                                                      
  3.  UPDATE (registration) message (COAP POST) is sent from Client to Server including information about the supported Objects and Object Instances and namely the new Instance of the APN Connection Profile Object                                 
                                                                                                                                                                                                                                                      
  4.  Server activates the new APN Connection Profile in changing Enable status to True by WRITE operation (COAP PUT /11/1/3)                                                                                                                         
                                                                                                                                                                                                                                                      
  5.  Server reads the list of active APN Connection Profiles by performing a TLV READ targeting Resource ID:11 of Object 10 (/10/11)                                                                                                                 |
| **Pass-Criteria**         | 1.  In test step 1., The Server receives a Success message (“2.01” Created) associated to the Instantiation of the APN connection profile Object.                                                                                                  
                                                                                                                                                                                                                                                      
  2.  In test step 2., the Client receives a Registration Update Trigger request on Resource ID:7 of the Device Object Instance (ID:3)                                                                                                                
                                                                                                                                                                                                                                                      
  3.  In test step 2., the Server receives the Success message (“2.04” Changed) associated to the Update Registration Request                                                                                                                         
                                                                                                                                                                                                                                                      
  4.  In test step 3, the Server receives an UPDATE (registration) operation from the Client along with the updated list of Object/Object Instances in that Client. This list contains the new Instance of the APN connection profile Object (/11/1)  
                                                                                                                                                                                                                                                      
  5.  In test step 4, the Server receives the Success message associated with the Server WRITE operation for the new APN activation.                                                                                                                  
                                                                                                                                                                                                                                                      
  6.  In test step 5., the Server receives a Success message (“2.05” Content) along with the list of the active APN containing the new Created APN (11:1)                                                                                             
                                                                                                                                                                                                                                                      
  NOTE: In case the device only supports one active APN profile this test is passed when the new APN profile is activated.                                                                                                                            |

##### WLAN Connectivity ID:12 \[1300-1349\]

&lt;Test cases to fill-up&gt;

1.  ##### Bearer Selection ID:13 \[1350-1399\]

    1.  ###### LightweightM2M-CONMGMT-1.0-int-1350 – Bearer Selection

|                           |                                                                                                                                                                                                                                                                                                                                   |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Test Case Id              | LightweightM2M-CONMGMT-1.0-int-1350                                                                                                                                                                                                                                                                                               |
| **Test Object**           | Client and Server                                                                                                                                                                                                                                                                                                                 |
| **Test Case Description** | Controlling bearers using Bearer Selection Object                                                                                                                                                                                                                                                                                 |
| **Tool**                  | n/a                                                                                                                                                                                                                                                                                                                               |
| **Test code**             | n/a                                                                                                                                                                                                                                                                                                                               |
| **Preconditions**         | -   The Client supports the minimum Configuration C.10 as defined in Annex C                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                     
  -   Device is switched on and operational                                                                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                                                                                     
  -   Client is registered at the LwM2M server                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                     
  -   The Client supports a Cellular Network Connectivity Object Instance and one instance of an APN Connection Profile Object. Cellular connectivity is established with the parameters given in the APN Connection Profile Object Instance. Also, the Client supports the WLAN Connectivity Object but WLAN radio is not enabled.  |
| **Test Procedure**        | Normal flow:                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                     
  1.  CREATE (COAP POST) operation is performed by the server targeting 13 to create the instance of the Bearer selection object with Preferred Communication Bearer (13/0/0) as WLAN preferred.                                                                                                                                     
                                                                                                                                                                                                                                                                                                                                     
  2.  Server receives success message (2.01 Created)                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                                     
  3.  Client shall turn on the WLAN radio and use it for connectivity with the Server. Client shall send Update to the Server indicating the update in registration as the Client’s IP address (and port) has changed.                                                                                                               
                                                                                                                                                                                                                                                                                                                                     
  4.  Server checks the status of the WLAN connectivity object by performing a READ on /12/0. The interface shall be enabled and running. The Server shall verify the values of Enable and Status resources for the same.                                                                                                            
                                                                                                                                                                                                                                                                                                                                     
  5.  Server performs WRITE operation on Preferred Communication Bearer (13/0/0) resource and updates its value to 3GPP PS Preferred.                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                     
  6.  Client shall turn on the Cellular network connectivity (if not already enabled) and use it for connectivity with the Server. Client shall send Update to the Server indicating the update in registration as the Client’s IP address (and port) has changed.                                                                   
                                                                                                                                                                                                                                                                                                                                     
  7.  Server checks the status of the Cellular Network Connectivity object by performing a READ on /10. The interface shall be enabled and running.                                                                                                                                                                                  |
| **Pass-Criteria**         | 1.  Bearer Selection Object is allowing the Server to control Client interface for communication                                                                                                                                                                                                                                  |

### Device Capability Management Object (ID 15) \[1500-1599\]

&lt;Test Cases too fill-up&gt;

1.  ### Portfolio Object (ID 16) \[1600-1699\]

    1.  #### LightweightM2M-1.0-int-1600 – Querying the readable resources of object

*&lt;Test Cases to fill-up&gt;*

#### LightweightM2M-1.0-int-1605 – Setting the writable resources

*&lt;Test Cases to fill-up&gt;*

#### LightweightM2M-1.0-int-1610 – Basic Observation and notification of a Portfolio Object Instance

*&lt;Test Cases to fill-up&gt;*

#### LightweightM2M-1.0-int-1611 – Extended Observation and notification of a Portfolio Object Instance

*&lt;Test Cases to fill-up&gt;*

#### LightweightM2M-1.0-int-1620 – Create Multiple Resource Instances

*&lt;Test Cases to fill-up&gt;*

#### LightweightM2M-1.0-int-1630 – Create Portfolio Object Instance

| Test Case Id              | LightweightM2M-1.0-int-1630                                                                                                                                                                                                                                                     |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                                                               |
| **Test Case Description** | Creating a new Instance of the Portfolio Object                                                                                                                                                                                                                                 |
| **Preconditions**         | -   The Client supports the Configuration C.12 as defined in Annex C                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                   
  -   The Client is registered with the Server                                                                                                                                                                                                                                     |
| **Test Procedure**        | A DISCOVER operations is performed by the Server on the Portfolio Object to retrieve its initial characteristics. A Portfolio CREATE operation is performed to add a new Instance in the LwM2M Client. Additional DISCOVER and READ check the results of the various operations 
                                                                                                                                                                                                                                                                                   
  Normal flow:                                                                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                                                   
  1.  An initial DISCOVER (CoAP GET Accept:40) operation is performed on Portfolio Object ID:16                                                                                                                                                                                    
                                                                                                                                                                                                                                                                                   
  2.  A CREATE operation is performed with the Portfolio Object as target and the 1630-SetOfValues as payload in TLV format                                                                                                                                                        
                                                                                                                                                                                                                                                                                   
  3.  A new DISCOVER operation is performed on Portfolio Object ID:16                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                   
  4.  A READ request is performed by the Server on the Portfolio Object (CoAP GET /16).                                                                                                                                                                                            |
| **Pass-Criteria**         | 1.  In test step 1, the Success Message (“2.05” Content) is received by the Server along with the payload related to the DISCOVER request and containing :                                                                                                                      
                                                                                                                                                                                                                                                                                   
  > &lt;/16/0/0/&gt;;dim=4                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                   
  1.  In test step 2, a Success message is received by the Server (“2.01” Created) related to the CREATE operation along with the new created Instance ID (should be /16/1)                                                                                                        
                                                                                                                                                                                                                                                                                   
  2.  In test step 3, the Success message (“2.05” Content) is received by the Server along with the payload related to the DISCOVER request and containing :                                                                                                                       
                                                                                                                                                                                                                                                                                   
  > &lt;/16/0/0/&gt;;dim=4, &lt;/16/1/0/&gt;;dim=2                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                   
  1.  In test step 4., the Success message (“2.05” Content) is received by the Server along with a TLV payload related to the READ Request and containing 2 Instances of the Portfolio Object :                                                                                    
                                                                                                                                                                                                                                                                                   
  -   Instance 0 with Identity Resource (ID:0) composed of 4 Instances as defined in Configuration C.12                                                                                                                                                                            
                                                                                                                                                                                                                                                                                   
  -   Instance 1 with Identity Resource (ID:0) composed of 2 Instances as defined in 1630-SetOfValues below.                                                                                                                                                                       |

#### LightweightM2M-1.0-int-1635 – Delete Portfolio Object Instance

| Test Case Id              | LightweightM2M-1.0-int-1635                                                                                                                                                                                                                  |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test Object**           | Client and Server                                                                                                                                                                                                                            |
| **Test Case Description** | Deleting all Instances of the Portfolio Object                                                                                                                                                                                               |
| **Preconditions**         | -   The Client supports the Configuration C.12 as defined in Annex C                                                                                                                                                                         
                                                                                                                                                                                                                                                
  -   The Client is registered with the Server                                                                                                                                                                                                  |
| **Test Procedure**        | A DISCOVER operations is performed by the Server on the Portfolio Object to retrieve its initial characteristics. Portfolio DELETE operations are performed for removing all the Portfolio Object Instances implemented in the LwM2M Client. 
                                                                                                                                                                                                                                                
  Normal flow:                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                
  1.  An initial DISCOVER (CoAP GET Accept:40) operation is performed on Portfolio Object ID:16                                                                                                                                                 
                                                                                                                                                                                                                                                
  2.  DELETE operations are performed for each Instance of the Portfolio Object                                                                                                                                                                 
                                                                                                                                                                                                                                                
  3.  A new DISCOVER operation is performed on Portfolio Object ID:16                                                                                                                                                                           |
| **Pass-Criteria**         | 1.  In test step 1, the Success Message (“2.05” Content) is received by the Server along with the payload related to the DISCOVER request and containing at least:                                                                           
                                                                                                                                                                                                                                                
  > &lt; /16&gt;,&lt;/16/0/0/&gt;;dim=4                                                                                                                                                                                                         
                                                                                                                                                                                                                                                
  1.  In test step 2, successive Success messages are received by the Server (“2.04” Deleted) related to each DELETE operation targeting a Portfolio Object Instance                                                                            
                                                                                                                                                                                                                                                
  2.  In test step 3, the Success message (“2.05” Content) is received by the Server along with the payload related to the DISCOVER request and containing: &lt;/16&gt;                                                                         
                                                                                                                                                                                                                                                
  > (Object ID16 present but without any Instance implemented in the Client)                                                                                                                                                                    |

1.  <span id="_Toc427068889" class="anchor"><span id="_Toc427069030" class="anchor"><span id="_Toc427069271" class="anchor"><span id="_Toc427069031" class="anchor"><span id="_Toc491867278" class="anchor"></span></span></span></span></span>Change History (Informative)

2.  <span id="_Toc44724972" class="anchor"><span id="_Toc51147388" class="anchor"><span id="_Toc51149242" class="anchor"><span id="_Toc427069032" class="anchor"><span id="_Toc491867279" class="anchor"></span></span></span></span></span>Approved Version History

|           |      |                  |
|-----------|------|------------------|
| Reference | Date | Description      |
| n/a       | n/a  | No prior version |

1.  <span id="_Toc44724973" class="anchor"><span id="_Toc51147389" class="anchor"><span id="_Toc51149243" class="anchor"><span id="_Toc124672222" class="anchor"><span id="_Toc427069033" class="anchor"><span id="_Toc491867280" class="anchor"></span></span></span></span></span></span>Draft/Candidate Version 1.0/1.0.1 History

<table>
<tbody>
<tr class="odd">
<td>Document Identifier</td>
<td>Date</td>
<td>Sections</td>
<td>Description</td>
</tr>
<tr class="even">
<td><p>Draft Versions</p>
<p>OMA-ETS-LightweightM2M-V1_0</p></td>
<td>18 Jun 2013</td>
<td>All</td>
<td>First Draft as agreed in OMA-IOP-MEC-2013-0083-INP_ETS_for_LWM2M</td>
</tr>
<tr class="odd">
<td></td>
<td>17 Oct 2013</td>
<td>All</td>
<td><p>Cleaned up Version for the LWM2M Testfest in Las Vegas as agreed in</p>
<p>OMA-IOP-MEC-2013-0103-CR_Clean_up_of_LWM2M_ETS</p></td>
</tr>
<tr class="even">
<td></td>
<td>20 Dec 2013</td>
<td>1, 2.1, 3.3, 5, 6.1.3, 6.2, 6.3, 6.4, 6.5</td>
<td><p>Incorporated CR:</p>
<p>OMA-IOP-MEC-2013-0115-CR_LWM2M_ETS_Update</p>
<p>Editorial changes</p></td>
</tr>
<tr class="odd">
<td></td>
<td>19 Feb 2014</td>
<td>2.1, 6.1.4, 6.2.1, 6.2.2, 6.2.3, 6.4.1, 6.5, 6.6</td>
<td><p>Incorporated CR:</p>
<p>OMA-IOP-MEC-2014-0005R01-CR_LWM2M_ETS_new_test_cases</p>
<p>Editorial changes</p></td>
</tr>
<tr class="even">
<td><p>Candidate Version</p>
<p>OMA-ETS-LightweightM2M-V1_0</p></td>
<td>26 Feb 2014</td>
<td>n/a</td>
<td><p>Status changed to Candidate by TP</p>
<p>TP Ref # OMA-TP-2014-0047-INP_LightweightM2M_V1_0_ETS_for_Candidate_approval</p></td>
</tr>
<tr class="odd">
<td><p>Draft Version</p>
<p>OMA-ETS-LightweightM2M-V1_0</p></td>
<td>22 Jan 2015</td>
<td>6.7, 6.8</td>
<td><p>Incorporated CRs:</p>
<p>OMA-IOP-MEC-2015-0001R01-CR_LWM2M_ETS_CONMGMT_test_case_for_APN_configuration</p>
<p>OMA-IOP-MEC-2015-0002-CR_LWM2M_ETS_Location_Object_Test_Case<br />
OMA-IOP-MEC-2015-0003-CR_LWM2M_ETS_CONMGMT_test_case_for_Bearer_Selection</p>
<p>Editorial changes</p></td>
</tr>
<tr class="even">
<td><p>Candidate Version</p>
<p>OMA-ETS-LightweightM2M-V1_0</p></td>
<td>03 Feb 2015</td>
<td>n/a</td>
<td><p>Status changed to Candidate by TP</p>
<p>TP Ref # OMA-TP-2015-0042-INP_LightweightM2M_V1_0_ETS_for_Candidate_re_approval</p></td>
</tr>
<tr class="odd">
<td><p>Draft Versions</p>
<p>OMA-ETS-LightweightM2M-V1_0</p></td>
<td>11 Aug 2015</td>
<td>6</td>
<td><p>Incorporated CR:</p>
<p>OMA-IOP-MEC-2015-0007R01-CR_LWM2M_Tests_Cases_New_Structure_</p>
<p>Editorial changes</p></td>
</tr>
<tr class="even">
<td></td>
<td>03 Sep 2015</td>
<td>6.1.3.5, 6.1.6.2, 6.1.6.4, 6.1.6.6, 6.1.6.9.1, 6.1.6.9.2, 6.1.6.9.3, 6.1.6.11</td>
<td><p>Incorporated CRs:</p>
<p>OMA-IOP-2015-0154R01-CR_LWM2M_ETS__SettingValues_int205</p>
<p>OMA-IOP-2015-0156R01-CR_LWM2M_ETS_Obj_1</p>
<p>OMA-IOP-2015-0157R01-CR_LWM2M_ETS_Obj_3</p>
<p>OMA-IOP-2015-0164R01-CR_LWM2M_ETS_Obj_4</p>
<p>OMA-IOP-2015-0165R01-CR_LWM2M_ETS_Obj_6</p>
<p>OMA-IOP-2015-0166R01-CR_LWM2M_ETS_Obj_7</p>
<p>Editorial changes</p></td>
</tr>
<tr class="odd">
<td></td>
<td>16 Sep 2015</td>
<td>6.1.2.5, 6.1.6.8.1, 6.1.6.8.2, 6.1.6.8.5-6.1.6.8.15</td>
<td><p>Incorporated CRs:</p>
<p>OMA-IOP-2015-0155R01-CR_LWM2M_ETS_BootStrapServer_int105</p>
<p>OMA-IOP-2015-0158R02-CR_LWM2M_ETS_FirmwareUpdate_Obj_5</p>
<p>Editorial changes</p></td>
</tr>
<tr class="even">
<td><p>Candidate Version</p>
<p>OMA-ETS-LightweightM2M-V1_0</p></td>
<td>08 Dec 2015</td>
<td>n/a</td>
<td><p>Status changed to Candidate by TP</p>
<p>TP Ref # OMA-TP-2015-0207-INP_LightweightM2M_V1_0_ETS_for_Candidate_re_approval</p></td>
</tr>
<tr class="odd">
<td><p>Draft Version</p>
<p>OMA-ETS-LightweightM2M-V1_0</p></td>
<td>26 Jul 2016</td>
<td>1, 4, 6, 6.1.2, 6.1.3.1, 6.1.3.3, 6.1.3.4, 6.1.3.9, 6.1.4.1, 6.1.5.1, 6.1.6.4.2</td>
<td><p>Incorporated CR:</p>
<p>OMA-IOP-2016-0037-CR_LWM2M_ETS_Editorial_Cover</p></td>
</tr>
<tr class="even">
<td><p>Candidate Version</p>
<p>OMA-ETS-LightweightM2M-V1_0</p></td>
<td>29 Aug 2016</td>
<td>n/a</td>
<td><p>Status changed to Candidate by TP</p>
<p>TP Ref # OMA-TP-2016-0093-INP_LightweightM2M_V1_0_ETS_for_Notification</p></td>
</tr>
<tr class="odd">
<td><p>Draft Version</p>
<p>OMA-ETS-LightweightM2M-V1_0</p></td>
<td>15 Mar 2017</td>
<td>2.1, 3.3, 4, 6.1.2, B.1, C</td>
<td><p>Incorporated CR:</p>
<p>OMA-DM-LightweightM2M-2017-0065R03-CR_LwM2M_ETS_UpgradeProposals</p></td>
</tr>
<tr class="even">
<td><p>Draft Versions</p>
<p>OMA-ETS-LightweightM2M-V1_0_1</p></td>
<td>21 Mar 2017</td>
<td>6.1.3.1, 6.1.3.3, 6.1.3.4, 6.1.3.5, 6.1.3.7, 6.1.3.8, 6.1.3.9, 6.1.4, 6.1.5, 6.1.6.2, C.4</td>
<td><p>Incorporated CRs:</p>
<p>OMA-DM-LightweightM2M-2017-0076-CR_LwM2M_ETS_DM_SE_Intf</p>
<p>OMA-DM-LightweightM2M-2017-0077R01-CR_LwM2M_ETS_InfoReport_Intf</p>
<p>OMA-DM-LightweightM2M-2017-0079R01-CR_LwM2M_ETS_Server_Object</p>
<p>OMA-DM-LightweightM2M-2017-0080-CR_LwM2M_ETS_Security_401</p></td>
</tr>
<tr class="odd">
<td></td>
<td>31 Mar 2017</td>
<td>6.1.6.4, 6.1.6.6.1, C.5, C.6</td>
<td><p>Incorporated CRs:</p>
<p>OMA-DM-LightweightM2M-2017-0081R01-CR_LwM2M_ETS_CoreDeviceObj</p>
<p>OMA-DM-LightweightM2M-2017-0082-CR_LwM2M_ETS_CoreFwUpdate_1</p></td>
</tr>
<tr class="even">
<td></td>
<td>10 Apr 2017</td>
<td>6.1.6.7, 6.1.6.8, C.6, C.8</td>
<td><p>Incorporated CRs:</p>
<p>OMA-DM-LightweightM2M-2017-0085-CR_LwM2M_ETS_LocationObj</p>
<p>OMA-DM-LightweightM2M-2017-0086-CR_LwM2M_ETS_ConnStatObj</p></td>
</tr>
<tr class="odd">
<td></td>
<td>12 Apr 2017</td>
<td>6.1.6.5, C.5</td>
<td><p>Incorporated CR:</p>
<p>OMA-DM-LightweightM2M-2017-0084R02-CR_LwM2M_ETS_ConnMonObj</p></td>
</tr>
<tr class="even">
<td></td>
<td>25 May 2017</td>
<td>6.1.2.2, 6.1.2.4, 6.1.3.10, 6.1.6.6</td>
<td><p>Incorporated CRs:</p>
<p>OMA-DM-LightweightM2M-2017-0102R01-CR_LwM2M_ETS_CoreFwUpdate_2</p>
<p>OMA-DM-LightweightM2M-2017-0119R03-CR_ETS_1.0.1_Registration_Fix</p>
<p>OMA-DM-LightweightM2M-2017-0127-CR_ETS_1.0.1_Discover</p></td>
</tr>
<tr class="odd">
<td></td>
<td>06 Jun 2017</td>
<td>6.2.3.1, 6.2.3.2, C.10</td>
<td><p>Incorporated CR:</p>
<p>OMA-DM-LightweightM2M-2017-0131R01-CR_ETS_1.0.1_ConnMgmt_10_13_Fix</p></td>
</tr>
<tr class="even">
<td></td>
<td>22 Jun 2017</td>
<td>6.1.6.8.6, 6.1.6.8.7, 6.2.5, C.11</td>
<td><p>Incorporated CR:</p>
<p>OMA-DM-LightweightM2M-2017-0150-CR_ETS_1.0.1_Obj_Mngt_1</p></td>
</tr>
<tr class="odd">
<td></td>
<td>07 Jul 2017</td>
<td>6.1.1.1, 6.1.2.1, 6.1.2.3, 6.1.2.4, 6.1.3.1, 6.1.3.3, 6.1.3.4, 6.1.3.5, 6.1.3.7, 6.1.3.8, 6.1.3.9, 6.1.3.10, 6.1.6.4.1, 6.1.6.4.2, 6.1.6.4.9, 6.1.6.4.10, 6.1.6.5.1, 6.1.6.6.1, 6.1.6.6.14, 6.1.6.7.1, 6.1.6.8.1, 6.1.6.8.2, 6.2.3.1, C.11, C.13</td>
<td><p>Incorporated CRs:</p>
<p>OMA-DM-LightweightM2M-2017-0122R02-CR_ETS_Cellular_network_connectivity_Obj</p>
<p>OMA-DM-LightweightM2M-2017-0152-CR_ETS_1.0.1_Global_Fixes_1</p>
<p>OMA-DM-LightweightM2M-2017-0156-CR_ETS_1.0.1_Client_Initiated_BS</p></td>
</tr>
<tr class="even">
<td></td>
<td>12 Jul 2017</td>
<td>6.1.3.11, 6.1.3.13, 6.1.6.8.6, 6.1.6.8.7, 6.2, 6.3, C.14, D</td>
<td><p>Incorporated CRs:</p>
<p>OMA-DM-LightweightM2M-2017-0167R01-CR_ETS_1.0.1_MultiServerContext</p>
<p>OMA-DM-LightweightM2M-2017-0173-CR_ETS_1.0.1_Obj_Mgt_Move_Fix</p></td>
</tr>
<tr class="odd">
<td></td>
<td>01 Aug 2017</td>
<td>D</td>
<td><p>Incorporated CR:</p>
<p>OMA-DM-LightweightM2M-2017-0175-CR_ETS_1.0.1_AnnexD_Fix</p></td>
</tr>
<tr class="even">
<td></td>
<td>30 Aug 2017</td>
<td>E</td>
<td><p>Incorporated CR:</p>
<p>OMA-DM-LightweightM2M-2017-0181-CR_New_Appendix_Entry_Criteria_TestFest</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc51147390" class="anchor"><span id="_Toc51149244" class="anchor"><span id="_Toc124672223" class="anchor"><span id="_Toc427069034" class="anchor"><span id="_Toc491867281" class="anchor"></span></span></span></span></span>Additional Information

2.  <span id="_Toc427069035" class="anchor"><span id="_Toc491867282" class="anchor"></span></span>Example of Test Configuration and Setup

The following hardware components were part of a test setup.

-   M2M device equipped with LwM2M client

-   Computer that runs the browser interface to the LwM2M Server component

-   Server that runs the LwM2M Server software

-   USIM provisioned for use on the network.

-   External appliance which is connected directly to M2M device (e.g. light, temperature sensor, motor).

In addition the demonstration setup shall include the following software components:

-   Measurement software which enables to see e.g. LwM2M messages and CoAP messages.

<!-- -->

-   The software shall enable

<!-- -->

-   GUI to trigger the chosen test cases

-   To see the flow of information between client and Server, e.g. on LwM2M protocol level and on CoAP transport level.

1.  <span id="_Ref483494021" class="anchor"><span id="_Ref483494365" class="anchor"><span id="_Toc491867283" class="anchor"></span></span></span>LwM2M Configurations

When a Test Case references a certain Configuration of that Annex, it means the features of that configuration are the minimum ones which must be supported by LwM2M Clients & Servers to pass that test; a richer configuration (superset) may be used instead, as long as it still contains the minimum features.

1.  <span id="_Toc491867284" class="anchor"></span>Basic Configuration 1

PSK Mode support, no SMS support

1.  <span id="_Toc491867285" class="anchor"></span>Basic Configuration 2

PSK Mode & SMS supports

1.  <span id="_Toc491867286" class="anchor"></span>Configuration 3

This configuration is a superset of Configuration C.1.

1.  <span id="_Toc491867287" class="anchor"></span>Configuration 4

Configuration 4 is a superset of Configuration 3 and can be used instead ; it implements the optional Resources related to external or internal battery which the voltage could vary.

1.  <span id="_Toc491867288" class="anchor"></span>Configuration 5

This configuration is a superset of Configuration C.1 and can be used instead; it implements the full Connectivity Monitoring Object ID:4

1.  <span id="_Toc491867289" class="anchor"></span>Configuration 6

Configuration 6 is a superset of Configuration 4 and can be used instead; the configuration C.4, has been completed with all the optional resources of the Device Object.

1.  <span id="_Toc491867290" class="anchor"></span>Configuration 7

This configuration is a superset of Configuration C.1 and can be used instead ; it implements the full Location Object ID:6

1.  <span id="_Ref483494006" class="anchor"><span id="_Ref483494356" class="anchor"><span id="_Toc491867291" class="anchor"></span></span></span>Configuration 8

2.  <span id="_Toc491867292" class="anchor"></span>Configuration 9

This configuration is a superset of Configuration C.1 and can be used instead ; it implements the full Connectivity Statistics Object ID:7

1.  <span id="_Toc491867293" class="anchor"></span>Basic Connectivity Management Configuration 10

PSK Mode support, no SMS support

1.  <span id="_Toc481070001" class="anchor"><span id="_Toc491867294" class="anchor"></span></span>Basic Connectivity Management Configuration 11 supporting Object ID:10 version 1.1

PSK Mode support, no SMS support

1.  <span id="_Toc491867295" class="anchor"></span>Configuration 12

This configuration is a superset of Configuration C.1 and can be used instead; it implements the Basic Portfolio Object ID:16 (Identity Resource with 4 Instances)

1.  <span id="_Toc491867296" class="anchor"></span>Bootstrap Server Contact Configuration

PSK Mode support, no SMS support

1.  <span id="_Toc491867297" class="anchor"></span>Multi-Servers Context Initial Configuration

PSK Mode support, no SMS support

1.  <span id="_Toc491867298" class="anchor"></span>Core Test Coverage

The following table aims at quantifying the Test Coverage of LwM2M 1.0 provided by the set of interoperable Test Cases defined in ETS 1.0.1.

The LwM2M Test Cases are distributed into 8 Functional Blocks (*BLOCK) :*

-   Bootstrap Interface

-   Registration Interface

-   DM& SE Interface

-   Information Reporting Interface

-   Security

-   Queue Mode

-   Core Objects

-   Multi-Server Context

| *BLOCK*                |         |      |     |                                 |            |
|------------------------|---------|------|-----|---------------------------------|------------|---------|--------|--------|
| Test                   | *Cover* | Pass | *W* | Test                            | *Test IDs* | *Avail* | Pass   | Weight |
| *Bootstrap Interface * | 20,00%  | 0,0% | 10  | \[0-99\]                        | 0,2        | 0       | *1,00* |
|                        |         |      |     |                                 |            |         |        | * *    |
|                        |         |      |     | Client Initiated Boostrap Mode  | 0          | 1       | 0      | 0,20   |
|                        |         |      |     | Server Initiated Bootstrap Mode |            | 0       | 0      | 0,10   |
|                        |         |      |     | Smartcard Boostrap Mode         |            | 0       | 0      | 0,20   |

For each Functional Block, an indivual Test Coverage qualification is determined (*Cover*) and the final LwM2M Enabler Test Coverage is obtained by recombining each individual Test Coverage results pondered by an weight (*W*) specific to each Functional Block.

A Functional Block is composed of several Test Cases (*Test IDs*) which contribute to the final Block Functional Test Coverage result according to the individual availability *(Avail : 0 or 1)* and the individual weight (*Weight*) of these tests inside the group.

In addition, this table can be used to determin the gap between a certain implementation (LwM2M Server or Client) and the LwM2M Specification, in regards to the functionalities of the enabler covered by this Test Specification.

In the above example, the single available Test Case from the Bootstrap Interface, will only contribute to 2% of the final Test Coverage status, since only 20% of the Function Block functionality is covered (*Cover*) for a Weight of 10% regarding the ponderation of that Functional Block in the final LwM2M Enabler Test Coverage result.

|                          |     |            | Functional Test Coverage : Client&Server TS 1.0 Interoperability |                                 |          |         | -    |
|--------------------------|-----|------------|------------------------------------------------------------------|---------------------------------|----------|---------|------|
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  | BLOCK                           |          |         |      |
| Test Coverage Rate (TCR) |     |            |                                                                  | Test                            | Cover    | Pass    | W    |
| Overall Spec TCR         |     | **49,66%** |                                                                  | Bootstrap Interface             | 20,00%   | 0,0%    | 10   |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
| Implem Test Result       |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  | Registration Interface          | 80,0%    | 0,0%    |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         | 15   |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  | DM & SE Interface               | 70,00%   | 0,00%   |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         | 25   |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  | Information Reporting Interface | 60,00%   | 0,00%   |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         | 10   |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  | Security                        | 30,00%   | 0,00%   | 15   |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  | Queue Mode                      | 0,00%    | 0,00%   | 5    |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  | *Core Objects *                 | *41,88%* | *0,00%* | *14* |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  | Multi-Server Context            | 30,00%   | 0,00%   |      |
|                          |     |            |                                                                  |                                 |          |         | 6    |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         |      |
|                          |     |            |                                                                  |                                 |          |         | 100  |
|                          |     |            |                                                                  |                                 |          |         |      |

|     |     |     |                                     |
|-----|-----|-----|-------------------------------------|
|     |     |     | BLOCK                               |
|     |     |     | Test                                |
|     |     |     |                                     |
|     |     |     | *Core Objects *                     |
|     |     |     | Core Security Object                |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     | Core Server Object                  |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     | Core Access Control Object          |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     | Core Device Object                  |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     | Core Connectivity Monitoring Object |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     | Core Firmware Object Update         |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     | Core Connectivity Statistics Object |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |
|     |     |     |                                     |

|     |     |     | Core Location Object |        |       |     | \[800-849\]                                                       | 0,5 | *0* | *1,00* |      |
|-----|-----|-----|----------------------|--------|-------|-----|-------------------------------------------------------------------|-----|-----|--------|------|-----|
|     |     |     |                      | 50,00% | 0,00% | 1   | Querying the readable resources of object                         | 801 | 1   | 0      | 0,15 |     |
|     |     |     |                      |        |       |     | Setting the writable resources                                    | 805 | 1   | 0      | 0,05 |     |
|     |     |     |                      |        |       |     | Basic Observation and notification on Location Object Instance    | 810 | 1   | 0      | 0,30 |     |
|     |     |     |                      |        |       |     | Extended Observation and notification of Location Object Instance | 811 | 0   | 0      | 0,35 |     |
|     |     |     |                      |        |       |     | Create Multiple Resource Instances                                | 820 | 0   | 0      | 0,05 |     |
|     |     |     |                      |        |       |     | Create Object Instance                                            | 830 | 0   | 0      | 0,05 |     |
|     |     |     |                      |        |       |     | Delete Object Instance                                            | 835 | 0   | 0      | 0,05 |     |

1.  <span id="_Toc491867299" class="anchor"></span>Enabler Validation Plan

The validation of this enabler will be made based on the successful execution of test cases defined in the \[LWM2M-ETS\].

A summary of test results will be the evidence that those test cases were executed. The lack of open Problem Reports will be the evidence the test cases were successful executed and that any issue found whether on test specifications, technical specifications or other was correctly addressed.

1.  <span id="_Toc479759253" class="anchor"><span id="_Toc491867300" class="anchor"></span></span>Entry Criteria for TestFest

The following tests need to be performed and passed by implementations by members wishing to participate in the TestFest. This ensures minimal requisite capability of the implementations. The tests are defined in the ETS \[LWM2M-ETS\] and any special comments are noted.

| Test Case Id               | Special Conditions |
|----------------------------|--------------------|
| LightweightM2M-1.0-int-101 |                    |
| LightweightM2M-1.0-int-102 |                    |
| LightweightM2M-1.0-int-201 |                    |
| LightweightM2M-1.0-int-203 |                    |

<span id="_Toc479759462" class="anchor"><span id="_Toc395691187" class="anchor"></span></span>Table 1: Listing of Tests for Entry Criteria for TestFest

1.  <span id="_Toc491867301" class="anchor"></span>Enabler Validation Test Cases

The following table should list the set of tests that are used for enabler validation. Not applicable in this case as the enabler has been already agreed.

| Test Case Id | ETR Requirement Id/Feature Key | ETR Status | Notes |
|--------------|--------------------------------|------------|-------|
|              |                                |            |       |

Table 1: Enabler Validation Test Cases
