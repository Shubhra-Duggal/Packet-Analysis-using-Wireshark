# Secure Shell

## SSH 
The client is setup at 172.16.117.2 and the server is setup on 172.16.117.3 Ubuntu machine. The connection is created and wireshark is readied for capture. All packets are captured and display filters are added after.    

The wireshark is listening on ens33.
![Screenshot 2021-08-17 at 10 47 37 AM](https://user-images.githubusercontent.com/42912140/129669968-0abc56da-32b4-462e-88fa-87ba964b14f9.png)

We create the connection and capture the packets.
![Screenshot 2021-08-17 at 11 15 13 AM](https://user-images.githubusercontent.com/42912140/129670193-bf65ea64-894f-41ae-9e69-5543b1d92472.png)
![Screenshot 2021-08-17 at 11 15 00 AM](https://user-images.githubusercontent.com/42912140/129670197-0714c167-e386-4094-9d90-3daa1a3a4542.png)


## TCP Connection Establishment
![Screenshot 2021-08-17 at 11 20 32 AM](https://user-images.githubusercontent.com/42912140/129670726-3b16e04c-8d10-4b0c-83a6-005b2d6f06cf.png).       

Before a client attempts to connect with a server, the server must first bind to and listen at a port to open it up for connections: this is called a passive open. Once the passive open is established, a client may establish a connection by initiating an active open using the three-way (or 3-step) handshake:
SYN: The active open is performed by the client sending a SYN to the server. The client sets the segment's sequence number to a random value A.
SYN-ACK: In response, the server replies with a SYN-ACK. The acknowledgment number is set to one more than the received sequence number i.e. A+1, and the sequence number that the server chooses for the packet is another random number, B.
ACK: Finally, the client sends an ACK back to the server. The sequence number is set to the received acknowledgment value i.e. A+1, and the acknowledgment number is set to one more than the received sequence number i.e. B+1.
Steps 1 and 2 establish and acknowledge the sequence number for one direction. Steps 2 and 3 establish and acknowledge the sequence number for the other direction. Following the completion of these steps, both the client and server have received acknowledgments and a full-duplex communication is established.

The SYN packets is sent by the client.   
![Screenshot 2021-08-17 at 11 25 22 AM](https://user-images.githubusercontent.com/42912140/129671343-b42c7c16-25a5-415e-b94b-706080de8048.png).     


The SYN, ACK packet is sent by server.  
![Screenshot 2021-08-17 at 11 25 30 AM](https://user-images.githubusercontent.com/42912140/129671371-696f2a0d-706a-4258-bfed-3ecb8b7cba7e.png).    


The ACK flag is sent by client.     
![Screenshot 2021-08-17 at 11 25 38 AM](https://user-images.githubusercontent.com/42912140/129671397-8f2cd258-80cc-4e74-8c4c-f979a6d3ac9d.png).    


## TCP Connection Termination
![Screenshot 2021-08-17 at 11 20 46 AM](https://user-images.githubusercontent.com/42912140/129670736-d2363d8d-d2c3-4533-bc06-7af8e64a49da.png)

The connection termination phase uses a four-way handshake, with each side of the connection terminating independently. When an endpoint wishes to stop its half of the connection, it transmits a FIN packet, which the other end acknowledges with an ACK. Therefore, a typical tear-down requires a pair of FIN and ACK segments from each TCP endpoint. After the side that sent the first FIN has responded with the final ACK, it waits for a timeout before finally closing the connection, during which time the local port is unavailable for new connections; this prevents possible confusion that can occur if delayed packets associated with a previous connection are delivered during a subsequent connection.
It is also possible to terminate the connection by a 3-way handshake, when host A sends a FIN and host B replies with a FIN & ACK (combining two steps into one) and host A replies with an ACK.[17]
Some operating systems, such as Linux and HP-UX,[citation needed] implement a half-duplex close sequence. If the host actively closes a connection, while still having unread incoming data available, the host sends the signal RST (losing any received data) instead of FIN. This assures that a TCP application is aware there was a data loss.[18]
A connection can be in a half-open state, in which case one side has terminated the connection, but the other has not. The side that has terminated can no longer send any data into the connection, but the other side can. The terminating side should continue reading the data until the other side terminates as well.

![Screenshot 2021-08-17 at 11 29 39 AM](https://user-images.githubusercontent.com/42912140/129671776-ef2c2aad-ba96-4798-8c53-818ff93ba042.png)
![Screenshot 2021-08-17 at 11 29 50 AM](https://user-images.githubusercontent.com/42912140/129671780-28944af8-f7d5-48a6-9953-5f4d425471ba.png)
![Screenshot 2021-08-17 at 11 29 57 AM](https://user-images.githubusercontent.com/42912140/129671788-65e1433a-183a-4832-8ffa-98bc34ae194d.png)
![Screenshot 2021-08-17 at 11 30 03 AM](https://user-images.githubusercontent.com/42912140/129671795-3f841fb0-16ef-4aae-aeac-e3a59b69746b.png)


## SSH Conversation
![Screenshot 2021-08-17 at 11 22 31 AM](https://user-images.githubusercontent.com/42912140/129670902-1428b03e-89fc-4ea9-8781-71cc15bf3c16.png)
