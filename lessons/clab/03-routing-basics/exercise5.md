$ docker exec clab-routing-basics-host1 traceroute -n -w 2 10.1.5.2
traceroute to 10.1.5.2 (10.1.5.2), 30 hops max, 60 byte packets
 1  10.1.1.1  1.144 ms  1.106 ms  1.090 ms
 2  10.1.2.2  0.585 ms  1.393 ms  1.381 ms
 3  10.1.2.1  1.007 ms  0.994 ms  0.979 ms
 4  10.1.2.2  1.384 ms  1.377 ms  1.371 ms
 5  * * *
 6  10.1.2.2  1.312 ms  0.951 ms  1.318 ms
 7  * * *
 8  10.1.2.2  1.203 ms * *
 9  * * *
10  * * *
11  * * *
12  10.1.2.2  5.987 ms  6.004 ms  6.125 ms
13  * * *
14  10.1.2.2  6.378 ms  6.412 ms  6.390 ms
15  * * *
16  10.1.2.2  7.126 ms  7.116 ms  7.119 ms
17  * * *
18  10.1.2.2  3.825 ms * *
19  * * *
20  * 10.1.2.2  4.823 ms  4.800 ms
21  * * *
22  10.1.2.2  5.776 ms  5.791 ms  6.307 ms
23  * * *
24  10.1.2.2  6.789 ms  6.734 ms  7.436 ms
25  * * *
26  10.1.2.2  7.534 ms  7.484 ms *
27  * * *
28  * * *
29  * * *
30  10.1.2.2  5.061 ms  5.071 ms  4.705 ms


Each IP packet has a TTL field. Eeach router/hop is obliged to decrease the TTL
value by 1. When TTL reaches 0 the packet is discarded and the router if it wants
to play nice may send back a Time Exceeded message back to source.

Traceroute uses this feature. It sends out probes with TTL starting at 1 and
increasing. This allows to trace the path a packet takes.
