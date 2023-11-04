<img width="1058" alt="Screen Shot 2023-11-04 at 11 49 45 AM" src="https://github.com/kieubo90/Net_practice-42/assets/88286643/648346e9-34f1-4826-86f1-b2b614ff8694">


The interface R3:				The interface R2:				The interface R1:
IP: 105.201.111.244				IP: 105.201.111.1				IP: 105.201.111.243
Maks: 255.255.255.192			Mask: 255.255.255.128			Mask: 255.255.0.0 
Client B:						Client A:
IP: 105.201.111.134				IP: 105.201.111.132
Mask: 255.255.0.0				Mask: 255.255.0.0

In this exercise, Client B and Client A are connecting through a switch to the router interface R1.
This is why it is necessary for them to have the same subnet mask. 
The interesting point to note is that the mask cannot be set to 255.255.1.0. 
The reason is that valid subnet masks must follow a specific sequence such as 0, 128, 192, ... 254 
due to binary behavior and the requirements for determining the network portion. 
Router R1 needs to establish connections with R3 and R2.
