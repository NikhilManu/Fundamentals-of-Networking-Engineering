## Host to Host Communication

- I need to send a message from Host A to Host B
- Usually a request to do something on host B (RPC)
- Each host n/w card has a unique Media Access Control (MAC) address
- Host A sends message to Host B specifying the MAC address. Everyone will "get" the message but only B will accept it.

- Imagine millions of machines. We need a way to eliminate the need to send it to everyone. The address needs to get better
- We need routability, so we have the IP address. IP address is built in two parts
- One part to identify the n/w, the other is for the host
- We use the n/w portion to eliminate many n/w. The host part is used to find host
- We still need the MAC addressses

Ex - 192.168.1.3, 192.168.1.4, 192.168.2.1, 192.168.2.2 ( Here first two are in same n/w and last two are in same n/w)

# What if you have many apps?

- It may not be enough to address the host. The host may be running many aps each with different requirement
- This is where we use "PORTS".
- we can send a HTTP request on port 80, a DNS request on port 53 and an SSH request on port 22 all running on the same server
