---
title: "IPv4 Addressing"
date: 2019-02-05
tags: 
- network engineering
- IPv4
- Internet Protocol
---
I briefly touched on IPv4 addresses in the TCP/IP suite. In summary IPv4 addresses are:
Dot-separated.

- 32 bits long and represented in decimal.
- There are just over 4 billion available addresses.
- Therefore it is necessary to use subnetting to separate networks and duplicate IP addresses from one another.

![](images/ipv4-binary.jpg "An IPv4 address shown in both binary and decimal dot notations")

### IPv4 structure and what it represents

So we know IP addresses are 32 bits long and that they are separated into 4 decimal numbers by dot separation (this is known as dotted decimal), therefore each number must represent 8bits.

Just as a reminder a bit is a binary digit, it can only represent a 0 or 1.
Each 8 bit group is called an octet. If we were to look at the dotted decimal number 192.168.2.1 in binary it would be:

11000000.10101000.00000010.00000001

Wait what how did we make that leap? If you haven’t worked with binary before this can be a bit of a curveball. The best way I think of binary is to imagine how counting would have evolved if instead of 10 fingers we only had one on each hand.

So humans count in base 10 (decimal) because fingers, whereas computers, count in Base 2 (binary) because computers are basically a bucket load of on and off switches.
So if we look at one octet that is all 1’s (and I’m pushing the limits of medium’s formatting here):

1 1 1 1 1 1 1 1

would be equal to:

2⁷ + 2⁶ + 2⁵ + 2⁴ + 2³ + 2² + 2¹ + 2⁰

in other words:

128 + 64 + 32 + 16 + 32 + 16 + 8 + 4 + 2 +1
equals 255.

<script src="https://gist.github.com/skipster2k2/9fe8184c907184fa23b5f1435feb6912.js"></script>

or in reverse if we took the first octet in our initial example, 192. 192 is made up of 128 + 64, therefore in 1’s and 0’s looks like:

128, 64, 32, 16, 32, 16, 8, 4, 2, 1

1 , 1 , 0 , 0 , 0 , 0 , 0 , 0

<script src="https://gist.github.com/skipster2k2/e268f0e0fec1abf43e9b14d3ffff0266.js"></script>

## Subnetting

As mentioned earlier IPv4 only has a puny 4 billion addresses. In order to be able to allocate more addresses, we use subnetting to divide the internet into separate sub-networks, where the same IP addresses can be used in each subnet, but cannot talk to one another directly.

Subnets are allocated via a subnet mask, this defines how many bits are to be allocated to the network, and how many for the host. A subnet tells the hosts within it that they can all talk to each other without passing through a router.

## Classful networks

There are some standard defined subnets called Classful networks. The table below shows the three classes available for public use and the number of hosts you can allocate to them. The more observant amongst you may have noticed that the available hosts are 2 less than the total number of permutations, 2^(32-n) that’s because the .0 address is always reserved as the network address, and the highest number address is reserved as the broadcast address. Internet or Public IPs are assigned and managed by [IANA](https://www.iana.org/).

<script src="https://gist.github.com/skipster2k2/cf6ac01f1a22a290f3ba4c31edde134b.js"></script>

There are other classes but they are not publicly available and are reserved for uses such as by the military.

Sometimes you will see the subnet mask displayed after an IP address as such:
192.168.2.1/16 this is called CIDR (Classless inter domain routing) notation and is a simple way of showing the IP and the number of bits assigned to the network. For classful networks this is always a full octet, and so will equal /8, /16 and /24 for Class A, B, and C subnets respectively.

## Classless networks.

Classless networks are simply any subnet mask that doesn’t fit the classful pattern.
Say for example you had a network of 157.28.0.0 with a subnet mask of 255.255.0.0 (i.e. a class B network). You want to create 4 networks for that IP address but they all need to be bigger than 254 hosts. That means making the subnet mask class C isn’t going to work as you won't have enough hosts in each network, allocating the whole of the 3rd octet to the network is too much.

So to calculate what the 3rd octet will be we need to calculate the number of bits to dedicate to the network. As we found out earlier, the binary value of a decimal number is 2^n so if we need 4 networks we need to work out the square root of 4, which is 2. Therefore we need to change 2 bits from host (0) to network (1). In other words:

11000000

We can use our binary to decimal table to calculate the decimal value:

<script src="https://gist.github.com/skipster2k2/e32a3fbc25e78dba8300ce702604a7b8.js"></script>

128 + 64 is 192. So our subnet mask is 255.255.192.0. We can also work out the CIDR notation is /18 as that is the number of bits we have assigned to the network (the first two octets plus the first 2 bits of the 3rd octet). Cool!

Next, we need to work out what the 4 networks within that subnet will be. Firstly we can ignore the first two octets, as they are 255.255. so we know for all 4 networks they will be 157.28.x.x

Next, we need to look at the variations of bits that we have allocated to the network (in this example the first 2 bits. The table below shows us all the permutations of bit setting we can have:

<script src="https://gist.github.com/skipster2k2/bf627c64c7c4addcd6e228fa3d1e33d3.js"></script>

So from this, we know that our 4 networks are:

Network 1: 157.28.0.0/18

Network 2: 157.28.64.0/18

Network 3: 157.28.128.0/18

Network 4 157.28.192.0/18

Finally, now we know the 4 networks we can work out what the IP range for each one is.

Let's look at network 1, we now won't change the bits assigned to the network and are instead interested in the bits assigned to the host, so the first 2 and last 2 IP addresses in binary will look like the table below:

<script src="https://gist.github.com/skipster2k2/bca52e160c4a447bafd484d40fcd06d6.js"></script>

Don't forget that the first two bits in the 3rd octet can’t change because they are assigned to the network, not the hosts. It’s worth knowing here that the first and last IP in a network range are reserved. The first IP is the network address (in this case 157.28.0.0) and the last is the broadcast address (157.28.63. 255) the address for all hosts on the network to broadcast datagrams to one another. In which case our first network range is:

157.28.0.1 to 157.28.63.254.

Let’s work out the rest of the ranges:

<script src="https://gist.github.com/skipster2k2/3011d0358dd89db58ad256721ea00d94.js"></script>

Translated to decimal:

Network 1: 157.28.0.1 to 157.28.63.254

Network 2: 157.28.64.1 to 157.28.127.254

Network 3: 157.28.128.1 to 157.28.191.254

Network 4: 157.28.192.1 to 157.28.255.254

Ta da!