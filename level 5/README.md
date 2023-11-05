
<img width="1252" alt="Screen Shot 2023-11-05 at 1 13 11 PM" src="https://github.com/kieubo90/Net_practice-42/assets/88286643/d43bff69-2abe-41be-93d9-865201f7d4d3">


Interface R2:				Interface R1:				Interface B1:				Interface A1:				Clien B:			
IP: 149.253.77.254			IP: 51.216.4.126			IP: 149.253.77.25			IP: 51.216.4.12				default
Mask: 255.255.192.0		Mask: 255.255.255.128		Mask: 255.255.192.0		Mask: 255.255.255.128		149.253.77.254	

Client A:
Next hop: 0.0.0.0/0
Destination: 51.216.4.126

First, interfaces A1 and B1 must be configured to connect with interfaces R1 and R2, respectively. These interfaces are on routers. For connectivity, A1 should share the same subnet mask with R1, and similarly, B1 should have the same subnet mask as R2. The mask will determine the range of IP addresses available for A1 and B1.

Based on the IP addresses of R1 and R2, we can assign IP addresses to A1 and B1 by adjusting the last octet. For instance, if the last octet of R1 is 128, it means we can assign addresses within the range of 1-126 or 129-254. However, since the default range for R1's last octet is up to 126, we should select an address between 1-126 for A1. Similarly, for B1, since the last octet of R2 is 0, we can select any address between 1-253, considering that the default end range for R2's last octet is 254.

Lastly, to allow Client A and Client B to communicate across different routers, they need to be on the same subnet mask, which is the default in our scenario. Their IP addresses should correspond to the IP addresses of R1 and R2. By assigning R1's address to Client A and R2's address to Client B, they can establish connectivity.
