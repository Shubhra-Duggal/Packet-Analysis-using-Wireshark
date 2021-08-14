# Transmission Control Protocol

## Structure
The TCP header contents and length can vary depending on options that may be in use, but in its simplest implementation it consists of:
• Source port and Destination port: These are well-known and registered ports are used (on servers) to access standard application services such as HTTP, FTP, SMTP, databases, and so on. Port numbers assigned to client/user sessions are usually in a higher number range and assigned sequentially.
• Sequence number: This is a number that represents the first octet in any given segment. Sequence numbers are initialized at the beginning of new sessions as a random number, and then incremented as data bytes are sent.
• Acknowledgment number: When the ACK flag bit is set, this field contains the next sequence number expected from the sender, which in turn acknowledges receipt of all the bytes received up to that point.
• Flags: These bits are used to control connection setups, terminations, and flow control mechanisms.
• Window size: This field indicates the current size of the buffer on this host used to store received data until it can be handed off to the receiving application. This information enables the sending host to adjust data flow rates in case of network or host congestion.

## TCP Flags

![Screenshot 2021-08-14 at 5 42 15 PM](https://user-images.githubusercontent.com/42912140/129445952-bc820c5b-b049-4e62-b4a0-cea7692f55f1.png)


## TCP Options
The TCP also supports a number of additional options, several of which are in common use in modern networks that you should be aware of. The snippet of a TCP header illustrated in the following screenshot depicts several of the most popular options:

The TCP options highlighted in the preceding screenshot include:
• Maximum Segment Size: This option allows you to specify of the number of bytes that can follow the TCP header. This option exists to allow adjustment to accommodate VLAN tagging or Multiprotocol Label Switching (MPLS).
• Window Scale: This option overcomes the inability of the Window Size field in a standard TCP header to specify a window size greater than 65,535 bytes. Window scaling allows you to specify a factor to multiply the advertised window size to achieve a larger window size. Both sides of a session must
be able to support this option for it to apply; this is determined during the session setup.
• TCP SACK Permitted Option: This option indicates that this node supports selective acknowledgments, which allows a node to acknowledge ongoing and incoming data packets while still asking for a specific missing packet. The recovery process only requires retransmission of the missing packet(s), instead of the missing packet and all the packets that followed. Both sides of a session must be able to support this option for it to apply, as determined during session setup.








