# Internet Control Message Protocol


## ICMP Code

![Screenshot 2021-08-14 at 5 37 57 PM](https://user-images.githubusercontent.com/42912140/129445972-997ed166-db03-4975-97ef-ee86af8d533d.png)

## ICMP pings
One of the most well-known uses of ICMP is to ping, wherein a device sends an ICMP echo request (Type 8, Code 0) packet to a 
distant host (via that host's IP address), which will (if the ICMP service isn't disabled or blocked by an intermediate firewall) 
respond with an ICMP echo reply (Type 0, Code 0) packet. Pings are
used to determine whether the target host is available and can be reached over the network. By measuring the time that expires 
between ping requests and replies, we know the round trip time (RTT) delay time over the network path.

The host (Mac OS) machine pings the virtual machine (Ubuntu) and receives the reply. The machine 172.16.117.2 is pinged from the machine 172.16.117.2 and the reply is received.
![Screenshot 2021-08-14 at 5 03 25 PM](https://user-images.githubusercontent.com/42912140/129445159-a0eaf63b-84e3-4705-b41d-a4da46174220.png)


The Ubuntu machine has Wireshark running with ICMP packets displayed.
![Screenshot 2021-08-14 at 5 03 38 PM](https://user-images.githubusercontent.com/42912140/129445205-fb9d2293-c54e-4232-a910-27da59bbdd6a.png)


**Note**: All packets have been captured, but only ICMP have been displayed above.
![Screenshot 2021-08-14 at 5 13 30 PM](https://user-images.githubusercontent.com/42912140/129445220-dc255250-c1a4-49d1-a0e8-44ac6580a472.png)


## ICMP traceroutes
A variation of ping functionality is used to perform a traceroute (also known as traceroute), which is a list of the IP addresses of the router interfaces that packets traverse to get from a sending device to a target host or device. The traceroutes are used to determine or confirm the network path taken from a sending device to a target host or device.


![Screenshot 2021-08-14 at 5 28 43 PM](https://user-images.githubusercontent.com/42912140/129445612-79ac0ca1-0b63-4647-8aee-004bb2a6904f.png)


A traceroute is accomplished by sending the ICMP echo request packets to a distant host just as in a normal ping, but with modifications to the Time-to-Live (TTL)
field in the IP header of each packet. The traceroute function takes advantage of
the fact that each router in a network path decrements the TTL value in a packet by 1, so as the packet traverses, the routers in a path and the TTL value will decrease accordingly along the way. If a router receives a packet with a TTL value of 1, it will send an ICMP TTL exceeded in transit (Type 11, Code 0) error message back to the sender (along with a copy of the request packet it received) and otherwise discard (not forward) the packet.



![Screenshot 2021-08-14 at 5 26 45 PM](https://user-images.githubusercontent.com/42912140/129445601-a022b7e8-b35d-4968-839e-7074e321b1b0.png)

![Screenshot 2021-08-14 at 5 26 35 PM](https://user-images.githubusercontent.com/42912140/129445573-0fd33c8a-3755-4d1d-af38-c52f288ffb32.png)




