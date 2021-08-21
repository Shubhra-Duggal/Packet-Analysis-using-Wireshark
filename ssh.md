# Secure Shell

The SSH connection is setup via [OpenSSH](https://github.com/Shubhra-Duggal/Network-Programming/tree/main/SSH).  

## Setup 
The client is setup at 172.16.117.2 and the server is setup on 172.16.117.3 Ubuntu machine. The connection is created and wireshark is readied for capture. All packets are captured and display filters are added after.    

The wireshark is listening on ens33.
![Screenshot 2021-08-17 at 10 47 37 AM](https://user-images.githubusercontent.com/42912140/129669968-0abc56da-32b4-462e-88fa-87ba964b14f9.png)

We create the connection and capture the packets.
![Screenshot 2021-08-17 at 11 15 13 AM](https://user-images.githubusercontent.com/42912140/129670193-bf65ea64-894f-41ae-9e69-5543b1d92472.png)
![Screenshot 2021-08-17 at 11 15 00 AM](https://user-images.githubusercontent.com/42912140/129670197-0714c167-e386-4094-9d90-3daa1a3a4542.png).   

The conversation has a [TCP](/tcp.md) connection estalishment phase and a connection termination phase.   


