# Transmission Control Protocol

## Structure
![Screenshot 2021-08-21 at 7 06 00 PM](https://user-images.githubusercontent.com/42912140/130323498-ab63894c-ed86-4680-a7bb-9dc529d04134.png).    

* Source and Destination port: The server is assigned one of the well known ports to access standard applications, whereas the client has one of the ports in the higher ranges.
* Sequence number: A random number is assigned at the beginning of the session and incremented for every packet send.
* Acknowledgement numberL When the ACK field is set in the flag then this holds the next (expected) sequence number. It also works as the acknowledgment of the packets received before.
* Header: Content varies depending upon options that are used.
* Flags: Controls the connection setup, termination and flow control mechanisms.
* Window: Indicated the current size of buffer that holds the received data, till receiver machine can process it. This indicates the sending machine to how to adjust the flow of packets.
* Checksum:
* Urgent pointer:  
* TCP options: TCP supports a number of additional options which are in common use in modern networks.

## TCP Flags

![Screenshot 2021-08-14 at 5 42 15 PM](https://user-images.githubusercontent.com/42912140/129445952-bc820c5b-b049-4e62-b4a0-cea7692f55f1.png)


## TCP Handshake

### Connection Establishment
Before a client attempts to connect with a server, the server must first bind to and listen at a port to open it up for connections: this is called a passive open. Once the passive open is established, a client may establish a connection by initiating an active open using the three-way (or 3-step) handshake:   
![Screenshot 2021-08-17 at 11 20 32 AM](https://user-images.githubusercontent.com/42912140/129670726-3b16e04c-8d10-4b0c-83a6-005b2d6f06cf.png). 

Step 1 (SYN) : In the first step, client wants to establish a connection with server, so it sends a segment with SYN(Synchronize Sequence Number) which informs server that client is likely to start communication and with what sequence number it starts segments with.    
![Screenshot 2021-08-17 at 11 25 22 AM](https://user-images.githubusercontent.com/42912140/129671343-b42c7c16-25a5-415e-b94b-706080de8048.png).   


Step 2 (SYN + ACK): Server responds to the client request with SYN-ACK signal bits set. Acknowledgement(ACK) signifies the response of segment it received and SYN signifies with what sequence number it is likely to start the segments with.   
![Screenshot 2021-08-17 at 11 25 30 AM](https://user-images.githubusercontent.com/42912140/129671371-696f2a0d-706a-4258-bfed-3ecb8b7cba7e.png).  


Step 3 (ACK) : In the final part client acknowledges the response of server and they both establish a reliable connection with which they will start the actual data transfer     
![Screenshot 2021-08-17 at 11 25 38 AM](https://user-images.githubusercontent.com/42912140/129671397-8f2cd258-80cc-4e74-8c4c-f979a6d3ac9d.png).   


The steps 1, 2 establish the connection parameter (sequence number) for one direction and it is acknowledged. The steps 2, 3 establish the connection parameter (sequence number) for the other direction and it is acknowledged. With these, a full-duplex communication is established.

Steps 1 and 2 establish and acknowledge the sequence number for one direction. Steps 2 and 3 establish and acknowledge the sequence number for the other direction. Following the completion of these steps, both the client and server have received acknowledgments and a full-duplex communication is established.

### Connection Termination
![Screenshot 2021-08-17 at 11 20 46 AM](https://user-images.githubusercontent.com/42912140/129670736-d2363d8d-d2c3-4533-bc06-7af8e64a49da.png)

The connection termination phase uses a four-way handshake, with each side of the connection terminating independently. When an endpoint wishes to stop its half of the connection, it transmits a FIN packet, which the other end acknowledges with an ACK. Therefore, a typical tear-down requires a pair of FIN and ACK segments from each TCP endpoint. After the side that sent the first FIN has responded with the final ACK, it waits for a timeout before finally closing the connection, during which time the local port is unavailable for new connections; this prevents possible confusion that can occur if delayed packets associated with a previous connection are delivered during a subsequent connection.
It is also possible to terminate the connection by a 3-way handshake, when host A sends a FIN and host B replies with a FIN & ACK (combining two steps into one) and host A replies with an ACK.[17]
Some operating systems, such as Linux and HP-UX,[citation needed] implement a half-duplex close sequence. If the host actively closes a connection, while still having unread incoming data available, the host sends the signal RST (losing any received data) instead of FIN. This assures that a TCP application is aware there was a data loss.[18]
A connection can be in a half-open state, in which case one side has terminated the connection, but the other has not. The side that has terminated can no longer send any data into the connection, but the other side can. The terminating side should continue reading the data until the other side terminates as well.

![Screenshot 2021-08-17 at 11 29 39 AM](https://user-images.githubusercontent.com/42912140/129671776-ef2c2aad-ba96-4798-8c53-818ff93ba042.png)
![Screenshot 2021-08-17 at 11 29 50 AM](https://user-images.githubusercontent.com/42912140/129671780-28944af8-f7d5-48a6-9953-5f4d425471ba.png)
![Screenshot 2021-08-17 at 11 29 57 AM](https://user-images.githubusercontent.com/42912140/129671788-65e1433a-183a-4832-8ffa-98bc34ae194d.png)
![Screenshot 2021-08-17 at 11 30 03 AM](https://user-images.githubusercontent.com/42912140/129671795-3f841fb0-16ef-4aae-aeac-e3a59b69746b.png)



