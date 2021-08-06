# Packet-Analysis-using-Wireshark

## Introduction
Wireshark is a packet-sniffing application. It is GUI-based. Wireshark is opensource software and supports all major operating systems- Windows, Mac OS X and Linux-based platforms. 
The normal traffic on the network has to be analysed to be able to recognise if there is a problem in traffic flow. For example: If one has to solve problems related to working of DHCP, then they need to know ehat the DHCP working traffic is like on a network.
There would be 3 panes displayed- packet list, packet details and packet bytes. Even the preferences can be set:

1. User Interface: Data presentation on Wireshark
2. Capture: The interface where the packets are captured, promiscuous mode, etc.
3. Printing: Format for printing data
4. Name Resolution: Resolution of addresses to readable form
5. Statistics: Configurable options
6. Protocols: Capture and display specific packets

## Filters

### Capture Filters

![Capture options](/Images/capture_filter_input.png)

You can also save complex and frequently used filters for future use.
![user-defined_filters](/Images/user-defined_filters.png)

### Berkeley Packet Filter (BPF)
The filter created is called an expression. We have the following list of qualifiers and corresponding primitives:

| Qualifier | Description | Example |
| --------- | ----------- | ------- |
| Type | ID name or number | host, net, port |
| Dir | Transfer direction | src, dst |
| Proto | Match to protocol | ether, ip, tcp, udp, http, ftp |

Logical operators as the following can also be added:
| Operator | . |
| ------- | - |
| AND | && |
| OR | \| \| |
| NOT | ! |
| EQUAL TP | == |
| NOT EQUAL TO | != |
| GREATER THAN EQUAL TO | >= |

### Capture vs Display Filter
Display filter shows only the packet without losing all the data in the capture file. 

![Display filter pane](/Images/display_filter_pane.png)

## Protocol-wise Analysis

* [Dynamic Host Configuration Protocol](/dhcp.md): It is responsible for dynamically allocating ip addresses to the devices on the network.
* [Domain Name System](/dns.md): Maps domain names to ip addresses
* [Address Resolution Protocol](/arp.md): It resolves the ip address to corresponding MAC address.
* Hypertext Transfer Protocol: It connects web browsers to web servers tpo view web pages
