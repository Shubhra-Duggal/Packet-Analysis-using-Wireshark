# Internet Control Message Protocol

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


