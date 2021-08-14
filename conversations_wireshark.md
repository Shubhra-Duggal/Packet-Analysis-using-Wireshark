# Conversations on Wireshark

Conversations can accessed from the Statistics menu on Wireshark.
![Screenshot 2021-08-14 at 12 40 32 PM](https://user-images.githubusercontent.com/42912140/129438355-3b2e7869-e84b-48f9-b99c-2a1e191ce3a1.png)   


The IPv4 section is observed.
![Screenshot 2021-08-14 at 12 42 15 PM](https://user-images.githubusercontent.com/42912140/129438386-41cd9047-a017-4337-8098-58d4003ef5bf.png)    



The rows can also be sorted on the basis of total bytes exchanged to identify the **Top Talkers**. 
![Screenshot 2021-08-14 at 4 50 41 PM](https://user-images.githubusercontent.com/42912140/129444749-191b085a-a357-476d-b22a-d9f09efe6ced.png)

## Network Name Resolution

Resolve physical addresses option displays assigned manufacturere code in place of first 3 octets.   
![Screenshot 2021-08-14 at 4 42 25 PM](https://user-images.githubusercontent.com/42912140/129444766-30b1aa12-5817-4c65-a998-54654acc56e6.png)

![Screenshot 2021-08-14 at 4 42 13 PM](https://user-images.githubusercontent.com/42912140/129444756-62f79db4-fee2-4b6c-9457-3ca401455867.png)


Also, the IP addresses do not provide much information, as it is not exactly a human readable format. Network Name Resolution feature can be utilised to perform reverse DNS queries to obtain names for the IP address. 

![Screenshot 2021-08-14 at 4 52 37 PM](https://user-images.githubusercontent.com/42912140/129444809-2406576a-1cf6-40b8-8ec2-e406f3f3ecb7.png)
![Screenshot 2021-08-14 at 4 52 24 PM](https://user-images.githubusercontent.com/42912140/129444812-a8465d5d-0729-4a9c-8518-9e1863cc6374.png)


The resolve network layer names option should be disabled so that Wireshark does not create additional network traffic when reolving the IP addresses, by making reverse DNS queries. Instead it can be enabled after the capture is completed. Even the ports can be given protocol-specific names.
![Screenshot 2021-08-14 at 4 54 37 PM](https://user-images.githubusercontent.com/42912140/129444860-763e9650-04a6-4a02-b8a4-e81a9fac663e.png)



