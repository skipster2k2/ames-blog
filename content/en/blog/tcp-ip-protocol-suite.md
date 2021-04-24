---
title: "TCP/IP Protocol Suite"
date: 2019-02-01
tags:
- TCP/IP
- Network Security
- Network Engineering
---
TCP/IP is a set of protocols that form the backbone of the internet. As I described in the [OSI model post]("/the-osi-model.md"), TCP (Transmission Control Protocol) provides reliable, ordered, and error-checked delivery of a stream of bytes between applications running on hosts. IP (Internet Protocol) is the protocol for shifting packets around between hosts in the network layer. The TCP/IP suite, however, contains a whole bunch of protocols beyond these two. (Fun fact: If to devices are communicating in a network with TCP/IP they are called network hosts. If they are using anything else they are called network nodes.)

As with all real-world implementations TCP/IP _sort of_ follows the OSI Model.

> All models are wrong but some are useful — George Box

![](/images/tcp-vs-osi.jpg "Image showing the OSI model compared to the TCP/IP protocol suite. This is explained in detail below.")

## TCP/IP Applications

I won't spend ages on TCP/IP applications but real-world context helped me make a bit more sense of the host layers in the OSI model. I had a bit of a hard time getting my head around the difference between application programs and the application layer. TCP/IP helped me suss out what was meant. For example when I open a web browser — an application program, it makes a call to HTTP — the protocol in the application layer of the OSI stack. The web browser itself is not represented in the model.

There are a whole bunch of protocols operating at this level to ensure different applications can access the network. Some common examples are:

**HTTP (HyperText Transfer Protocol):** the rules for handling hypertext documents and hyperlinks, i.e. the world wide web.

**SMTP (Simple Mail Transfer Protocol):** The rules for sending emails.

**POP3(Post Office Protocol) and IMAP (Internet Message Application Protocol):** The rules for receiving emails.

**FTP (File Transfer Protocol):** The rules for sending files.

**SSH: (Secure Shell):** The rules for managing network services securely over the internet.

## Transmission Control Protocol (TCP)

Because most communication on the internet requires a reliable connection, TCP has become the dominant protocol. It operates at the network layer of the OSI model and it establishes a reliable connection through a process called the three-way handshake:

- Host 1 sends a Synchronisation (SYN) Request to Host 2.
- Host 2 receives the request and sends back a Synchronisation Acknowledgement (SYN/ACK) request back to Host 1.
- On receipt of the SYN/ACK Host 1 sends a final Acknowledgement (ACK) back to Host 2 and the connection is established.
- Data transfer (in the form of bytes) then takes place between the two hosts.

This virtual circuit setup is called overhead. Additionally, the hosts don’t rely solely on the initial requests to ensure the reliability of the connection but instead will continue to check periodically to ensure it is still established and that data is flowing properly.

So that’s all great if one application is making a request but as we have seen there are loads of applications and the higher layers making requests. This can often be at a faster speed than the supporting network and can cause bottleneck issues. TCP manages this demand with a process called Flow Control. Flow control is a pull system (which as an agile delivery lead makes me very happy). The receiver is responsible for telling the sender that it has received data and it is ok to send more. Lovely!

1. The segments delivered are acknowledged back to the sender upon their reception.
2. Any segments not acknowledged are retransmitted.
3. Segments are sequenced back into their proper order upon arrival at their destination.
4. A manageable data flow is maintained in order to avoid congestion, overloading, and data loss.

This works well most of the time but it is still possible for the transmitting host to send a burst of data that is too much for the receiver to cope with. What happens then? The receiving host has a memory allocation called a buffer and it stores the burst of datagrams in this memory. (The origin of the dreaded ‘buffering’ message when viewing videos on the internet, a data-heavy process).

But what if the sender is so fast, it sends a massive stream of datagrams before the host has a chance to acknowledge it, and that is larger than the buffer? TCP has a plan for this too, in this scenario the receiving host sends a Not Ready indicator back to the sender, this is like an emergency brake and stops the sender from transmitting any more data until the host has had a chance to process the data in its buffer. Once the receiving host has done this it then transmits a Go indicator to the sender to resume data transfer.

Importantly the data is transferred in order from sender to receiver, this sequencing means that should any of the three failure scenarios mentioned above occur, both hosts know how far they have got through the transfer in order to resume after the failure is rectified.

These multiple levels of fault tolerance mean that TCP is a very reliable connection-oriented protocol because it has the following characteristics:

- A virtual circuit is set up (such as a three-way handshake).
- It uses sequencing.
- It uses acknowledgements.
- It uses flow control.

Finally, it is possible to reduce the robustness of this process for the sake of throughput through a control called Windowing. As you can imagine, acknowledging every datagram received back to the host could be a hefty process for large file transfers. Windowing defines how many data segments (measured in bytes) can be sent before an acknowledgement is required back from the receiving host. For example, a window of 3 would mean that 3 bytes of data can be sent before the receiver needs to send the sender and acknowledgement. The larger the size of the window, the bigger the risk of a buffer overflow.

But how is sequencing ensured if the receiver only acknowledges every few data segments? This is done with acknowledgements. Say Host A wants to transmit the segments 123456789 with a window of 3 to Host B.

- Host A sends 1
- Host A sends 2
- Host A sends 3
- Host B receives 123 and so acknowledges by requesting 4.
- Host A sends 4
- Host A loses connection whilst trying to send 5.
- Host A sends 6
- Host B now realises it is missing 5 so requests 5.
- Host A sends 5
- Host B now requests 7
- etc etc

## Internet Protocol (IP)

The Internet Protocol is concerned with addressing — ensuring data gets from the right source to the right destination. It sits unsurprisingly in the network layer of the OSI model.

There are currently two versions of the protocol in active use, IPv4 and IPv6.

### IPv4

IPv4 is the most well-known version. When most people talk about IP addresses they are describing an IPv4 address. They are made up of 4 dot-separated numerical values called octets. Each value is a decimal representation of a binary value. I will cover what this means (and how to calculate IP addresses and subnet masks in Week 2).

IPv4 is a 32 bit pool of addresses, this means that it is possible to have 4,294,967,296 (4 billion) addresses. This sounds like a lot but we have already nearly run out of IPv4 public addresses. Public addresses are those that are distributed by IANA (The Internet Assigned Number Authority) and are the IP representation of internet domain names. You can have many networks using the same IP addresses provided they are contained behind a subnet. A subnet is a logical subdivision of an IP network and can be described as Classful or Classless. This will be covered in more detail in Week 2.

An IPv4 address looks like this:

193.168.2.1/24

Where 192.168.2.1 is the host address and /24 is the subnet. The subnet can also be represented in dot-separated format, in the case of /24 this will be 255.255.255.0

### IPv6

IPv6 are 128-bit addresses, they are colon separated and represented in hexadecimal. The IPv6 pool of addresses is 340,282,366,920,938,463,463,374,607,431,768,211,456 or 340 billion billion billion billion addresses!! As a result, they don't have a need for subnet’s. IPv6 headers are much smaller than IPv4 addresses, uses IPSec by default (encrypts the packets whilst being sent) it also broadcasts by default in Multicast mode.

An example IPv6 address looks like this:

2001:0DB8:0000:0000:0000:FF00:0042:8329

It is ok to remove all leading zeroes from an address:

2001:DB8:0:0:0:FF00:42:8329

And consecutive zeroes can be removed and represented by double colons. Although only once within the sequence:

2001:DB8::FF00:42:8329

## Network Access or Link Layer

The TCP/IP protocol suite is designed to be device agnostic and so doesnt concern itself too much with the link layer. As with the OSI model the link layer is concerned with moving packets between network hosts and includes protocols for translating logical IP addresses to physical MAC addresses such as the ARP (Address Resolution Protocol).