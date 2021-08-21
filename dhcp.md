# Dynamic Host Configuration Protocol

## Structure
![Screenshot 2021-08-22 at 3 41 44 AM](https://user-images.githubusercontent.com/42912140/130336065-d8063d21-ca17-49a9-9ef6-0186bc8a4d52.png)


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

![Screenshot 2021-08-22 at 3 43 06 AM](https://user-images.githubusercontent.com/42912140/130336089-79493fac-a34e-4f76-aaa5-ff6c067a5843.png)


1. Discover  

![Screenshot 2021-08-22 at 3 44 26 AM](https://user-images.githubusercontent.com/42912140/130336252-7f9e3f3a-2e8e-4d31-8bf3-e7dabc14a995.png).   

The source address is 0.0.0.0, because the client does not yet have the ip address. 
255.255.255.255 on port 68 is the destination address, which is a network independent broadcast address.
The device does not know the address of DHCP server. 
DHCP relies of UDP at transport layer because of high speed and DHCP even has reliability measures.
* DHCP Message Type
* Client Identifier
* Requested IP Address
* Parametre Request List


2. Offer
![Screenshot 2021-08-22 at 3 44 58 AM](https://user-images.githubusercontent.com/42912140/130336258-659cbaea-15d4-4209-a5d8-994fd9eb02c1.png).   



3. Request
![Screenshot 2021-08-22 at 3 45 08 AM](https://user-images.githubusercontent.com/42912140/130336260-a103aaf6-03f9-40b6-99af-a035ce10c15d.png).   



4. Acknowledgement
![Screenshot 2021-08-22 at 3 51 36 AM](https://user-images.githubusercontent.com/42912140/130336261-e4ba351a-04c8-4e7d-9118-9f8c53cb0809.png).  

DHCP server sends an acknowledgment packets for the requested ip address to the client.



Refer: BOOTP

## 
