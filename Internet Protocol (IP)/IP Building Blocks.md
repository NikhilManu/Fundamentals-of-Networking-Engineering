## The IP Building Blocks

# What we mean by packets?

Packets is a layer three, that means its a bunch of data with destination IP address with source IP address.

# IP address

- Layer 3 property
- Can be set automatically or statically
- Network and Host portion
- 4 bytes in IPv4 - 32 bits

# Network vs Host

- a.b.c.d/x (a.b.c.d are integers) x is the network bits and remaining are the host.
- 192.168.254.0/24 => First 24 bits (3 bytes) are network the rest 8 are for the host.
- This means we can have 2^24 networks and each network has 2^8(255) hosts. Also called a Subnet

# Subnet Mask

- 192.168.254.0/24 is also called a subnet.
- The subnet has a mask 255.255.255.0
- Subnet mask is used to determine whether an IP is in the same subnet

# Default Gateway

- Most networks consist o hosts and a Default Gateway
- When Host A want to talk to B directly if both are in same subnet. Otherwise A sends it to someone who might know, the gateway
- The Gateway has an IP Address and each hos should know its gateway
