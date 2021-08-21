# Transmission Control Protocol


![Screenshot 2021-08-21 at 7 06 00 PM](https://user-images.githubusercontent.com/42912140/130323498-ab63894c-ed86-4680-a7bb-9dc529d04134.png)


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



## TCP Handshake

### Connection Establishment
Before a client attempts to connect with a server, the server must first bind to and listen at a port to open it up for connections: this is called a passive open. Once the passive open is established, a client may establish a connection by initiating an active open using the three-way (or 3-step) handshake:   
![Screenshot 2021-08-14 at 5 49 54 PM](https://user-images.githubusercontent.com/42912140/129446137-fe8da299-4d86-4f98-9c3d-42571de7a1c6.png)

Step 1 (SYN) : In the first step, client wants to establish a connection with server, so it sends a segment with SYN(Synchronize Sequence Number) which informs server that client is likely to start communication and with what sequence number it starts segments with
Step 2 (SYN + ACK): Server responds to the client request with SYN-ACK signal bits set. Acknowledgement(ACK) signifies the response of segment it received and SYN signifies with what sequence number it is likely to start the segments with
Step 3 (ACK) : In the final part client acknowledges the response of server and they both establish a reliable connection with which they will start the actual data transfer
The steps 1, 2 establish the connection parameter (sequence number) for one direction and it is acknowledged. The steps 2, 3 establish the connection parameter (sequence number) for the other direction and it is acknowledged. With these, a full-duplex communication is established.

Steps 1 and 2 establish and acknowledge the sequence number for one direction. Steps 2 and 3 establish and acknowledge the sequence number for the other direction. Following the completion of these steps, both the client and server have received acknowledgments and a full-duplex communication is established.

### Connection Termination
The connection termination phase uses a four-way handshake, with each side of the connection terminating independently. When an endpoint wishes to stop its half of the connection, it transmits a FIN packet, which the other end acknowledges with an ACK. Therefore, a typical tear-down requires a pair of FIN and ACK segments from each TCP endpoint. After the side that sent the first FIN has responded with the final ACK, it waits for a timeout before finally closing the connection, during which time the local port is unavailable for new connections; this prevents possible confusion that can occur if delayed packets associated with a previous connection are delivered during a subsequent connection.
It is also possible to terminate the connection by a 3-way handshake, when host A sends a FIN and host B replies with a FIN & ACK (combining two steps into one) and host A replies with an ACK.[17]
Some operating systems, such as Linux and HP-UX,[citation needed] implement a half-duplex close sequence. If the host actively closes a connection, while still having unread incoming data available, the host sends the signal RST (losing any received data) instead of FIN. This assures that a TCP application is aware there was a data loss.[18]
A connection can be in a half-open state, in which case one side has terminated the connection, but the other has not. The side that has terminated can no longer send any data into the connection, but the other side can. The terminating side should continue reading the data until the other side terminates as well.


