<!-- Generated from schema\oc2ls-wd13.jadn, Thu Apr  4 17:48:54 2019-->
## Schema
| . | . |
| ---: | :--- |
| **title:** | OpenC2 Language Objects |
| **module:** | oasis-open.org/openc2/oc2ls/v1.0 |
| **patch:** | 0-csdpr02 |
| **description:** | Datatypes that define the content of OpenC2 commands and responses. |
| **exports:** | OpenC2-Command, OpenC2-Response, Message-Type, Status-Code, Date-Time |
| **imports:** | **slpf**:&nbsp;oasis-open.org/openc2/oc2slpf/v1.0 |

**_Type: Message (Array)_**

| ID | Type | # | Description |
| ---: | :--- | ---: | :--- |
| 1 | Message-Type | 1 | msg_type:: message element |
| 2 | String | 1 | content_type:: message element |
| 3 | Null | 1 | content:: message element |
| 4 | Status-Code | 0..1 | status:: message element |
| 5 | String | 0..1 | request_id:: message element |
| 6 | String | 0..* | to:: message element |
| 7 | String | 0..1 | from:: message element |
| 8 | Date-Time | 0..1 | created:: message element |

**_Type: OpenC2-Command (Record)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **action** | Action | 1 | The task or activity to be performed (i.e., the 'verb'). |
| 2 | **target** | Target | 1 | The object of the Action. The Action is performed on the Target. |
| 3 | **args** | Args | 0..1 | Additional information that applies to the Command. |
| 4 | **actuator** | Actuator | 0..1 | The subject of the Action. The Actuator executes the Action on the Target. |
| 5 | **command_id** | String | 0..1 | An identifier of this Command. |

**_Type: Action (Enumerated)_**

| ID | Name | Description |
| ---: | :--- | :--- |
| 1 | **scan** | Systematic examination of some aspect of the entity or its environment. |
| 2 | **locate** | Find an object physically, logically, functionally, or by organization. |
| 3 | **query** | Initiate a request for information. |
| 6 | **deny** | Prevent a certain event or action from completion, such as preventing a flow from reaching a destination or preventing access. |
| 7 | **contain** | Isolate a file, process, or entity so that it cannot modify or access assets or processes. |
| 8 | **allow** | Permit access to or execution of a Target. |
| 9 | **start** | Initiate a process, application, system, or activity. |
| 10 | **stop** | Halt a system or end an activity. |
| 11 | **restart** | Stop then start a system or an activity. |
| 14 | **cancel** | Invalidate a previously issued Action. |
| 15 | **set** | Change a value, configuration, or state of a managed entity. |
| 16 | **update** | Instruct a component to retrieve, install, process, and operate in accordance with a software update, reconfiguration, or other update. |
| 18 | **redirect** | Change the flow of traffic to a destination other than its original destination. |
| 19 | **create** | Add a new entity of a known type (e.g., data, files, directories). |
| 20 | **delete** | Remove an entity (e.g., data, files, flows). |
| 22 | **detonate** | Execute and observe the behavior of a Target (e.g., file, hyperlink) in an isolated environment. |
| 23 | **restore** | Return a system to a previously known state. |
| 28 | **copy** | Duplicate an object, file, data flow, or artifact. |
| 30 | **investigate** | Task the recipient to aggregate and report information as it pertains to a security event or incident. |
| 32 | **remediate** | Task the recipient to eliminate a vulnerability or attack point. |

**_Type: Target (Choice)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **artifact** | Artifact | 1 | An array of bytes representing a file-like object or a link to that object. |
| 2 | **command** | String | 1 | A reference to a previously issued Command. |
| 3 | **device** | Device | 1 | The properties of a hardware device. |
| 7 | **domain_name** | Domain-Name | 1 | A network domain name. |
| 8 | **email_addr** | Email-Addr | 1 | A single email address. |
| 9 | **features** | Features | 1 | A set of items used with the query Action to determine an Actuator's capabilities. |
| 10 | **file** | File | 1 | Properties of a file. |
| 13 | **ipv4_net** | IPv4-Net | 1 | An IPv4 address range including CIDR prefix length. |
| 14 | **ipv6_net** | IPv6-Net | 1 | An IPv6 address range including prefix length. |
| 15 | **ipv4_connection** | IPv4-Connection | 1 | A 5-tuple of source and destination IPv4 address ranges, source and destination ports, and protocol |
| 16 | **ipv6_connection** | IPv6-Connection | 1 | A 5-tuple of source and destination IPv6 address ranges, source and destination ports, and protocol |
| 17 | **mac_addr** | MAC-Addr | 1 | A Media Access Control (MAC) address - EUI-48 or EUI-64 as defined in [[EUI]](#eui) |
| 18 | **process** | Process | 1 | Common properties of an instance of a computer program as executed on an operating system. |
| 25 | **properties** | Properties | 1 | Data attribute associated with an Actuator |
| 19 | **uri** | URI | 1 | A uniform resource identifier (URI). |

**_Type: Actuator (Choice)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1024 | **slpf** | slpf:Actuator | 1 | **Example**: Actuator Specifiers defined in the Stateless Packet Filtering Profile |

**_Type: Args (Map)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **start_time** | Date-Time | 0..1 | The specific date/time to initiate the Action |
| 2 | **stop_time** | Date-Time | 0..1 | The specific date/time to terminate the Action |
| 3 | **duration** | Duration | 0..1 | The length of time for an Action to be in effect |
| 4 | **response_requested** | Response-Type | 0..1 | The type of Response required for the Action: `none`, `ack`, `status`, `complete`. |

**_Type: OpenC2-Response (Map)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **status** | Status-Code | 1 | An integer status code |
| 2 | **status_text** | String | 0..1 | A free-form human-readable description of the Response status |
| 3 | **strings** | String | 0..* | Generic set of string values |
| 4 | **ints** | Integer | 0..* | Generic set of integer values |
| 5 | **results** | MapOf(String, Any) | 0..* | Generic Map of key:value pairs (keys are strings, and values are any valid JSON value). A JSON value can be an object, array, number, string, true, false, or null, as defined by ECMA-404. |
| 6 | **versions** | Version | 0..* | List of OpenC2 language versions supported by this Actuator |
| 7 | **profiles** | ArrayOf(Nsid) | 0..1 | List of profiles supported by this Actuator |
| 9 | **pairs** | Action-Targets | 0..* | List of targets applicable to each supported Action |
| 10 | **rate_limit** | Number | 0..1 | Maximum number of requests per minute supported by design or policy |

**_Type: Status-Code (Enumerated.ID)_**

| ID | Description |
| ---: | :--- |
| 102 | Processing:: an interim Response used to inform the Producer that the Consumer has accepted the request but has not yet completed it. |
| 200 | OK:: the request has succeeded. |
| 400 | Bad Request:: the Consumer cannot process the request due to something that is perceived to be a Producer error (e.g., malformed request syntax). |
| 401 | Unauthorized:: the request lacks valid authentication credentials for the target resource or authorization has been refused for the submitted credentials. |
| 403 | Forbidden:: the Consumer understood the request but refuses to authorize it. |
| 404 | Not Found:: the Consumer has not found anything matching the request. |
| 500 | Internal Error:: the Consumer encountered an unexpected condition that prevented it from fulfilling the request. |
| 501 | Not Implemented:: the Consumer does not support the functionality required to fulfill the request. |
| 503 | Service Unavailable:: the Consumer is currently unable to handle the request due to a temporary overloading or maintenance of the Consumer. |

**_Type: Artifact (Record)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **mime_type** | String | 0..1 | Permitted values specified in the IANA Media Types registry, [[RFC6838]](#rfc6838) |
| 2 | **payload** | Payload | 0..1 | Choice of literal content or URL |
| 3 | **hashes** | Hashes | 0..1 | Hashes of the payload content |

**_Type: Device (Map)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **hostname** | Hostname | 1 | A hostname that can be used to connect to this device over a network |
| 2 | **description** | String | 0..1 | A human-readable description of the purpose, relevance, and/or properties of this device |
| 3 | **device_id** | String | 0..1 | An identifier that refers to this device within an inventory or management system |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Domain-Name** | String (hostname) | [[RFC1034]](#rfc1034), Section 3.5 |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Email-Addr** | String (email) | Email address, [[RFC5322]](#rfc5322), Section 3.4.1 |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Features** | ArrayOf(Feature) [0..10] | An array of zero to ten names used to query an Actuator for its supported capabilities. |

**_Type: File (Map)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **name** | String | 0..1 | The name of the file as defined in the file system |
| 2 | **path** | String | 0..1 | The absolute path to the location of the file in the file system |
| 3 | **hashes** | Hashes | 0..1 | One or more cryptographic hash codes of the file contents |

**_Type: IPv4-Net (Array /ipv4-net)_**

| ID | Type | # | Description |
| ---: | :--- | ---: | :--- |
| 1 | IPv4-Addr | 1 | ipv4_addr:: as defined in [[RFC0791]](#rfc0791) |
| 2 | Integer | 0..1 | prefix_length:: If omitted, refers to a single host address. |

**_Type: IPv4-Connection (Record)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **src_addr** | IPv4-Net | 0..1 | IPv4 source address range |
| 2 | **src_port** | Port | 0..1 | source service per [[RFC6335]](#rfc6335) |
| 3 | **dst_addr** | IPv4-Net | 0..1 | IPv4 destination address range |
| 4 | **dst_port** | Port | 0..1 | destination service per [[RFC6335]](#rfc6335) |
| 5 | **protocol** | L4-Protocol | 0..1 | layer 4 protocol (e.g., TCP) - see [Section 3.4.2.9](#3429-l4-protocol) |

**_Type: IPv6-Net (Array /ipv6-net)_**

| ID | Type | # | Description |
| ---: | :--- | ---: | :--- |
| 1 | IPv6-Addr | 1 | ipv6_addr:: as defined in [[RFC8200]](#rfc8200) |
| 2 | Integer | 0..1 | prefix_length:: If omitted, refers to a single host address. |

**_Type: IPv6-Connection (Record)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **src_addr** | IPv6-Net | 0..1 | IPv6 source address range |
| 2 | **src_port** | Port | 0..1 | source service per [[RFC6335]](#rfc6335) |
| 3 | **dst_addr** | IPv6-Net | 0..1 | IPv6 destination address range |
| 4 | **dst_port** | Port | 0..1 | destination service per [[RFC6335]](#rfc6335) |
| 5 | **protocol** | L4-Protocol | 0..1 | layer 4 protocol (e.g., TCP) - [Section 3.4.2.9](#3429-l4-protocol) |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **MAC-Addr** | Binary (eui) | Media Access Control / Extended Unique Identifier address - EUI-48 or EUI-64 as defined in [[EUI]](#eui). |

**_Type: Process (Map)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **pid** | Integer | 0..1 | Process ID of the process |
| 2 | **name** | String | 0..1 | Name of the process |
| 3 | **cwd** | String | 0..1 | Current working directory of the process |
| 4 | **executable** | File | 0..1 | Executable that was executed to start the process |
| 5 | **parent** | Process | 0..1 | Process that spawned this one |
| 6 | **command_line** | String | 0..1 | The full command line invocation used to start this process, including all arguments |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Properties** | ArrayOf(String) | A list of names that uniquely identify properties of an Actuator. |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **URI** | String (uri) | Uniform Resource Identifier |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Action-Targets** | MapOf(Action, Targets) | Map of each action supported by this actuator to the list of targets applicable to that action. |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Targets** | ArrayOf(Target.Enum) [1..*] | List of Target fields |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Date-Time** | Integer | Date and Time |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Duration** | Integer | A length of time |

**_Type: Feature (Enumerated)_**

| ID | Name | Description |
| ---: | :--- | :--- |
| 1 | **versions** | List of OpenC2 Language versions supported by this Actuator |
| 2 | **profiles** | List of profiles supported by this Actuator |
| 3 | **pairs** | List of supported Actions and applicable Targets |
| 4 | **rate_limit** | Maximum number of requests per minute supported by design or policy |

**_Type: Hashes (Map)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **md5** | Binary /x | 0..1 | MD5 hash as defined in [[RFC1321]](#rfc1321) |
| 2 | **sha1** | Binary /x | 0..1 | SHA1 hash as defined in [[RFC6234]](#rfc6234) |
| 3 | **sha256** | Binary /x | 0..1 | SHA256 hash as defined in [[RFC6234]](#rfc6234) |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Hostname** | String (hostname) | Internet host name as specified in [[RFC1123]](#rfc1123) |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **IPv4-Addr** | Binary /ipv4-addr | 32 bit IPv4 address as defined in [[RFC0791]](#rfc0791) |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **IPv6-Addr** | Binary /ipv6-addr | 128 bit IPv6 address as defined in [[RFC8200]](#rfc8200) |

**_Type: L4-Protocol (Enumerated)_**

| ID | Name | Description |
| ---: | :--- | :--- |
| 1 | **icmp** | Internet Control Message Protocol - [[RFC0792]](#rfc0792) |
| 6 | **tcp** | Transmission Control Protocol - [[RFC0793]](#rfc0793) |
| 17 | **udp** | User Datagram Protocol - [[RFC0768]](#rfc0768) |
| 132 | **sctp** | Stream Control Transmission Protocol - [[RFC4960]](#rfc4960) |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Nsid** | String [1..16] | A short identifier that refers to a namespace. |

**_Type: Payload (Choice)_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **bin** | Binary | 1 | Specifies the data contained in the artifact |
| 2 | **url** | URI | 1 | MUST be a valid URL that resolves to the un-encoded content |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Port** | Integer [0..65535] | Transport Protocol Port Number, [[RFC6335]](#rfc6335) |

**_Type: Response-Type (Enumerated)_**

| ID | Name | Description |
| ---: | :--- | :--- |
| 0 | **none** | No response |
| 1 | **ack** | Respond when Command received |
| 2 | **status** | Respond with progress toward Command completion |
| 3 | **complete** | Respond when all aspects of Command completed |


| Type Name | Type Definition | Description |
| :--- | :--- | :--- |
| **Version** | String | Major.Minor version number |
