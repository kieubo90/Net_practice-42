<img width="1173" alt="Screen Shot 2023-11-06 at 11 04 01 AM" src="https://github.com/kieubo90/Net_practice-42/assets/88286643/fe9173e5-3ef4-4c43-beb1-5dbcbb543e9a">

Interface Somewhere on the Net:
IP: 8.8.8.8
Mask: /16
This part we do not need to care since it is not related to the connection within the router to the switch and computer.

Internet I: Internet routes:	Interface R2				    Interface R1				    Interface A1:
destination: 163.172.250.12		IP: 163.172.250.12			IP: 75.241.19.254			  IP: 75.241.19.227
next hop: 75.241.19.225/25		Mask: 255.255.255.240		Mask: 255.255.255.128		Mask: 255.255.255.128

Client A:				                Router R: gate.non-real.com Routes:
destination: 75.241.19.254		  next hop: 0.0.0.0/0
next hop: 0.0.0.0/0		          Destination: 163.172.250.1

Firstly, as usual, interface A1 needs to connect with interface R1, so the masks of both must be identical. In the range of 128 (last octet), we can assign values from 129-254. Since the default of A1 is 227, we must assign values to R1 from 129-254, excluding 127.

Moving on to router R, its mask is 10.0.0.0/8. Since the mask of client A is default, it can connect to anything as long as the router ends with "/0". The "/0" represents CIDR notation (Classless Inter-Domain Routing).

As R2 is set to default, we're only concerned about the mask of inter-routes. The address is 75.241.19.0/31, we need to change this address match with interface R1 and in range with subnet mask 128(last octet) 75.241.19.225. This allows it to connect with router R1, which in turn connects with our client computer A. We can adjust this based on its CIDR and the subnet masks of Client A and R1. For client A, we don't need to be concerned because it will accept whatever it receives. However, R1 requires 2 host addresses, ranging from 0-127 and 128-255. Therefore, we must set the bits of CIDR from 0-24 to ensure we don't limit the host addresses of R1.
