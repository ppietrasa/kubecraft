A valid looking route can still black-hole traffic if the next hop in the
routing table points to a non-existing/down host.  In such cases, after
diagnosing the last working hop. I might check the hops routing table -> note
the next hop target and check the ARP table. Do I see my next hop target there?
If not the entry in the routing table is likely incorrect.  I could also
probably just ping the next hop target from there.

BTW. In SR Linux I don't see a failed resolution in the ARP table. I simply see no entry:
+----------------+----------------+-----------------+----------------+-------------------------------+------------------------------------------------------------+
|   Interface    |  Subinterface  |    Neighbor     |     Origin     |      Link layer address       |                           Expiry                           |
+================+================+=================+================+===============================+============================================================+
| ethernet-1/1   |              0 |        10.1.1.2 |        dynamic | AA:C1:AB:2A:0A:36             | 3 hours from now                                           |
| ethernet-1/2   |              0 |        10.1.2.2 |        dynamic | 1A:34:04:FF:00:01             | 34 minutes from now                                        |
| mgmt0          |              0 |     172.20.20.1 |        dynamic | 02:42:6D:31:D8:0F             | 32 minutes from now                                        |
+----------------+----------------+-----------------+----------------+-------------------------------+------------------------------------------------------------

A mainstream linux would mark a failed resolution with
"incomplete" in `apn -n`.
