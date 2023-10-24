
<img width="953" alt="Screen Shot 2023-10-23 at 5 57 46 PM" src="https://github.com/kieubo90/Net_practice-42/assets/88286643/505a5a4b-e087-46dd-8977-760698862529">

This is also another basic of IP address and subnet mask. Since we only need to consider 2 individuals computers.
This time the subnet mask of interface B1 and A1 is : 255.255.255.224.
So the range of the IP address are:
192.168.117.1 - 192.168.117.30
192.168.117.33 - 192.168.117.62
192.168.117.65 - 192.168.117.94
192.168.117.97 - 192.168.117.126
192.168.117.129 - 192.168.117.158
192.168.117.161 - 192.168.117.190
192.168.117.193 - 192.168.117.222
192.168.117.225 - 192.168.117.254

But the interface B1 is fixed with the last Octet is 222. so we can choose from this range 
192.168.117.193 - 192.168.117.222 .Except 222 we can choose any.

The same thing with interface D1 and C1 but now the subnet mask is /30 so leave us only 2 option for the last octet are:
253 and 254. The giving IP is 127.0.0.0 which is public IP address so we can borrow the IP address from B1 and A1 or you can
searching for the private IP address and using those as long as the last Octet of D1 and C1 are 253 and 254.
