# Domain Name System

## Packet Structure

![packet_structure_dns](https://user-images.githubusercontent.com/42912140/128457872-75148cef-584e-4f6f-820a-6de52e01e649.png)

* DNS ID Number: Associates DNS queries with DNS responses.
* OpCode: Type of query.
* Authoritative Answers (AA): Response is from a name server with authority over the domain.
* Truncation (TC): Response was truncated because it was too large to fit within the packet.
* Recursion Desired (RD): When set, the DNS client requests a recursive query if the target name server does not contain the information requested.
* Recursion Available (RA): If set, in a response, the name server supports recursive queries.
* Reserved (Z): Set as all zeros.
* Response Code (RCode): In DNS responses, indicates the presence of errors.
* Question Count: Number of entries in the Questions section. 
* Answer Count: Number of entries in the Answers section.
* Name Server Count: Number of name server resource records in the Authority section.
* Additional Records Count: Number of other resource records in the Additional Information section.
* Questions section: Variable-sized. Contains one or more queries for information to be sent to the DNS server.
* Answers section: Variable-sized. Carries one or more resource records that answer queries.
* Authority section: Variable-sized. Contains resource records that point to authoritative name servers.
* Additional Information: Variable-sized. Contains resource records that hold additional information.

![packet_dns](https://user-images.githubusercontent.com/42912140/128458015-104a8cbe-1ce2-4c4a-9ab4-9df497f66a93.png)







