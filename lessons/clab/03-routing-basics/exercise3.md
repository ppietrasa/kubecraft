The diagnostic commands:

host 1 is: 10.1.1.2

from host2 to host3:
$ docker exec clab-routing-basics-host2 traceroute 10.1.5.2
traceroute to 10.1.5.2 (10.1.5.2), 30 hops max, 60 byte packets
 1  10.1.4.1 (10.1.4.1)  1.171 ms !N  1.098 ms !N  1.080 ms !N

 shows that the packets cannot exit srl2 (10.1.4.1)

from host3 to host2:
$ docker exec clab-routing-basics-host3 traceroute 10.1.4.2
traceroute to 10.1.4.2 (10.1.4.2), 30 hops max, 60 byte packets
 1  10.1.5.1 (10.1.5.1)  1.291 ms  1.268 ms  1.259 ms
 2  10.1.3.1 (10.1.3.1)  0.749 ms  0.753 ms  0.746 ms
 3  * * *


 shows that the packets reach 10.1.3.1 srl1 (10.1.3.1)


The missing route breaks both directions as ping packages need to
return. These likely reach their destination when pinging host3
from host2, but the answers of host2 are lost.
