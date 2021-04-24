---
title: "Network Fundamentals"
date: 2019-01-28
tags:
- network security
- network design
- network engineering
---
![](/images/network_fundamentals.jpg "An image showing a number of colourful Cat5 cables with the banner ‘Network fundamentals’")

Network fundamentals explores how computer networks are designed to enable the sharing of data taking into account three key requirements:

**Performance.** The sharing of data and resources doesn’t degrade the computers on the network.

**Reliability.** The network doesn’t fall over all the time.

**Security.** Data is only shared with those that should have access to it.

## Types

**Peer to Peer** is where every node on the network has equal access to the network and each node shares data and resources. The advantages are you don’t have to fork out for servers, or administrators to manage the network. The disadvantages are that every user of the network has to ensure they have an access token for every host on the network, this doesn’t scale well and is a nightmare to manage.

**Client-Server** is where there is a centralised server managing users access tokens and credentials (in the case of a windows network via active directory). The advantages are that this scales well for large networks, users only have one set of credentials which know what roles and permissions the user has to resources on the network. Additionally, servers have more grunt so can manage multiple requests so performance is better. The disadvantages are it’s more expensive and requires administrators of the network.

## Network Scale

Depending on how big your network is, defines the best approach to designing it, there are a number of different designs:

**Local Area Network.** LAN’s interconnect hosts within a small geographical area, usually an office. LAN’s are usually owned by the same company, and can be as big as a room, a floor, a building, or a campus of buildings. The course says data rates are faster than LAN’s. However, I’m not sure how true this is, Dark fibre networks, usually used in WAN’s can have speeds up to 10GBps, most LAN’s I have come across are rarely faster than 1Gbps.

**Metropolitan Area Network.** MAN’s interconnect hosts within a city sized area. MAN’s can be owned and utilised as public utilities or may be used to connect companies or campuses covering lots of buildings in a citywide area. They are often used to connect LAN’s in different buildings together.

**Wide Area Network.** WAN’s connect hosts that are ‘geographically dispersed, usually over 100km apart. Similar to MAN’s a WAN can be thought of as a number of LAN’s connected together via transmission lines and routers.

**Personal Area Network.** PAN’s are localised networks of a couple of metres for personal devices to communicate with one another. The devices may or may not belong to the person in question. PANs can be used for communication among the personal devices themselves (intrapersonal communication), or for connecting to a higher level network and the Internet (an uplink). PAN technology includes It can be made possible using IrDA, Bluetooth and USB.

## Physical Topology

**Physical topology** describes how we connect hosts together (primarily in cabled networks). There are 4 types: Star, Extended Star, Bus and Ring.

**Star topology** is where all hosts are connected to one another via a central network device such as a hub or switch. This is a really common topology as it is easy to extend and the impact of cable failure is low as it only affects one device. However, if the hub or switch goes bang the whole network is down.

**Bus topology** is where all hosts are connected via one big pipe, all the devices can directly connect to one another with no device hops between them. However, if there is a fault in the Bus it affects all the devices.

**Extended Star** is a hybrid of star and bus topologies, where two star networks are connected to one another via a bus.

**Ring topology** is where all hosts are connected to each other directly via network cards to the hosts next to one another. The advantages are that there is no need for a central network device such as a hub or switch. If the ring network is multi-directional, it can handle cable failure. However, if a host in the network fails, the network fails, it is also difficult to extend.