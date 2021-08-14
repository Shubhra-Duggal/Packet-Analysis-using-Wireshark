# Packet-Analysis-using-Wireshark

## Introduction
Wireshark is a packet-sniffing application. It is GUI-based. Wireshark is opensource software and supports all major operating systems- Windows, Mac OS X and Linux-based platforms. 
The normal traffic on the network has to be analysed to be able to recognise if there is a problem in traffic flow. For example: If one has to solve problems related to working of DHCP, then they need to know ehat the DHCP working traffic is like on a network.   

On occasions, Wireshark may not be able to keep up with a busy link. It is a GUI tool and calls dumpcap, which is a command line tool. Dumpcap captures the packets and stores them as a disk file, while Wireshark reads and presents them. There are various high performance capture appliance offered which can be used as an alternative.

## Install Wireshark
The demonstration has been performed on a Linux environment- Ubuntu 20.04.2.0 virtual machine running on VMWare Fusion for Mac OS. The setup for the environment of operating system has not been detailed.

Wireshark has been [setup on the machine](installation_wireshark.md) and the interface ens33 is [identified as the interface](identify_interface.md) on which we capture packets.

![Screenshot 2021-08-14 at 12 25 40 PM](https://user-images.githubusercontent.com/42912140/129437991-51637427-8c1e-4d33-acf7-2c02ba0ae3fd.png)

## Conversations
Sometimes we need identify the specific packets. This can be done by identifying the IP addresses of the source and destination. Even the conversation between specific nodes can also be filtered out. [Conversation](conversations_wireshark.md) can be accessed from the Statistics menu.

## Capture Location
The [selection of location](location_wireshark.md) to capture packets for analysis depends on:
* Issue being investigated
* Usefulness of the packets captured depending upon the ability to capture packets
* Technical obstacles faced during capture

## Filters
### Capture Filters
Capture filters are used to reduce the amount of traffic saved during a packet capture. 
In practice, capture filters should be used sparingly, if used at all, to help make sure 
that no packets that are important for an analysis are inadvertently missed because they 
fall outside the capture filter parameters. Remember that you can always filter out unwanted
traffic from a capture, but you can't do anything about missed packets once the capture is finished. 
If you're unsure about a capture, perform the capture again with a more generous capture filter or none at all.

One scenario where a capture filter is appropriate is when you want to let a capture run for a long 
period of time. Then, you should filter out as much extraneous traffic as possible to keep capture
file sizes under control. However, take care to make sure the capture filter you apply doesn't exclude 
any traffic that may be useful for the analysis.
It's usually a good idea to do some trial captures when using capture filters to verify that the filter 
is working as desired before doing the official capture that you want to keep.

### Display Filters







## Protocols

### ICMP
The [Internet Control Message Protocol](icmp.md) (ICMP) is used to send error messages indicating that a requested service is not available, or if device could not be reached. It is a control protocol. Although it is transported as IP datagrams, it does not carry the application data. Instead, it carries the information about the status of the network itself.

### IP

### TCP

## Troubleshooting
