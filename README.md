# Packet-Analysis-using-Wireshark

## Introduction
Wireshark is a packet-sniffing application. It is GUI-based. Wireshark is opensource software and supports all major operating systems- Windows, Mac OS X and Linux-based platforms. 
The normal traffic on the network has to be analysed to be able to recognise if there is a problem in traffic flow. For example: If one has to solve problems related to working of DHCP, then they need to know ehat the DHCP working traffic is like on a network.

## Install Wireshark
The demonstration has been performed on a Linux environment- Ubuntu 20.04.2.0 virtual machine running on VMWare Fusion for Mac OS. The setup for the environment of operating system has not been detailed.

Wireshark has been [setup on the machine](installation_wireshark.md) and the interface ens33 is [identified as the interface](identify_interface.md) on which we capture packets.

![Screenshot 2021-08-14 at 12 25 40 PM](https://user-images.githubusercontent.com/42912140/129437991-51637427-8c1e-4d33-acf7-2c02ba0ae3fd.png)

## Conversations
Sometimes we need identify the specific packets. This can be done by identifying the IP addresses of the source and destination. Even the conversation between specific nodes can also be filtered out. [Conversation](conversations_wireshark.md) can be accessed from the Statistics menu.

## Filters







## Protocols

### IP

### TCP

## Troubleshooting
