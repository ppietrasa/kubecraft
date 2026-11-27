Before traceroute output:
```
$ docker exec clab-dynamic-routing-bgp-host2 traceroute -n -w 2 10.1.5.2
traceroute to 10.1.5.2 (10.1.5.2), 30 hops max, 60 byte packets
 1  10.1.4.1  1.070 ms  1.032 ms  1.070 ms
 2  10.1.2.1  1.016 ms  1.010 ms  1.004 ms
 3  10.1.3.2  0.885 ms  0.885 ms  0.885 ms
 4  10.1.5.2  0.548 ms  0.718 ms  0.732 ms
```

After traceroute output:
```
$ docker exec clab-dynamic-routing-bgp-host2 traceroute -n -w 2 10.1.5.2
traceroute to 10.1.5.2 (10.1.5.2), 30 hops max, 60 byte packets
 1  10.1.4.1  0.679 ms  0.643 ms  0.616 ms
 2  10.1.6.2  0.989 ms  0.980 ms  0.979 ms
 3  10.1.5.2  0.520 ms  0.591 ms  0.622 ms
```

BGP route detail:
```
$ docker exec -it clab-dynamic-routing-bgp-srl2 sr_cli "show network-instance default protocols bgp routes ipv4 prefix 10.1.5.0/24 detail"
----------------------------------------------------------------------------------------------------------------------------------------------------------------------
Show report for the BGP routes to network "10.1.5.0/24" network-instance  "default"
----------------------------------------------------------------------------------------------------------------------------------------------------------------------
Network: 10.1.5.0/24
Received Paths: 2
  Path 1: <Valid,>
    Route source    : neighbor 10.1.2.1
    Route Preference: MED is -, No LocalPref
    BGP next-hop    : 10.1.2.1
    Path            :  i **[65001, 65003]**
    Communities     : None
    RR Attributes   : No Originator-ID, Cluster-List is [ - ]
    Aggregation     : Not an aggregate route
    Unknown Attr    : None
    Invalid Reason  : None
    Tie Break Reason: as-path-length
  Path 2: <Best,Valid,Used,>
    Route source    : neighbor 10.1.6.2
    Route Preference: MED is -, No LocalPref
    BGP next-hop    : 10.1.6.2
    Path            :  i **[65003]**
    Communities     : None
    RR Attributes   : No Originator-ID, Cluster-List is [ - ]
    Aggregation     : Not an aggregate route
    Unknown Attr    : None
    Invalid Reason  : None
    Tie Break Reason: none

Path 2 was advertised to: 
[ 10.1.2.1 ]
Route Preference: MED is -, No LocalPref
Path            :  i [65002, 65003]
Communities     : None
RR Attributes   : No Originator-ID, Cluster-List is [ - ]
Aggregation     : Not an aggregate route
Unknown Attr    : None
```

Shortest AS path decided the winner ( marked ** )
