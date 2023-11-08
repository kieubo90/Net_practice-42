<img width="1125" alt="Screen Shot 2023-11-08 at 5 44 59 PM" src="https://github.com/kieubo90/Net_practice-42/assets/88286643/57d9be67-90c1-4036-bd27-5fe7e05b4b5b">

Internet I: Internet Routes:		Interface R12				    Interface R13				    Router R1: gate.non-real.com
Destination: 163.196.181.0/26		IP: 163.18.250.12			  IP: 163.196.181.62			Destination: 0.0.0.0/0		0.0.0.0/0
Next hop: 163.18.250.12			    Mask: 255.255.255.240		Mask: 255.255.255.240		next hop: 163.196.181.51 	163.18.250.1

Interface R21:				    Interface R23			  Interface R22				        Router R2: transit.my-isp.org
IP: 163.196.181.51			  IP: 163.196.181.2		IP: 163.196.181.20			    Destination: 10.0.0.0/0
Mask: 255.255.255.240		  Mask: /28			      Mask: 255.255.255.240		    Next hop: 163.196.181.62

Interface D1				    Client D: home.non-real.com		Interface C1				    Client C: office.non-real.com
IP: 163.196.181.3			  Destination: default				  IP: 163.16.181.21			  Destination: 0.0.0.0/0
Mask: 255.255.255.240		Next hop: 163.196.181.2			  Mask: 255.255.255.240		Next hop: 163.196.181.20

We have Internet I with a default destination of 163.196.181.0/26, which connects to Router R1. The first route on R1 has a default destination with the next hop set to 163.196.181.51. This aligns with the /26 subnet, where the addressable range is divided into blocks such as 0-63, 64-127, and so on. The next hop of Internet I's route is 163.18.250.12 because this is the IP address of Interface R12. It is crucial that R12's IP address matches the next hop address to establish connectivity to the Internet.

For Interface R21, the subnet must fall within the range of 163.196.181.49-62, and we have Router R2's route set to 163.196.181.62. Therefore, Interface R13 is assigned the IP address 163.196.181.62 to facilitate the connection between R13 and R21. All associated subnet masks should be 255.255.255.240.

From Interface R21, there are two sub-routers connecting to Clients D and C. For Interface R23, the IP is 163.196.181.13, and the subnet mask is /28, which allows for four separate networks. Interface D1 should connect with Interface R23; thus, its address should be within the range of 1-14, based on their last octet, which is .240.

Interface R22 is assigned 163.196.181.34, and Interface C1 is assigned 163.196.181.35, ensuring they do not overlap with Interface R23 and D.

The routes for Clients D and C are set to connect with Interfaces R23 and R22, respectively. The next hop for Client D is 163.196.181.13, and for Client C, it is 163.196.181.34. Their destinations are both set to the default route.
