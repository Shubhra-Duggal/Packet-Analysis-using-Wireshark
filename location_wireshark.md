# Location Wireshark

The assumption is that the communication occurs between a server and a client(user). 

## Capture Locations
### Client Location
The client's machine can be used to verify the problem reported. There is a lot less traffic here and makes the captured files smaller and filtering easier. You can:
* Ensure ARP and DNS are working
* Analyse the login and authentication process
* Calculate the round trip time from client to server
* Verify the TCP session setup handshake
* Determine if there is packet loss, retransmission or out of order packets


### Server Location
It can be that packet capture on client side is not practical, then it can be done on server side. Capture filter have to be applied here to limit file size. Similar metrics can be measured here.
When we have to evaluate the server side response time, then also packet capture should happen at server side, to detect any delay in server-to-database interactions.



### Mid-Network Location
The source of trouble has to be narrowed down, hence, packets have to be captured at numerous points- core switch, router interface, firewalls. 

## Altered Packets
There are several network devices that can alter the packet between server and client, therefore packets have to captured on either side of the device to pinpoint the trouble.

### Routers and Gateways
They can be configured for Network Address Translation (NAT). The public IP address of the network is used to communication. It replaces the private address of the client.
The port numbers can also be translated and is used to support multiple sessions, called Port Address Translation (PAT). The conversation between client and server will constitute different IP addresses and port numbers.

### Proxy Servers and Firewalls
Devices such as these can act as an intermediary between clients wanting to use resources 
from other (usually external) servers. These devices are most typically deployed between 
users inside a company and outside (web) services accessed via the Internet. These devices 
are employed for their security capabilities, allowing administrative control over what can 
be accessed and the type of data content that can be relayed between the two networks, malware 
scanning, and so on. From a packet analysis standpoint, you should be aware that in addition 
to performing a NAT/PAT function, some implementations of these devices may actually terminate 
a user session on one side and initiate a completely different session between the device and 
the outside host on the other side, on behalf of the user, such that the TCP handshake and session parameters,
IP addresses and port numbers, and packet sizes can all differ on either side.


### IP Tunnels using Generic Routing Encapsulation
These are used to connect two IP networks that don't otherwise have a native routing path 
to each other. The original packets are encapsulated inside packets with different
IP addresses appropriate for the network media that they will traverse. The most common 
use of IP tunneling is to connect private corporate networks together through public 
Internet connections or to connect Internet Protocol Version 6 (IPv6) networks together 
over traditional IPv4 network paths. IP tunnels can be configured between routers and high-end switches.

## Remote Capture
If you're capturing from a user location and cannot or do not wish to install Wireshark on 
the user's machine or you're capturing at another location in the network, you have two options 
to obtain a copy of the packets traversing the network: Test Access Ports or switch port mirroring.


### Test Access Port (TAP)
A Test Access Port (TAP) is a device that copies all the packets flowing through it to one or more monitor ports. 
A station with Wireshark installed on it can be connected to one of the monitor ports to capture the packets.
You should select an aggregating TAP that supports the link speed of the network ports being analyzed 
(usually 100 Mbps or 1 Gbps) and that will copy and combine the packets flowing in both directions 
(transmit data from the user's workstation and receive data from the network); the aggregating TAP funnels 
the traffic to a single connection (transmit to the Wireshark station) so that you can capture the traffic in 
both directions with a single network interface on the Wireshark station. Be aware that since you're copying 
packets from two directions into one pipe to the Wireshark station, it is possible to oversubscribe the monitor 
port if traffic rates are extremely high. If this happens, the excess packets will be dropped. Oversubscription 
usually isn't a concern at user workstations, but it could be for switch trunks or other high traffic areas.
The following figure illustrates how a TAP is inserted between a user workstation and that workstation's switch 
port, and how a Wireshark workstation is attached to capture packets:


### Switch Port Mirroring
Switch port mirroring, also known as a Switched Port Analyzer (SPAN) feature or spanning a port, is the practice 
of configuring a network switch to perform the same function as a TAP: to make a copy of the packets flowing in 
and out of a specified port and send them to an otherwise unused monitor port where a Wireshark station is attached 
to capture the packets.
The advantage of using port mirroring is that no connections need to be broken to insert a TAP. The monitor port 
can be easily configured by a switch administrator and just as easily disabled.
The potential issues with this option include the fact that not all switches
support port mirroring, and there is some evidence to suggest that using this
feature can affect the performance of the switch, at least for the port being monitored. The possibility of
oversubscribing the monitor port from excessive transmit plus receiving traffic levels also exists for port mirroring, 
as is the case when using a TAP, and this is likely when monitoring switch trunks to other switches, as these will be 
carrying traffic for multiple users.
The following diagram is a simple illustration of a port mirroring scenario on a switch. The packets to and from the 
workstation port are copied to the port where the Wireshark station is connected.

