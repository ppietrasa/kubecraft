Routing table before BGP (only local routes):

--------------------+------+-----------+---------------------+---------+---------+--------+-----------+------------+------------+------------+---------------+
|       Prefix       |  ID  |   Route   |     Route Owner     | Active  | Origin  | Metric |   Pref    |  Next-hop  |  Next-hop  |   Backup   | Backup Next-  |
|                    |      |   Type    |                     |         | Network |        |           |   (Type)   | Interface  |  Next-hop  | hop Interface |
|                    |      |           |                     |         | Instanc |        |           |            |            |   (Type)   |               |
|                    |      |           |                     |         |    e    |        |           |            |            |            |               |
+====================+======+===========+=====================+=========+=========+========+===========+============+============+============+===============+
| 10.1.1.0/24        | 2    | local     | net_inst_mgr        | True    | default | 0      | 0         | 10.1.1.1   | ethernet-  |            |               |
|                    |      |           |                     |         |         |        |           | (direct)   | 1/1.0      |            |               |
| 10.1.1.1/32        | 2    | host      | net_inst_mgr        | True    | default | 0      | 0         | None       | None       |            |               |
|                    |      |           |                     |         |         |        |           | (extract)  |            |            |               |
| 10.1.1.255/32      | 2    | host      | net_inst_mgr        | True    | default | 0      | 0         | None (broa |            |            |               |
|                    |      |           |                     |         |         |        |           | dcast)     |            |            |               |
| 10.1.2.0/24        | 3    | local     | net_inst_mgr        | True    | default | 0      | 0         | 10.1.2.1   | ethernet-  |            |               |
|                    |      |           |                     |         |         |        |           | (direct)   | 1/2.0      |            |               |
| 10.1.2.1/32        | 3    | host      | net_inst_mgr        | True    | default | 0      | 0         | None       | None       |            |               |
|                    |      |           |                     |         |         |        |           | (extract)  |            |            |               |
| 10.1.2.255/32      | 3    | host      | net_inst_mgr        | True    | default | 0      | 0         | None (broa |            |            |               |
|                    |      |           |                     |         |         |        |           | dcast)     |            |            |               |
| 10.1.3.0/24        | 4    | local     | net_inst_mgr        | True    | default | 0      | 0         | 10.1.3.1   | ethernet-  |            |               |
|                    |      |           |                     |         |         |        |           | (direct)   | 1/3.0      |            |               |
| 10.1.3.1/32        | 4    | host      | net_inst_mgr        | True    | default | 0      | 0         | None       | None       |            |               |
|                    |      |           |                     |         |         |        |           | (extract)  |            |            |               |
| 10.1.3.255/32      | 4    | host      | net_inst_mgr        | True    | default | 0      | 0         | None (broa |            |            |               |
|                    |      |           |                     |         |         |        |           | dcast)     |            |            |               |
+--------------------+------+-----------+---------------------+---------+---------+--------+-----------+------------+------------+------------+---------------+

Routing table after BGP (local + bgp routes):

+--------------------+------+-----------+---------------------+---------+---------+--------+-----------+------------+------------+------------+---------------+
|       Prefix       |  ID  |   Route   |     Route Owner     | Active  | Origin  | Metric |   Pref    |  Next-hop  |  Next-hop  |   Backup   | Backup Next-  |
|                    |      |   Type    |                     |         | Network |        |           |   (Type)   | Interface  |  Next-hop  | hop Interface |
|                    |      |           |                     |         | Instanc |        |           |            |            |   (Type)   |               |
|                    |      |           |                     |         |    e    |        |           |            |            |            |               |
+====================+======+===========+=====================+=========+=========+========+===========+============+============+============+===============+
| 10.1.1.0/24        | 2    | local     | net_inst_mgr        | True    | default | 0      | 0         | 10.1.1.1   | ethernet-  |            |               |
|                    |      |           |                     |         |         |        |           | (direct)   | 1/1.0      |            |               |
| 10.1.1.1/32        | 2    | host      | net_inst_mgr        | True    | default | 0      | 0         | None       | None       |            |               |
|                    |      |           |                     |         |         |        |           | (extract)  |            |            |               |
| 10.1.1.255/32      | 2    | host      | net_inst_mgr        | True    | default | 0      | 0         | None (broa |            |            |               |
|                    |      |           |                     |         |         |        |           | dcast)     |            |            |               |
| 10.1.2.0/24        | 3    | local     | net_inst_mgr        | True    | default | 0      | 0         | 10.1.2.1   | ethernet-  |            |               |
|                    |      |           |                     |         |         |        |           | (direct)   | 1/2.0      |            |               |
| 10.1.2.1/32        | 3    | host      | net_inst_mgr        | True    | default | 0      | 0         | None       | None       |            |               |
|                    |      |           |                     |         |         |        |           | (extract)  |            |            |               |
| 10.1.2.255/32      | 3    | host      | net_inst_mgr        | True    | default | 0      | 0         | None (broa |            |            |               |
|                    |      |           |                     |         |         |        |           | dcast)     |            |            |               |
| 10.1.3.0/24        | 4    | local     | net_inst_mgr        | True    | default | 0      | 0         | 10.1.3.1   | ethernet-  |            |               |
|                    |      |           |                     |         |         |        |           | (direct)   | 1/3.0      |            |               |
| 10.1.3.1/32        | 4    | host      | net_inst_mgr        | True    | default | 0      | 0         | None       | None       |            |               |
|                    |      |           |                     |         |         |        |           | (extract)  |            |            |               |
| 10.1.3.255/32      | 4    | host      | net_inst_mgr        | True    | default | 0      | 0         | None (broa |            |            |               |
|                    |      |           |                     |         |         |        |           | dcast)     |            |            |               |
| 10.1.4.0/24        | 0    | bgp       | bgp_mgr             | True    | default | 0      | 170       | 10.1.2.0/2 | ethernet-  |            |               |
|                    |      |           |                     |         |         |        |           | 4 (indirec | 1/2.0      |            |               |
|                    |      |           |                     |         |         |        |           | t/local)   |            |            |               |
| 10.1.5.0/24        | 0    | bgp       | bgp_mgr             | True    | default | 0      | 170       | 10.1.3.0/2 | ethernet-  |            |               |
|                    |      |           |                     |         |         |        |           | 4 (indirec | 1/3.0      |            |               |
|                    |      |           |                     |         |         |        |           | t/local)   |            |            |               |
+--------------------+------+-----------+---------------------+---------+---------+--------+-----------+------------+------------+------------+---------------+

All cross-subnet pings succeeding:

docker exec clab-dynamic-routing-bgp-host1 ping -c 3 10.1.4.2
PING 10.1.4.2 (10.1.4.2) 56(84) bytes of data.
64 bytes from 10.1.4.2: icmp_seq=1 ttl=62 time=103 ms
64 bytes from 10.1.4.2: icmp_seq=2 ttl=62 time=0.548 ms
64 bytes from 10.1.4.2: icmp_seq=3 ttl=62 time=0.462 ms

$ docker exec clab-dynamic-routing-bgp-host1 ping -c 3 10.1.5.2
PING 10.1.5.2 (10.1.5.2) 56(84) bytes of data.
64 bytes from 10.1.5.2: icmp_seq=1 ttl=62 time=104 ms
64 bytes from 10.1.5.2: icmp_seq=2 ttl=62 time=0.608 ms
64 bytes from 10.1.5.2: icmp_seq=3 ttl=62 time=0.687 ms

$ docker exec clab-dynamic-routing-bgp-host2 ping -c 3 10.1.5.2
PING 10.1.5.2 (10.1.5.2) 56(84) bytes of data.
64 bytes from 10.1.5.2: icmp_seq=1 ttl=61 time=0.499 ms
64 bytes from 10.1.5.2: icmp_seq=2 ttl=61 time=0.670 ms
64 bytes from 10.1.5.2: icmp_seq=3 ttl=61 time=0.902 ms

