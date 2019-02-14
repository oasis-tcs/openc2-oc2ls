![OASIS Logo](http://docs.oasis-open.org/templates/OASISLogo-v2.0.jpg)
-------

# Open Command and Control (OpenC2) Language Specification Version 1.0
## Committee Specification Draft 07 /<br>Public Review Draft 01
## 17 October 2018
### Specification URIs
#### This version:
* http://docs.oasis-open.org/openc2/oc2ls/v1.0/csprd01/oc2ls-v1.0-csprd01.md (Authoritative)
* http://docs.oasis-open.org/openc2/oc2ls/v1.0/csprd01/oc2ls-v1.0-csprd01.html
* http://docs.oasis-open.org/openc2/oc2ls/v1.0/csprd01/oc2ls-v1.0-csprd01.pdf

#### Previous version:
* http://docs.oasis-open.org/openc2/oc2ls/v1.0/csd05/md/oc2ls-v1.0-wd07.md (Authoritative)
* http://docs.oasis-open.org/openc2/oc2ls/v1.0/csd05/oc2ls-v1.0-csd05.html
* http://docs.oasis-open.org/openc2/oc2ls/v1.0/csd05/oc2ls-v1.0-csd05.pdf

#### Latest version:
* http://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.md (Authoritative)
* http://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.html
* http://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.pdf

#### Technical Committee:
* [OASIS Open Command and Control (OpenC2) TC](https://www.oasis-open.org/committees/openc2/)

#### Chairs:
* Joe Brule (jmbrule@nsa.gov), [National Security Agency](https://www.nsa.gov/)
* Sounil Yu (sounil.yu@bankofamerica.com), [Bank of America](http://www.bankofamerica.com/)

#### Editors:
* Jason Romano (jdroman@nsa.gov), [National Security Agency](https://www.nsa.gov/)
* Duncan Sparrell (duncan@sfractal.com), [sFractal Consulting LLC](http://www.sfractal.com/)

#### Abstract:
Cyberattacks are increasingly sophisticated, less expensive to execute, dynamic and automated. The provision of cyberdefense via statically configured products operating in isolation is untenable. Standardized interfaces, protocols and data models will facilitate the integration of the functional blocks within a system and between systems. Open Command and Control (OpenC2) is a concise and extensible language to enable machine to machine communications for purposes of command and control of cyber defense components, subsystems and/or systems in a manner that is agnostic of the underlying products, technologies, transport mechanisms or other aspects of the implementation. It should be understood that a language such as OpenC2 is necessary but insufficient to enable coordinated cyber responses that occur within cyber relevant time. Other aspects of coordinated cyber response such as sensing, analytics, and selecting appropriate courses of action are beyond the scope of OpenC2.

#### Status:
This document was last revised or approved by the OASIS Open Command and Control (OpenC2) TC on the above date. The level of approval is also listed above. Check the "Latest version" location noted above for possible later revisions of this document. Any other numbered Versions and other technical work produced by the Technical Committee (TC) are listed at https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=openc2#technical.

TC members should send comments on this specification to the TC's email list. Others should send comments to the TC's public comment list, after subscribing to it by following the instructions at the "Send A Comment" button on the TC's web page at https://www.oasis-open.org/committees/openc2/.

This specification is provided under the [Non-Assertion](https://www.oasis-open.org/policies-guidelines/ipr#Non-Assertion-Mode) Mode of the OASIS IPR Policy, the mode chosen when the Technical Committee was established. For information on whether any patents have been disclosed that may be essential to implementing this specification, and any offers of patent licensing terms, please refer to the Intellectual Property Rights section of the TC's web page (https://www.oasis-open.org/committees/openc2/ipr.php).

Note that any machine-readable content ([Computer Language Definitions](https://www.oasis-open.org/policies-guidelines/tc-process#wpComponentsCompLang)) declared Normative for this Work Product is provided in separate plain text files. In the event of a discrepancy between any such plain text file and display content in the Work Product's prose narrative document(s), the content in the separate plain text file prevails.

#### Citation format:
When referencing this specification the following citation format should be used:

**[OpenC2-Lang-v1.0]**

_Open Command and Control (OpenC2) Language Specification Version 1.0_. Edited by Jason Romano and Duncan Sparrell. 17 October 2018. OASIS Committee Specification Draft 07 / Public Review Draft 01. http://docs.oasis-open.org/openc2/oc2ls/v1.0/csprd01/oc2ls-v1.0-csprd01.html. Latest version: http://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.html.

-------

## Notices
Copyright © OASIS Open 2018. All Rights Reserved.

All capitalized terms in the following text have the meanings assigned to them in the OASIS Intellectual Property Rights Policy (the "OASIS IPR Policy"). The full [Policy](https://www.oasis-open.org/policies-guidelines/ipr) may be found at the OASIS website.

This document and translations of it may be copied and furnished to others, and derivative works that comment on or otherwise explain it or assist in its implementation may be prepared, copied, published, and distributed, in whole or in part, without restriction of any kind, provided that the above copyright notice and this section are included on all such copies and derivative works. However, this document itself may not be modified in any way, including by removing the copyright notice or references to OASIS, except as needed for the purpose of developing any document or deliverable produced by an OASIS Technical Committee (in which case the rules applicable to copyrights, as set forth in the OASIS IPR Policy, must be followed) or as required to translate it into languages other than English.

The limited permissions granted above are perpetual and will not be revoked by OASIS or its successors or assigns.

This document and the information contained herein is provided on an "AS IS" basis and OASIS DISCLAIMS ALL WARRANTIES, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTY THAT THE USE OF THE INFORMATION HEREIN WILL NOT INFRINGE ANY OWNERSHIP RIGHTS OR ANY IMPLIED WARRANTIES OF MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE.

OASIS requests that any OASIS Party or any other party that believes it has patent claims that would necessarily be infringed by implementations of this OASIS Committee Specification or OASIS Standard, to notify OASIS TC Administrator and provide an indication of its willingness to grant patent licenses to such patent claims in a manner consistent with the IPR Mode of the OASIS Technical Committee that produced this specification.

OASIS invites any party to contact the OASIS TC Administrator if it is aware of a claim of ownership of any patent claims that would necessarily be infringed by implementations of this specification by a patent holder that is not willing to provide a license to such patent claims in a manner consistent with the IPR Mode of the OASIS Technical Committee that produced this specification. OASIS may include such claims on its website, but disclaims any obligation to do so.

OASIS takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this document or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any effort to identify any such rights. Information on OASIS' procedures with respect to rights in any document or deliverable produced by an OASIS Technical Committee can be found on the OASIS website. Copies of claims of rights made available for publication and any assurances of licenses to be made available, or the result of an attempt made to obtain a general license or permission for the use of such proprietary rights by implementers or users of this OASIS Committee Specification or OASIS Standard, can be obtained from the OASIS TC Administrator. OASIS makes no representation that any information or list of intellectual property rights will at any time be complete, or that any claims in such list are, in fact, Essential Claims.

The name "OASIS" is a trademark of [OASIS](https://www.oasis-open.org/), the owner and developer of this specification, and should be used only to refer to the organization and its official outputs. OASIS welcomes reference to, and implementation and use of, specifications, while reserving the right to enforce its marks against misleading uses. Please see https://www.oasis-open.org/policies-guidelines/trademark for above guidance.

-------

# Table of Contents
[[TOC]]

-------

# 1 Introduction
OpenC2 is a suite of specifications that enables command and control of cyber defense systems and components.  OpenC2 typically uses a request-response paradigm where a command is encoded by an OpenC2 producer (managing application) and transferred to an OpenC2 consumer (managed device or virtualized function) using a secure transfer protocol. The consumer can respond with status and any requested information.  The contents of both the command and the response are fully defined in schemas, allowing both parties to recognize the syntax constraints imposed on the exchange.

OpenC2 allows the application producing the commands to discover the set of capabilities supported by the managed devices.  These capabilities permit the managing application to adjust its behavior to take advantage of the features exposed by the managed device.  The capability definitions can be easily extended in a noncentralized manner, allowing standard and non-standard capabilities to be defined with semantic and syntactic rigor.

## 1.1 IPR Policy
This specification is provided under the [Non-Assertion](https://www.oasis-open.org/policies-guidelines/ipr#Non-Assertion-Mode) Mode of the [OASIS IPR Policy](https://www.oasis-open.org/policies-guidelines/ipr), the mode chosen when the Technical Committee was established. For information on whether any patents have been disclosed that may be essential to implementing this specification, and any offers of patent licensing terms, please refer to the Intellectual Property Rights section of the TC's web page ([https://www.oasis-open.org/committees/openc2/ipr.php](https://www.oasis-open.org/committees/openc2/ipr.php)).

## 1.2 Terminology
* **Action**: The task or activity to be performed.
* **Actuator**: The entity that performs the action.
* **Command**: A message defined by an action-target pair that is sent from a producer and received by a consumer.
* **Consumer**: A managed device / application that receives commands.  Note that a single device / application can have both consumer and producer capabilities.
* **Producer**: A manager application that sends commands.
* **Response**: A message from a consumer to a producer acknowledging a command or returning the requested resources or status to a previously received request.
* **Target**: The object of the action, i.e., the action is performed on the target.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [[RFC2119](#rfc2119)] and [[RFC8174](#rfc8174)].

## 1.3 Normative References

###### [OpenC2-HTTPS-v1.0]
_Specification for Transfer of OpenC2 Messages via HTTPS Version 1.0_. Edited by David Lemire. Latest version: http://docs.oasis-open.org/openc2/open-impl-https/v1.0/open-impl-https-v1.0.html
###### [OpenC2-SLPF-v1.0]
_Open Command and Control (OpenC2) Profile for Stateless Packet Filtering Version 1.0_. Edited by Joe Brule, Duncan Sparrell, and Alex Everett. Latest version: http://docs.oasis-open.org/openc2/oc2slpf/v1.0/oc2slpf-v1.0.html
###### [RFC768]
Postel, J., "User Datagram Protocol", STD 6, RFC 768, August 1980, http://www.rfc-editor.org/info/rfc768.
###### [RFC792]
Postel, J., "Internet Control Message Protocol", STD 5, RFC 792, September 1981, http://www.rfc-editor.org/info/rfc792.
###### [RFC793]
Postel, J., "Transmission Control Protocol", STD 7, RFC 793, September 1981, http://www.rfc-editor.org/info/rfc793.
###### [RFC1034]
Mockapetris, P. V., "Domain names - concepts and facilities", STD 13, RFC 1034, November 1987, http://www.rfc-editor.org/info/rfc1034.
###### [RFC1123]
Braden, R., "Requirements for Internet Hosts - Application and Support", STD 3, RFC 1123, October 1989, http://www.rfc-editor.org/info/rfc1123.
###### [RFC1321]
Rivest, R., "The MD5 Message-Digest Algorithm", RFC 1321, April 1992, http://www.rfc-editor.org/info/rfc1321.
###### [RFC2119]
Bradner, S., "Key words for use in RFCs to Indicate Requirement Levels", BCP 14, RFC 2119, DOI 10.17487/RFC2119, March 1997, http://www.rfc-editor.org/info/rfc2119.
###### [RFC3986]
Berners-Lee, T., Fielding, R., Masinter, L., "Uniform Resource Identifier (URI): Generic Syntax", STD 66, RFC 3986, January 2005, http://www.rfc-editor.org/info/rfc3986.
###### [RFC4122]
Leach, P., Mealling, M., Salz, R., "A Universally Unique IDentifier (UUID) URN Namespace", RFC 4122, July 2005, http://www.rfc-editor.org/info/rfc4122.
###### [RFC4648]
Josefsson, S., "The Base16, Base32, and Base64 Data Encodings", RFC 4648, October 2006, http://www.rfc-editor.org/info/rfc4648.
###### [RFC4960]
Stewart, R. "Stream Control Transmission Protocol", RFC 4960, September 2007, http://www.rfc-editor.org/info/rfc4960.
###### [RFC5237]
Arkko, J., Bradner, S., "IANA Allocation Guidelines for the Protocol Field", BCP 37, RFC 5237, February 2008, http://www.rfc-editor.org/info/rfc5237.
###### [RFC5322]
Resnick, P., "Internet Message Format", RFC 5322, October 2008, http://www.rfc-editor.org/info/rfc5322.
###### [RFC5612]
Eronen, P., Harrington, D., "Enterprise Number for Documentation Use", RFC 5612, August 2009, http://www.rfc-editor.org/info/rfc5612.
###### [RFC6234]
Eastlake 3rd, D., Hansen, T., "US Secure Hash Algorithms (SHA and SHA-based HMAC and HKDF)", RFC 6234, May 2011, http://www.rfc-editor.org/info/rfc6234.
###### [RFC6335]
Cotton, M., Eggert, L., Touch, J., Westerlund, M., Cheshire, S., "Internet Assigned Numbers Authority (IANA) Procedures for the Management of the Service Name and Transport Protocol Port Number Registry", BCP 165, RFC 6335, August 2011, http://www.rfc-editor.org/info/rfc6335.
###### [RFC6838]
Freed, N., Klensin, J., Hansen, T., "Media Type Specifications and Registration Procedures, BCP 13, RFC 6838, January 2013, http://www.rfc-editor.org/info/rfc6838.
###### [RFC7493]
Bray, T., "The I-JSON Message Format", RFC 7493, March 2015, http://www.rfc-editor.org/info/rfc7493.
###### [RFC8174]
Leiba, B., "Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words", BCP 14, RFC 8174, DOI 10.17487/RFC8174, May 2017, http://www.rfc-editor.org/info/rfc8174.
###### [RFC8259]
Bray, T., "The JavaScript Object Notation (JSON) Data Interchange Format", STD 90, RFC 8259, December 2017, http://www.rfc-editor.org/info/rfc8259.

## 1.4 Non-Normative References
###### [IACD]
M. J. Herring, K. D. Willett, "Active Cyber Defense: A Vision for Real-Time Cyber Defense," Journal of Information Warfare, vol. 13, Issue 2, p. 80, April 2014.<br>Willett, Keith D., "Integrated Adaptive Cyberspace Defense: Secure Orchestration", International Command and Control Research and Technology Symposium, June 2015.
###### [UML]
"UML Multiplicity and Collections", https://www.uml-diagrams.org/multiplicity.html

## 1.5 Document Conventions
### 1.5.1 Naming Conventions
* [RFC2119](#rfc2119)/[RFC8174](#rfc8174) key words (see [section 1.4](#14-non-normative-references)) are in all uppercase.
* All property names and literals are in lowercase, except when referencing canonical names defined in another standard (e.g., literal values from an IANA registry).
* All words in structure component names are capitalized and are separated with a hyphen, e.g., ACTION, TARGET, TARGET-SPECIFIER.
* Words in property names are separated with an underscore (_), while words in string enumerations and type names are separated with a hyphen (-).
* The term "hyphen" used here refers to the ASCII hyphen or minus character, which in Unicode is "hyphen-minus", U+002D.
* All type names, property names, object names, and vocabulary terms are between three and 40 characters long.

### 1.5.2 Font Colors and Style
The following color, font and font style conventions are used in this document:

* A fixed width font is used for all type names, property names, and literals.
* Property names are in bold style – **`created_a**t`
* All examples in this document are expressed in JSON. They are in fixed width font, with straight quotes, black text and a light shaded background, and 4-space indentation. JSON examples in this document are representations of JSON Objects. They should not be interpreted as string literals. The ordering of object keys is insignificant. Whitespace before or after JSON structural characters in the examples are insignificant [[RFC8259](#rfc8259)].
* Parts of the example may be omitted for conciseness and clarity. These omitted parts are denoted with the ellipses (...).

Example:

```javascript
{   
    "action": "contain",
    "target": {
        "user_account": {
            "user_id": "fjbloggs",
            "account_type": "windows-local"
        }
    }
}
```

## 1.6 Overview
OpenC2 is a suite of specifications to command actuators that execute cyber defense functions in an unambiguous, standardized way.  These specifications include the OpenC2 Language Specification, Actuator Profiles, and Transfer Specifications.  The OpenC2 Language Specification and Actuator Profile specifications focus on the standard at the producer and consumer of the command and response while the transfer specifications focus on the protocols for their exchange.

* The OpenC2 Language Specification provides the semantics for the essential elements of the language, the structure for commands and responses, and the schema that defines the proper syntax for the language elements that represent the command or response.
* OpenC2 Actuator Profiles specify the subset of the OpenC2 language relevant in the context of specific actuator functions. Cyber defense components, devices, systems and/or instances may (in fact are likely) to implement multiple actuator profiles.  Actuator profiles define the requirements for performing a specific function, and may define new language elements if needed to perform that function.
* OpenC2 Transfer Specifications utilize existing protocols and standards to implement OpenC2 in specific environments. These standards are used for communications and security functions beyond the scope of the language, such as message transfer encoding, authentication, and end-to-end transfer of OpenC2 messages.

The OpenC2 Language Specification defines a language used to compose messages for command and control of cyber defense systems and components.  A message consists of a header and a payload (_defined_ as a message body in the OpenC2 Language Specification Version 1.0 and _specified_ in one or more actuator profiles). 

In general, there are two types of participants involved in the exchange of OpenC2 messages, as depicted in Figure 1-1:

1. **OpenC2 Producers**: An OpenC2 Producer is an entity that creates commands to provide instruction to one or more systems to act in accordance with the content of the command. An OpenC2 Producer may receive and process responses in conjunction with a command.
2. **OpenC2 Consumers**: An OpenC2 Consumer is an entity that receives and may act upon an OpenC2 command.  An OpenC2 Consumer may create responses that provide any information captured or necessary to send back to the OpenC2 Producer. 

The language defines two payload structures:

1. **Command**: An instruction from one system known as the OpenC2 "Producer", to one or more systems, the OpenC2 "Consumer(s)", to act on the content of the command.
2. **Response**: Any information captured or necessary to send back to the OpenC2 Producer  that issued the Command, i.e., the OpenC2 Consumer’s response to the OpenC2 Producer.

![no alt title](images/image_1.png)

**Figure 1-1. OpenC2 Message Exchange**

OpenC2 implementations integrate the related OpenC2 specifications described above with related industry specifications, protocols, and standards. Figure 1 depicts the relationships among OpenC2 specifications, and their relationships to other industry standards and environment-specific implementations of OpenC2. Note that the layering of implementation aspects in the diagram is notional, and not intended to preclude the use of any particular protocol or standard.

![no alt title](images/image_2.png)

**Figure 1-2. OpenC2 Documentation and Layering Model**

OpenC2 is conceptually partitioned into four layers as shown in Table 1-1.

**Table 1-1. OpenC2 Protocol Layers**

| Layer | Examples |
| :--- | :--- |
| Function-Specific Content | Actuator Profiles<br>(standard and extension) |
| Common Content | Language Specification<br>(this document) |
| Message | Transfer Specifications<br>(OpenC2-over-HTTPS, OpenC2-over-CoAP, …) |
| Secure Transfer | HTTPS, CoAP, MQTT, OpenDXL, ... |

* The **Secure Transfer** layer provides a communication path between the producer and the consumer.  OpenC2 can be layered over any standard transfer protocol.
* The **Message** layer provides a transfer- and content-independent mechanism for conveying requests, responses, and notifications.  A transfer specification maps transfer-specific protocol elements to a transfer-independent set of message elements consisting of content and associated metadata.  
* The **Common Content** layer defines the structure of OpenC2 commands and responses and a set of common language elements used to construct them.
* The **Function-specific Content** layer defines the language elements used to support a particular cyber defense function.  An actuator profile defines the implementation conformance requirements for that function.  OpenC2 Producers and Consumers will support one or more profiles.

## 1.7 Goal
The goal of the OpenC2 Language Specification is to provide a language for interoperating between functional elements of cyber defense systems. This language used in conjunction with OpenC2 Actuator Profiles and OpenC2 Transfer Specifications allows for vendor-agnostic cybertime response to attacks.

The Integrated Adaptive Cyber Defense (IACD) framework defines a collection of activities, based on the traditional OODA (Observe–Orient–Decide–Act) Loop [[IACD](#iacd)]:

* Sensing:  gathering of data regarding system activities
* Sense Making:  evaluating data using analytics to understand what's happening
* Decision Making:  determining a course-of-action to respond to system events
* Acting:  Executing the course-of-action 

The goal of OpenC2 is to enable coordinated defense in cyber-relevant time between decoupled blocks that perform cyber defense functions.  OpenC2 focuses on the Acting portion of the IACD framework; the assumption that underlies the design of OpenC2 is that the sensing/ analytics have been provisioned and the decision to act has been made. This goal and these assumptions guides the design of OpenC2:

* **Technology Agnostic:**  The OpenC2 language defines a set of abstract atomic cyber defense actions in a platform and product agnostic manner
* **Concise:**  An OpenC2 command is intended to convey only the essential information required to describe the action required and can be represented in a very compact form for communications-constrained environments
* **Abstract:**  OpenC2 commands and responses are defined abstractly and can be encoded and transferred via multiple schemes as dictated by the needs of different implementation environments
* **Extensible:**  While the OpenC2 language defines a core set of actions and targets for cyber defense, it supports separate definition of additional language elements to accommodate new cyber defense technologies.

## 1.8 Purpose and Scope
The OpenC2 Language Specification defines the set of components to assemble a complete command and control message and provides a framework so that the language can be extended. To achieve this purpose, the scope of this specification includes:

1. the set of actions and options that may be used in OpenC2 commands
2. the set of targets and target specifiers
3. a syntax that defines the structure of commands and responses
4. a JSON serialization of OpenC2 commands and responses
5. the procedures for extending the language

The OpenC2 language assumes that the event has been detected, a decision to act has been made, the act is warranted, and the initiator and recipient of the commands are authenticated and authorized. The OpenC2 language was designed to be agnostic of the other aspects of cyber defense implementations that realize these assumptions. The following items are beyond the scope of this specification:

1. Language elements applicable to some actuators, which may be defined in individual actuator profiles.
2. Alternate serializations of OpenC2 commands and responses.
3. The enumeration of the protocols required for transport, information assurance, sensing, analytics and other external dependencies.

-------

# 2 OpenC2 Language Description
The OpenC2 language has two distinct content types: command and response. The command is sent from a producer to a consumer and describes an action to be performed by an actuator on a target. The response is sent from a consumer, usually back to the producer, and is a means to provide information (such as acknowledgement, status, etc.) as a result of a command.

## 2.1 OpenC2 Command
The command describes an action to be performed on a target and may include information identifying the actuator or actuators that are to execute the command. 

A command has four main components: ACTION, TARGET, ARGUMENTS, and ACTUATOR. The following list summarizes the components of a command. 

* **ACTION** (required): The task or activity to be performed.
* **TARGET** (required): The object of the action. The ACTION is performed on the TARGET.
    * **TARGET-NAME** (required): The name of the object of the action.
    * **TARGET-SPECIFIERS** (optional): The specifier further identifies the target to some level of precision, such as a specific target, a list of targets, or a class of targets.
* **ARGUMENTS** (optional): Provide additional information on how the command is to be performed, such as date/time, periodicity, duration etc.
* **ACTUATOR** (optional): The ACTUATOR executes the command (the ACTION and TARGET). The ACTUATOR type will be defined within the context of an Actuator Profile.
    * **ACTUATOR-NAME** (required): The name of the set of functions (e.g., "slpf") performed by the actuator, and the name of the profile defining commands applicable to those functions.
    * **ACTUATOR-SPECIFIERS** (optional): The specifier identifies the actuator to some level of precision, such as a specific actuator, a list of actuators, or a group of actuators.

The ACTION and TARGET components are required and are populated by one of the actions in [Section 3.3.1.1](#3311-action) and the targets in [Section 3.3.1.2](#3312-target). A particular target may be further refined by one or more TARGET-SPECIFIERS. Procedures to extend the targets are described in [Section 3.3.3](#334-extensions).

TARGET-SPECIFIERS provide additional precision to identify the target (e.g., 10.1.2.3) and may include a method of identifying multiple targets of the same type (e.g., 10.1.0.0/16).

The ARGUMENTS component, if present, is populated by one or more 'command arguments' that determine how the command is executed. ARGUMENTS influence the command by providing information such as time, periodicity, duration, or other details on what is to be executed. They can also be used to convey the need for acknowledgement or additional status information about the execution of a command. The valid ARGUMENTS defined in this specification are in [Section 3.3.1.4](#3314-command-arguments).

An ACTUATOR is an implementation of a cyber defense function that executes the command. An Actuator Profile is a specification that identifies the subset of ACTIONS, TARGETS and other aspects of this language specification that are required or optional in the context of a particular ACTUATOR. An Actuator Profile may extend the language by defining additional ARGUMENTS, ACTUATOR-SPECIFIERS, and/or TARGETS that are meaningful and possibly unique to the actuator.

The ACTUATOR optionally identifies the entity or entities that are tasked to execute the command. Specifiers for actuators refine the command so that a particular function, system, class of devices, or specific device can be identified. 

The ACTUATOR component may be omitted from a command and typically will not be included in implementations where the identities of the endpoints are unambiguous or when a high-level effects-based command is desired and the tactical decisions on how the effect is achieved is left to the recipient.  

## 2.2 OpenC2 Response
The OpenC2 Response is a message sent from the recipient of a command. Response messages provide acknowledgement, status, results from a query, or other information.

The following list summarizes the fields and subfields of an OpenC2 Response. 

* **STATUS** (required): An integer containing a numerical status code
* **STATUS_TEXT** (optional): A free-form string containing human-readable description of the response status. The string can contain more detail than is represented by the status code, but does not affect the meaning of the response.
* **RESULTS** (optional): Contains the data or extended status code that was requested from an OpenC2 Command. 

-------

# 3 OpenC2 Language Definition 
## 3.1 Base Components and Structures
### 3.1.1 Data Types
The syntax of valid OpenC2 messages is defined using an information model constructed from the data types presented here:

| Type | Description |
| :--- | :--- |
| **Primitive Types** |   |
| Binary | A sequence of octets.  Length is the number of octets. |
| Boolean | A logical entity that can have two values: `true` and `false`. |
| Integer | A whole number. |
| Number | A real number. |
| Null | Nothing, used to designate fields with no value. |
| String | A sequence of characters. Each character must have a valid Unicode codepoint.  Length is the number of characters. |
| **Structures** |   |
| Array | An ordered list of unnamed fields. Each field has an ordinal position and type. |
| ArrayOf | An ordered list of unnamed fields of the same type. Each field has an ordinal position and the specified type. |
| Choice | One field selected from a set of named fields. The value has a name and type. |
| Enumerated | A set of id:name pairs where id is an integer. The Enumerated.ID subtype is a set of ids only. |
| Map | An unordered set of named fields. Each field has an id, name and type. |
| Record | An ordered list of named fields, e.g. a message, record, structure, or row in a table. Each field has an ordinal position, name, and type. |

### 3.1.2 Derived Data Types
The following types are defined as value constraints applied to String (text string), Binary (octet string) or Integer values.  The serialized representation of the base types is specified in [Section 3.1.5](#315-serialization), but there are no restrictions on how derived types are represented internally by an implementation. 

| Type | Base | Description |
| :--- | :--- | :--- |
| Domain-Name | String | RFC 1034 Section 3.5 |
| Date-Time | Integer | Milliseconds since 00:00:00 UTC, 1 January 1970. |
| Duration | Integer | Milliseconds. |
| Email-Addr | String | RFC 5322 Section 3.4.1 |
| Identifier | String | (TBD rules, e.g., initial alpha followed by alphanumeric or underscore) |
| IP-Addr | Binary | 32 bit IPv4 address or 128 bit IPv6 address |
| MAC-Addr | Binary | Media Access Control / Extended Unique Identifier address - EUI-48 or EUI-64. |
| Port | Integer | 16 bit RFC 6335 Transport Protocol Port Number |
| Request-Id | Binary | A value of up to 128 bits |
| URI | String | RFC 3986 |
| UUID | Binary | 128 bit Universal Unique Identifier, RFC 4122 Section 4 |

### 3.1.3 Multiplicity
Property tables for types based on Array, Choice, Map and Record include a multiplicity column (#) that specifies the minimum and maximum cardinality (number of elements) of a field.  As used in the Unified Modeling Language ([UML](#uml)), typical examples of multiplicity are:

| Multiplicity | Description | Keywords |
| :--- | :--- | :--- |
| 1 | Exactly one instance | Required |
| 0..1 | No instances or one instance | Optional |
| 1..* | At least one instance | Required, Repeatable |
| 0..* | Zero or more instances | Optional, Repeatable |
| m..n | At least m but no more than n instances | Required, Repeatable |

When used with a Type, multiplicity is enclosed in square brackets, e.g.,:

| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **Features** | ArrayOf(Feature) [0..10] | An array of zero to ten names used to query an actuator for its supported capabilities. |

### 3.1.4 Derived Enumerations
An Enumerated field may be derived ("auto-generated") from the fields of a Choice, Map or Record type by appending ".*" to the type name.

**_Type: Example-sel (Record)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | targets | Target.* | 1..* | Enumeration auto-generated from a Choice |

### 3.1.5 Imported Types
Each Actuator profile defines a *base schema* - the subset of the OpenC2 language relevant in the context of specific actuator functions.  Each profile has a unique name used to unambiguously identify the profile document (and it's base schema).

In addition, a profile may define profile-specific types that are *imported* by its base schema. Type definitions are imported under a *namespace* to allow profiles to be developed independently and their definitions brought together into a single merged schema without risk of ambiguity or name collisions. A namespace consists of:

* The unique name of the schema being imported
* A short namespace identifier (**nsid**) assigned locally within the base schema to refer to the unique name

In this document, type definitions are represented as tables and importing is a conceptual process.  When using a schema language, importing is an actual process that takes a base schema and a set of imported schemas as inputs and produces a single merged schema as output. In both cases the base schema locally assigns a namespace identifier to each schema that it imports, and importing a schema means prepending the namespace identifier to all type names defined in that schema.

Producers and Consumers MUST support the syntax defined by the merged schema, regardless of whether the implementation is based on conceptually merging tables from a set of documents or physically merging a set of schema files.

**Example - Import a Schema**

Assume that a schema being imported includes the following type definitions:

**_Type: Target (Choice)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **device** | Device | 1 | |

**_Type: Device (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **model** | String | 0..1 | |
| 2 | **manufacturer** | String | 0..1 | |

After conceptually importing that schema under the "abc" namespace identifier, the base schema would be interpreted as if it contained the following definitions:

**_Type: abc:Target (Choice)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **device** | abc:Device | 1 | |

**_Type: abc:Device (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **model** | String | 0..1 | |
| 2 | **manufacturer** | String | 0..1 | |

A Consumer lists the profiles it supports in response to the "query features imports" command. The Producer then knows the unique names of all imported profiles and the nsids assigned to each profile by that Consumer. The Target type defined in the profile's base schema contains a subset of the Target fields defined in this document, plus a field for each imported profile:

**_Type: Target (Choice)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **artifact** | Artifact | 1 | An array of bytes representing a file-like object or a link to that object. |
| 3 | **device** | Device | 1 | The properties of a hardware device. |
| 7 | **domain_name** | Domain-Name | 1 | A network domain name. |
| 1030 | **abc** | abc:Target | 1 | Imported targets defined in the "abc" profile |

The **device** target and the **abc** target have different Types, and even though the combined schema includes type definitions for both Device and abc:Device, those definitions do not conflict.

The ID and Name of a field whose Type is imported are arbitrary, but because there may not be a way for a Producer to determine the schema used by a Consumer, the field Name assigned to an imported type SHOULD equal the nsid of that type. 

### 3.1.6 Serialization
OpenC2 is agnostic of any particular serialization; however, implementations MUST support JSON serialization in accordance with RFC 7493 and additional requirements specified in the following table.

**JSON Serialization Requirements:**

| OpenC2 Data Type | JSON Serialization Requirement |
| :--- | :--- |
| **Binary** | JSON **string** containing Base64url encoding of the binary value as defined in Section 5 of RFC 4648. |
| **Boolean** | JSON **true** or **false** |
| **Integer** | JSON **number** |
| **Number** | JSON **number** |
| **Null** | JSON **null** |
| **String** | JSON **string** |
| **Array** | JSON **array** |
| **ArrayOf** | JSON **array** |
| **Choice** | JSON **object** with one member.  Member key is the field name.   |
| Choice.ID | JSON **object** with one member. Member key is the integer field id converted to string. |
| **Enumerated** | JSON **string** |
| **Enumerated.ID** | JSON **integer** |
| **Map** | JSON **object**. Member keys are field names. |
| **Map.ID** | JSON **object**. Member keys are integer field ids converted to strings. |
| **Record** | JSON **object**. Member keys are field names. |

#### 3.1.6.1 ID and Name Serialization
Instances of Enumerated types and keys for Choice and Map types are serialized as ID values except when using serialization formats intended for human consumption, where Name strings are used instead.  Defining a type using ".ID" appended to the base type (e.g., Enumerated.ID, Map.ID) indicates that:

1. Type definitions and application values use only the ID.  There is no corresponding name except as an optional part of the description.
2. Instances of Enumerated values and Choice/Map keys are serialized as IDs regardless of serialization format.

#### 3.1.6.2 Integer Serialization
For machine-to-machine serialization formats, integers are represented as binary data, e.g., 32 bits, 128 bits.   But for human-readable serialization formats (XML and JSON), integers are converted to strings.  For example, the JSON "number" type represents integers and real numbers as decimal strings without quotes, e.g., { "height": 68.2 }, and as noted in RFC 7493 Section 2.2, a sender cannot expect a receiver to treat an integer with an absolute value greater than 2^^53 as an exact value.

The default representation of Integer types in text serializations is the native integer type for that format, e.g., "number" for JSON.   Integer fields with a range larger than the IEEE 754 exact range (e.g., 64, 128, 2048 bit values) are indicated by appending ".<bit-size>" or ".*" to the type, e.g. Integer.64 or Integer.*.  All serializations ensure that large Integer types are transferred exactly, for example in the same manner as Binary types.  Integer values support arithmetic operations; Binary values are not intended for that purpose.

## 3.2 Message
As described in Section 1.1, this language specification and one or more actuator profiles define the content of OpenC2 commands and responses, while transfer specifications define the on-the-wire format of a message over specific secure transport protocols.  Transfer specifications are agnostic with regard to content, and content is agnostic with regard to transfer protocol.  This decoupling is accomplished by defining a standard message interface used to transfer any type of content over any transfer protocol.

A message is a content- and transport-independent set of elements conveyed between consumers and producers.  To ensure interoperability all transfer specifications must unambiguously define how the message elements in [Table 3-1](#table-3-1-common-message-elements) are represented within the secure transport protocol. This does not imply that all message elements must be used in all messages.  Content, content_type, and msg_type are required, while other message elements are not required by this specification but may be required by other documents.

###### Table 3-1. Common Message Elements

| Name | Description |
| :--- | :--- |
| **content** | Message body as specified by content_type and msg_type. |
| **content_type** | String. Media Type that identifies the format of the content, including major version. Incompatible content formats must have different content_types.  Content_type **application/openc2** identifies content defined by OpenC2 language specification versions 1.x, i.e., all versions that are compatible with version 1.0. |
| **msg_type** | Message-Type. One of **request**, **response**, or **notification**.  For the **application/openc2** content_type the request content is an OpenC2-Command and the response content is an OpenC2-Response.  OpenC2 does not currently define any notification content. |
| **status** | Status-Code.  Populated with a numeric status code in response messages.  Not present in request or notification messages. |
| **request_id** | Request-Id. A unique identifier value of up to 128 bits that is attached to request and response messages. This value is assigned by the sender and is copied unmodified into all responses to support  reference to a particular command, transaction or event chain. |
| **created** | Date-Time. Creation date/time of the content, the number of milliseconds since 00:00:00 UTC, 1 January 1970. |
| **from** | String. Authenticated identifier of the creator of or authority for execution of a message. |
| **to** | ArrayOf(String). Authenticated identifier(s) of the authorized recipient(s) of a message. |

Implementations may use environment variables, private APIs, data structures, class instances, pointers, or other mechanisms to represent messages within the local environment.  However the internal representation of a message does not affect interoperability and is therefore beyond the scope of OpenC2.  This means that the message content is a data structure in whatever form is used within an implementation, not a serialized representation of that structure.  Content is the input provided to a serializer or the output of a de-serializer.  Msg_type is a three-element enumeration whose protocol representation is defined in each transfer spec, for example as a string, an integer, or a two-bit field.  The internal form of enumerations, like content, does not affect interoperability and is therefore unspecified.

## 3.3 Content
The scope of this specification is to define the ACTION and TARGET portions of an OpenC2 command and the common portions of an OpenC2 response.  The properties of the OpenC2 command are defined in [Section 3.3.1](#331-openc2-command) and the properties of the response are defined in [Section 3.3.2](#332-openc2-response).

In addition to the ACTION and TARGET, an OpenC2 command has an optional ACTUATOR. Other than identification of namespace identifier, the semantics associated with the ACTUATOR specifiers are beyond the scope of this specification.  The actuators and actuator-specific results contained in a response are specified in ‘Actuator Profile Specifications’ such as StateLess Packet Filtering Profile, Routing Profile etc.

### 3.3.1 OpenC2 Command
The OpenC2 Command describes an action performed on a target. 

**_Type: OpenC2-Command (Record)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **action** | Action | 1 | The task or activity to be performed (i.e., the 'verb'). |
| 2 | **target** | Target | 1 | The object of the action. The action is performed on the target. |
| 3 | **args** | Args | 0..1 | Additional information that applies to the command. |
| 4 | **actuator** | Actuator | 0..1 | The subject of the action. The actuator executes the action on the target. |

#### 3.3.1.1 Action
**_Type: Action (Enumerated)_**

| ID | Name | Description |
| :--- | :--- | :--- |
| 1 | **scan** | Systematic examination of some aspect of the entity or its environment. |
| 2 | **locate** | Find an object physically, logically, functionally, or by organization. |
| 3 | **query** | Initiate a request for information. |
| 6 | **deny** | Prevent a certain event or action from completion, such as preventing a flow from reaching a destination or preventing access. |
| 7 | **contain** | Isolate a file, process, or entity so that it cannot modify or access assets or processes. |
| 8 | **allow** | Permit access to or execution of a target. |
| 9 | **start** | Initiate a process, application, system, or activity. |
| 10 | **stop** | Halt a system or end an activity. |
| 11 | **restart** | Stop then start a system or an activity. |
| 14 | **cancel** | Invalidate a previously issued action. |
| 15 | **set** | Change a value, configuration, or state of a managed entity. |
| 16 | **update** | Instruct a component to retrieve, install, process, and operate in accordance with a software update, reconfiguration, or other update. |
| 18 | **redirect** | Change the flow of traffic to a destination other than its original destination. |
| 19 | **create** | Add a new entity of a known type (e.g., data, files, directories). |
| 20 | **delete** | Remove an entity (e.g., data, files, flows). |
| 22 | **detonate** | Execute and observe the behavior of a target (e.g., file, hyperlink) in an isolated environment. |
| 23 | **restore** | Return a system to a previously known state. |
| 28 | **copy** | Duplicate an object,  file, data flow or artifact. |
| 30 | **investigate** | Task the recipient to aggregate and report information as it pertains to a security event or incident. |
| 32 | **remediate** | Task the recipient to eliminate a vulnerability or attack point. |

The following actions are under consideration for use in future versions of the Language Specification. Implementers may use these actions with the understanding that they may not be in future versions of the language.

* **report** - Task an entity to provide information to a designated recipient
* **pause** - Cease operation of a system or activity while maintaining state.
* **resume** - Start a system or activity from a paused state
* **move** - Change the location of a file, subnet, network, or process
* **snapshot** - Record and store the state of a target at an instant in time
* **save** - Commit data or system state to memory
* **throttle** - Adjust the rate of a process, function, or activity
* **delay** - Stop or hold up an activity or data transmittal
* **substitute** - Replace all or part of the payload
* **sync** - Synchronize a sensor or actuator with other system components
* **mitigate** -  Task the recipient to circumvent a problem without necessarily eliminating the vulnerability or attack point

**Usage Requirements:**

* Each command MUST contain exactly one action. 
* All commands MUST only use actions from this section (either the table or the list) 
* Actions defined external to this section SHALL NOT be used.

#### 3.3.1.2 Target
**_Type: Target (Choice)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **artifact** | Artifact | 1 | An array of bytes representing a file-like object or a link to that object. |
| 2 | **command** | Request-Id | 1 | A reference to a previously issued OpenC2 Command. |
| 3 | **device** | Device | 1 | The properties of a hardware device. |
| 7 | **domain_name** | Domain-Name | 1 | A network domain name. |
| 8 | **email_addr** | Email-Addr | 1 | A single email address. |
| 16 | **features** | Features | 1 | A set of items used with the query action to determine an actuator's capabilities. |
| 10 | **file** | File | 1 | Properties of a file. |
| 11 | **ip_addr** | IP-Addr | 1 | An IP address (either version 4 or version 6). |
| 15 | **ip_connection** | IP-Connection | 1 | A network connection that originates from a source and is addressed to a destination. Source and destination addresses may be either IPv4 or IPv6; both should be the same version |
| 13 | **mac_addr** | MAC-Addr | 1 | A Media Access Control (MAC) address - EUI-48 or EUI-64 |
| 17 | **process** | Process | 1 | Common properties of an instance of a computer program as executed on an operating system. |
| 25 | **properties** | Properties | 1 | Data attribute associated with an actuator |
| 19 | **uri** | URI | 1 | A uniform resource identifier(URI). |
| 1024 | **slpf** | slpf:Target | 1 | **Example**: Targets defined in the Stateless Packet Filter profile |

The following targets are under consideration for use in future versions of the Language Specification. Implementers may use these targets with the understanding that they may not be in future versions of the language.

* directory
* disk
* disk_partition
* email_message
* memory
* software
* user_account
* user_session
* volume
* windows_registry_key
* x509_certificate

**Usage Requirements:**

* The TARGET field in an OpenC2 Command MUST contain exactly one type of target (e.g. ip_addr).

#### 3.3.1.3 Actuator
**_Type: Actuator (Choice)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1024 | **slpf** | slpf:Actuator | 1 | **Example**: Actuator Specifiers defined in the Stateless Packet Filter profile |

#### 3.3.1.4 Command Arguments
**_Type: Args (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **start_time** | Date-Time | 0..1 | The specific date/time to initiate the action  |
| 2 | **stop_time** | Date-Time | 0..1 | The specific date/time to terminate the action |
| 3 | **duration** | Duration | 0..1 | The length of time for an action to be in effect |
| 4 | **response_requested** | Response-Type | 0..1 | The type of response required for the action: `none`, `ack`, `status`, `complete`. |
| 1024 | **slpf** | slpf:Args | 1 | **Example**: Command Arguments defined in the Stateless Packet Filter profile |

**Usage Requirements:**

* When response_requested is not explicitly contained in an OpenC2 Command, a Consumer MUST respond in the same manner as {"response_requested": "complete"}.

### 3.3.2 OpenC2 Response
**_Type: OpenC2-Response (Record)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **status** | Status-Code | 1 | An integer status code |
| 2 | **status_text** | String | 0..1 | A free-form human-readable description of the response status |
| 3 | **strings** | String | 0..* | Generic set of string values |
| 4 | **ints** | Integer | 0..* | Generic set of integer values |
| 5 | **kvps** | KVP | 0..* | Generic set of key:value pairs |
| 6 | **versions** | Version | 0..* | List of OpenC2 language versions supported by this actuator |
| 7 | **profiles** | jadn:Uname | 0..* | List of profiles supported by this actuator |
| 8 | **schema** | jadn:Schema | 0..1 | Syntax of the OpenC2 language elements supported by this actuator |
| 9 | **pairs** | Action-Targets | 0..* | List of targets applicable to each supported action |
| 10 | **rate_limit** | Number | 0..1 | Maximum number of requests per minute supported by design or policy |
| 1024 | **slpf** | slpf:Response | 1 | **Example**: Response types defined in the Stateless Packet Filter profile |

**Example:**

```javascript
{   
    "status": 200,
    "status_text": "All endpoints successfully updated",
    "strings": ["wd-394", "sx-2497"]
}
```

Usage Requirements:

* All Responses MUST contain a status.
* Responses MAY contain status_text and/or results.

#### 3.3.2.1 OpenC2 Response Status Code
**_Type: Status-Code (Enumerated.ID)_**

| ID | Description |
| :--- | :--- |
| 102 | **Processing** - an interim response used to inform the producer that the consumer has accepted the request but has not yet completed it. |
| 200 | **OK** - the request has succeeded. |
| 400 | **Bad Request** - the consumer cannot process the request due to something that is perceived to be a producer error (e.g., malformed request syntax). |
| 401 | **Unauthorized** - the request lacks valid authentication credentials for the target resource or authorization has been refused for the submitted credentials. |
| 403 | **Forbidden** - the consumer understood the request but refuses to authorize it. |
| 404 | **Not Found** - the consumer has not found anything matching the request. |
| 500 | **Internal Error** - the consumer encountered an unexpected condition that prevented it from fulfilling the request. |
| 501 | **Not Implemented** - the consumer does not support the functionality required to fulfill the request. |
| 503 | **Service Unavailable** - the consumer is currently unable to handle the request due to a temporary overloading or maintenance of the consumer. |

## 3.4 Type Definitions
### 3.4.1 Target Types
#### 3.4.1.1 Artifact
**_Type: Artifact (Record)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **mime_type** | String | 0..1 | Permitted values specified in the IANA Media Types registry, RFC 6838 |
| 2 | **payload** | Payload | 0..1 | Choice of literal content or URL |
| 3 | **hashes** | Hashes | 0..1 | Hashes of the payload content |

#### 3.4.1.3 Device
**_Type: Device (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **hostname** | Hostname | 1 | A hostname that can be used to connect to this device over a network |
| 2 | **description** | String | 0..1 | A human-readable description of the purpose, relevance, and/or properties of this device |
| 3 | **device_id** | String | 0..1 | An identifier that refers to this device within an inventory or management system |

#### 3.4.1.4 Domain Name
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **Domain-Name** | String (hostname) | RFC 1034, section 3.5 |

#### 3.4.1.5 Email Address
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **Email-Addr** | String (email) | Email address, RFC 5322, section 3.4.1 |

#### 3.4.1.6 Features
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **Features** | ArrayOf(Feature) | An array of zero to ten names used to query an actuator for its supported capabilities. |

#### 3.4.1.7 File
**_Type: File (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **name** | String | 0..1 | The name of the file as defined in the file system |
| 2 | **path** | String | 0..1 | The absolute path to the location of the file in the file system |
| 3 | **hashes** | Hashes | 0..1 | One or more cryptographic hash codes of the file contents |

#### 3.4.1.8 IP Address
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **IP-Addr** | Binary | 32 bit IPv4 address or 128 bit IPv6 address |

#### 3.4.1.9 IP Connection
**_Type: IP-Connection (Record)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **src_addr** | IP-Addr | 0..1 | ip_addr of source, could be ipv4 or ipv6 - see ip_addr section |
| 2 | **src_port** | Port | 0..1 | source service per RFC 6335 |
| 3 | **dst_addr** | IP-Addr | 0..1 | ip_addr of destination, could be ipv4 or ipv6 - see ip_addr section |
| 4 | **dst_port** | Port | 0..1 | destination service per RFC 6335 |
| 5 | **protocol** | L4-Protocol | 0..1 | layer 4 protocol (e.g., TCP) - see l4_protocol section |

**Usage Requirements:**

* src_addr and dst_addr MUST be the same version (ipv4 or ipv6) if both are present.

#### 3.4.1.10 MAC Address
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **MAC-Addr** | Binary | Media Access Control / Extended Unique Identifier address - EUI-48 or EUI-64. |

#### 3.4.1.11 Process
**_Type: Process (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **pid** | Integer | 0..1 | Process ID of the process |
| 2 | **name** | String | 0..1 | Name of the process |
| 3 | **cwd** | String | 0..1 | Current working directory of the process |
| 4 | **executable** | File | 0..1 | Executable that was executed to start the process |
| 5 | **parent** | Process | 0..1 | Process that spawned this one |
| 6 | **command_line** | String | 0..1 | The full command line invocation used to start this process, including all arguments |

#### 3.4.1.12 Properties
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **Properties** | ArrayOf(String) | A list of names that uniquely identify properties of an actuator. |

#### 3.4.1.13 URI
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **URI** | String | Uniform Resource Identifier |

### 3.4.2 Data Types
#### 3.4.2.1 Request Identifier
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **Request-Id** | Binary | A value of up to 128 bits that uniquely identifies a particular command |

#### 3.4.2.2 Date-Time
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **Date-Time** | Integer | Milliseconds since 00:00:00 UTC, 1 January 1970 |

#### 3.4.2.3 Duration
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **Duration** | Integer | Milliseconds |

#### 3.4.2.4 Hashes
**_Type: Hashes (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **md5** | Binary | 0..1 | MD5 hash as defined in RFC 1321 |
| 2 | **sha1** | Binary | 0..1 | SHA1 hash as defined in RFC 6234 |
| 3 | **sha256** | Binary | 0..1 | SHA256 hash as defined in RFC 6234 |

#### 3.4.2.5 Hostname
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
|  **Hostname** | String | A legal Internet host name as specified in RFC 1123 |

#### 3.4.2.7 L4 Protocol
Value of the protocol (IPv4) or next header (IPv6) field in an IP packet. Any IANA value, RFC 5237

**_Type: L4-Protocol (Enumerated)_**

| ID | Name | Description |
| :--- | :--- | :--- |
| 1 | **icmp** | Internet Control Message Protocol - RFC 792 |
| 6 | **tcp** | Transmission Control Protocol - RFC 793 |
| 17 | **udp** | User Datagram Protocol - RFC 768 |
| 132 | **sctp** | Stream Control Transmission Protocol - RFC 4960 |

#### 3.4.2.8 Payload
**_Type: Payload (Choice)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **bin** | Binary | 1 | Specifies the data contained in the artifact |
| 2 | **url** | URI | 1 | MUST be a valid URL that resolves to the un-encoded content |

#### 3.4.2.9 Port
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **Port** | Integer | Transport Protocol Port Number, RFC 6335 |

#### 3.4.2.10 Feature
Specifies the results to be returned from a query features command.

**_Type: Feature (Enumerated)_**

| ID | Name | Description |
| :--- | :--- | :--- |
| 1 | **versions** | List of OpenC2 Language versions supported by this actuator |
| 2 | **profiles** | List of profiles supported by this actuator |
| 3 | **pairs** | List of supported actions and applicable targets |
| 4 | **rate_limit** | Maximum number of requests per minute supported by design or policy |

#### 3.4.2.11 Response-Type
**_Type: Response-Type (Enumerated)_**

| ID | Name | Description |
| :--- | :--- | :--- |
| 0 | **none** | No response |
| 1 | **ack** | Respond when command received |
| 2 | **status** | Respond with progress toward command completion |
| 3 | **complete** | Respond when all aspects of command completed |

#### 3.4.2.12 Version
| Type Name | Base Type | Description |
| :--- | :--- | :--- |
| **Version** | String | Major.Minor version number |

#### 3.4.2.14 Key-Value Pair
**_Type: KVP (Array)_**

| ID | Type | # | Description |
| :--- | :--- | :--- | :--- |
| 1 | String | 1 | "key": name of this item |
| 2 | String | 1 | "value": string value of this item |

#### 3.4.2.15 Action-Targets Array
**_Type: Action-Targets (Array)_**

| ID | Type | # | Description |
| :--- | :--- | :--- | :--- |
| 1 | Action | 1 | An action supported by this actuator. |
| 2 | Target.* | 1..* | List of targets applicable to this action.  The targets are enumerated values derived from the set of Target types. |

-------

# 4 Required Commands/Responses 
An OpenC2 command consists of an ACTION/TARGET pair and associated SPECIFIERS and ARGUMENTs.  This section enumerates the allowed commands, identify which are required or optional to implement, and present the associated responses.  

An OpenC2 Consumer MUST process an OpenC2 Command where "query" is specified for the ACTION and "features" is specified for the TARGET, hereafter, referred to as a 'query features' command".

Upon processing a 'query features'  command, an OpenC2 Consumer MUST issue an OpenC2 Response to the OpenC2 Producer that issued the OpenC2 Command.

-------

# 5 Conformance
## 5.1 OpenC2 Message Content
A conformant OpenC2 Command 

1. MUST be structured in accordance with Section 3.4.1, and 
2. MUST include exactly one ACTION specified in Section 3.4.1.1.

A conformant OpenC2 Response

1. MUST be structured in accordance with Section 3.4.2, and 
2. MUST include exactly one STATUS specified in Section 3.4.2.1.

## 5.2 OpenC2 Producer
A conformant OpenC2 Producer 

1. MUST issue OpenC2 Commands and process OpenC2 Responses specified in Section 4
2. MUST implement JSON serialization of generated OpenC2 Commands in accordance with RFC 7493

## 5.3 OpenC2 Consumer
A conformant OpenC2 Consumer 

1. MUST process OpenC2 Commands and issue OpenC2 Responses specified in Section 4
2. MUST implement JSON serialization of generated OpenC2 Responses in accordance with RFC 7493

-------

# Annex A. Examples
## A.1 Example 1
This example shows the elements of an OpenC2 Message containing an OpenC2 Command. The content of the message is the de-serialized command structure in whatever format is used by the implementation, independent of the transfer protocol and serialization format used to transport the message.

The request_id in this example is a 64 bit binary value which can be displayed in many ways, including hex:` 'd937 fca9 2b64 4e71'`,  base64url: `'2Tf8qStkTnE'`, and Python byte string - ASCII characters with hex escapes (\xNN) for non-ASCII bytes: `b'\xd97\xfc\xa9+dNq'`.  If OpenC2 producers generate numeric or alphanumeric request_ids, they are still binary values and are limited to 128 bits, e.g.,: hex: '6670 2d31 3932 352d 3337 3632 3864 3663', base64url: 'ZnAtMTkyNS0zNzYyOGQ2Yw', byte string: b'fp-1925-37628d6c'.

The created element is a Date-Time value of milliseconds since the epoch.  The example `1539355895215` may be displayed as` '12 October 2018 14:51:35 UTC'`.

This example, illustrating an internal representation of a message, is non-normative.  Other programming languages (e.g., Java, Javascript, C, Erlang) have different representations of literal values.  There are no interoperability considerations or conformance requirements for how message elements are represented internally within an implementation.  Only the serialized values of the message elements embedded within a protocol is relevant to interoperability.


### A.1.1 Command Message
content-type: 'application/openc2'
msg_type: 'request'
request_id: b'\xd97\xfc\xa9+dNq'
from: 'nocc-3497'
to: ['#filter-devices']
created: 1539355895215
content: {'action': 'query', 'target': {'features': ['versions', 'profiles']}}

### A.1.2 Response Message
The response message contains a status code, a content-type that is normally the same as the request content type, a msg_type of `'response'`, and the response content.  The request_id from the command message, if present, is returned unchanged in the response message.  The "to" element of the response normally echoes the "from" element of the command message, but the "from" element of the response is the actuator's identifier regardless of whether the command was sent to an individual actuator or a group.  The "created" element, if present, contains the creation time of the response.

A responder could potentially return non-openc2 content, such as a PDF report or an HTML document, in response to an openc2 command.  No actuator profiles currently define response content types other than openc2.

status: 200
content-type: 'application/openc2'
msg_type: 'response'
request_id: b'\xd97\xfc\xa9+dNq'
from: 'pf72394'
to: ['nocc-3497']
created: 1539355898000
content: {'status': 200, 'versions': ['1.3'], 'profiles': ['oasis-open.org/openc2/v1.0/ap-slpf']}

## A.2 Example 2
This example is for a transport where the header information is outside the JSON (e.g., HTTPS API) and only body is in JSON.

**Command:**

```
{
    "action": "query",
    "target": {
        "properties": ["battery_percentage"]
    },
    "actuator": {
        "esm": {
            "asset_id": "TGEadsasd"
        }
    }:
}
```

**Response:**

```
{
    "status": 200,
    "kvps": [["battery_percentage", "0.577216"]]
}
```

## A.3 Example 3
**Command:**

```
{
  "action": "query",
  "target": {
    "features": ["versions", "profiles"]
  }
}
```

**Response:**

```
{
  "status_text": "ACME Corp Internet Toaster",
  "versions": ["1.0"],
  "profiles": []
}
```

-------

# Annex C. Acronyms

| Acroynm | Definition |
| :--- | :--- |
API | Application Programming Interface
CBOR | Concise Binary Object Representation
CoAP | Constrained Application Protocol
DNS | Domain Name Server
HTTP | Hyper Text Transfer Protocol
IACD | Iintegrated Adaptive Cyber Defense
IANA | Internet Assigned Numbers Authority 
ICMP | Internet Control Message Protocol
IP | Internet Protocol
IPR | Intellectual Property Rights
JSON | Java Script Notation
KMIP | Key Management Interface Protocol
KVP | Key Value Pairs
MAC | Media Access Control
MD5 | Message Digest
MIME | Multipurpose Internet Mail Extensions 
MQTT | Message Queuing Telemetry Transfer 
NSID | Namespace Identifier
OASIS | Organization for the Advancement of Structured Information Standards
OpenC2 | Open  Command and Control
OpenDXL | Open Data eXchange Layer
RFC | Request for Comment
SCTP | Straem Control Transmission Protocol
SHA | Security Hash Algorithm
SLPF | StateLess Packet Filtering
STIX | Structured Threat Intel eXchange
TC | Technical Committee
TCP | Tranmission Control Protocol
TLV | Type Length Value
UDP | User Datagram Control Protocol
Uname | Unique Name
URI | Uniform Resource Identifier
XML | eXtensibel Markup Language

-------

# Annex C. Revision History
| Revision | Date | Editor | Changes Made |
| :--- | :--- | :--- | :--- |
| v1.0-wd01 | 10/31/2017 | Romano, Sparrell | Initial working draft |
| v1.0-csd01 | 11/14/2017 | Romano, Sparrell | approved wd01 |
| v1.0-wd02 | 01/12/2018 | Romano, Sparrell | csd01 ballot comments<br>targets |
| v1.0-wd03 | 01/31/2018 | Romano, Sparrell | wd02 review comments |
| v1.0-csd02 | 02/14/2018 | Romano, Sparrell | approved wd03 |
| v1.0-wd04 | 03/02/2018 | Romano, Sparrell | Property tables<br>threads (cmd/resp) from use cases<br>previous comments |
| v1.0-wd05 | 03/21/2018 | Romano, Sparrell | wd04 review comments |
| v1.0-csd03 | 04/03/2018 | Romano, Sparrell | approved wd05 |
| v1.0-wd06 | 05/15/2018 | Romano, Sparrell | Finalizing message structure<br>message=header+body<br>Review comments<br>Using word ‘arguments’ instead of ‘options’ |
| v1.0-csd04 | 5/31/2018 | Romano, Sparrell | approved wd06 |
| v1.0-wd07 | 7/11/2018 | Romano, Sparrell | Continued refinement of details<br>Review comments<br>Moved some actions and targets to reserved lists |
| v1.0-wd08 | 10/05/2018 | Romano, Sparrell | Continued refinement of details<br>Review comments |
| v1.0-wd09 | 10/17/2018 | Romano, Sparrell | Additional review comments to create wd09 for CSD approval and release for public review. |

-------

# Annex D. Acknowledgments
The following individuals have participated in the creation of this specification and are gratefully acknowledged:

**OpenC2 TC Members:**

| First Name | Last Name | Company |
| :--- | :--- | :--- |
Philippe | Alcoy | Arbor Networks
Darren | Anstee | Arbor Networks
Michelle | Barry | AT&T
Brian | Berliner | Symantec Corp.
Adam | Bradbury | EclecticIQ
Joe | Brule | National Security Agency
Michael | Butt | NC4
Toby | Considine | University of North Carolina at Chapel Hill
Trey | Darley | New Context Services Inc.
David | Darnell | North American Energy Standards Board
Sudeep | Das | McAfee
Andrea | De Bernardi | Moviri SPA
Blake | Essing | AT&T
Alex | Everett | University of North Carolina at Chapel Hill
Joyce | Fai | National Security Agency
Travis | Farral | Anomali
David | Girard | Trend Micro
Andy | Gray | ForeScout
John-Mark | Gurney | New Context Services Inc.
Stefan | Hagen | Individual
David | Hamilton | AT&T
Nick | Humphrey | Huntsman Security
Christian | Hunt | New Context Services Inc.
April | Jackson | G2
Sridhar | Jayanthi | Individual
Bret | Jordan | Symantec Corp.
Jason | Keirstead | IBM
David | Kemp | National Security Agency
David | Lemire | G2
Jason | Liu | Northrop Grumman
Radu | Marian | Bank of America
Danny | Martinez | G2
Lisa | Mathews | National Security Agency
James | Meck | FireEye Inc.
Efrain | Ortiz | Symantec Corp.
Paul | Patrick | FireEye Inc.
Michael | Pepin | NC4
Nirmal | Rajarathnam | ForeScout
Chris | Ricard | Financial Services Information Sharing and Analysis Center (FS-ISAC)
Daniel | Riedel | New Context Services Inc.
Jason | Romano | National Security Agency
Philip | Royer | Splunk Inc.
Thomas | Schreck | Siemens AG
Duane | Skeen | Northrop Grumman
Duncan | Sparrell | sFractal Consulting LLC
Michael | Stair | AT&T
Andrew | Storms | New Context Services Inc.
Gerald | Stueve | Fornetix
Rodney | Sullivan | NCI Agency
Allan | Thomson | LookingGlass
Bill | Trost | AT&T
Raymon | van der Velde | EclecticIQ
Jyoti | Verma | Cisco Systems
David | Waltermire | NIST
Jason | Webb | LookingGlass
Sean | Welsh | AT&T
Charles | White | Fornetix
Sounil | Yu | Bank of America

