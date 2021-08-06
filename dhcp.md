# Dynamic Host Configuration Protocol

## Packet Structure

* OpCode: Recognises packet as request/reply
* Hardware Type
* Hardware Length
* Hops: It is used by relay agents to find DHCP server
* Transaction ID: Random number for sequences
* Seconds Elapsed: since the first requent made
* Flags: Traffic that can be accepted- broadcast, unicast etc.
* Client IP Addresses: Derived from our ip address
* Our IP Address: ip address offered by DHCP server
* Server IP Address: DHCP server's ip address
* Gateway IP Address: Default gateway's address
* Client Hardware Address: Client's MAC address
* Server Host Name
* Boot File
* Options

## Address Assignment

1. Discover  
The source address is 0.0.0.0, because the client does not yet have the ip address. 
255.255.255.255 on port 68 is the destination address, which is a network independent broadcast address.
The device does not know the address of DHCP server. 
DHCP relies of UDP at transport layer because of high speed and DHCP even has reliability measures.
* DHCP Message Type
* Client Identifier
* Requested IP Address
* Parametre Request List
2. Offer

3. Request

4. Acknowledgement
DHCP server sends an acknowledgment packets for the requested ip address to the client.



Refer: BOOTP

## 
