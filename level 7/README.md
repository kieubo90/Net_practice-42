<img width="1308" alt="Screen Shot 2023-11-07 at 2 01 10 PM" src="https://github.com/kieubo90/Net_practice-42/assets/88286643/f88620c4-4e50-46e4-9932-edd6deb06024">

In this exercise, we need to consider the behavior of this circular network. Since the network only requires three components:

Network between Computer1 and Router1
Network between Router1 and Router2
Network between Router2 and Computer2
For the subnet mask of this circular network, we only need to use 255.255.255.240 or /28. We can leave the subnet masks for the client devices as default. So, we set up the interfaces with a subnet mask of 255.255.255.240 or /28.

For interface A1, we need to connect it to Router1. So, the IP address of A1 can be set as 104.198.14.2 (it can be within the range 2 - 14) since this subnet allows for 16 host addresses.

For the two routers, R1 and R2, they need to be able to connect with each other in the same way as Computer A1 connects with R1. We can use a range for the last octet from 241 to 253 for this purpose.

Additionally, since we have routes between R1 and R2, we can leave the subnet masks as default. The IP addresses of the routes can be based on the IP addresses of the routers. For the routes of R1, the IP address can be 104.198.14.241 (241-253), and for the routes of R2, the IP address can be 104.198.14.254 (which cannot be changed because R1's IP is fixed).

The rest of the configuration is similar to Computer A1 connecting with R1. For Computer C to connect with Router R2, we can use the same subnet mask: 255.255.255.240 or /28. The IP address should be in a different range from the other networks, avoiding conflicts with addresses from the ranges 1-14 and 241-254. For example, Computer C can have an IP address of 104.198.14.65 to 104.198.14.78.

To enable Computer A and C to connect with each other, we need to use a default subnet mask and set the address of their respective routers. For Computer A, the router's IP address is 104.198.14.1, and for Computer C, it is 104.198.14.78.
