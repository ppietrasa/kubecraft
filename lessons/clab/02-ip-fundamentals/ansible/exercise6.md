Local subnet is the one my IP and subnet mask pair specifies. Hosts within the
local subnet are typically on the same physical link (Ethernet) or the same
network segment. These can directly talk to each other on the link layer. On
Ethernet they can find out each others MACs via ARP. In contrast, hosts on the
remote subnet, as the name suggests, are not in the vicinity (not on the same
link) and the devices/hosts on the local subnet need to hand over packets to
such a network to a gateway for further routing.
