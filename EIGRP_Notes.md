# EIGRP Notes

Cisco added some of the features from link-state routing protocols to EIGRP which makes it far more advanced than a true distance vector routing protocol like RIP. This is why (probably the marketing department) calls EIGRP an **advanced distance vector or hybrid routing protocol** .

## Link State Protocol

- Link State knows every thing about the network.
- RIP is a true distance vector routing protocol and very simple:
- No neighbor discovery.
- Periodic updates.
- Vulnerable to loops.
- Simple metric (hop count).

## Distance Vector Protocol 1

- Distance Vector is what the neighbor router has told it.

Cisco added **some of the features from link-state routing protocols to EIGRP** which makes it far more advanced than a true distance vector routing protocol like RIP. This is why (probably the marketing department) calls **EIGRP an advanced distance vector or hybrid routing protocol**.

> - EIGRP does not use broadcast packets to send information to other neighbors but will use multicast or unicast.
> - Besides IPv4 you can also use EIGRP to route IPv6 or even some older network layer protocols like IPX or AppleTalk.
> - EIGRP is **100% loop-free** and I'm going to show you why this is true.

**EIGRP Protocol Number is 8**

# TEST MESSAGE 2

EIGRP runs **directly on top of the IP header**. If you look at the picture above you see we have a frame header (for example an Ethernet Frame), an IP Header (we are using IPv4) and inside the IP packet you'll find EIGRP.

```sh
R1#sh ip eigrp neighbors
EIGRP-IPv4 Neighbors for AS(100)
H   Address                 Interface              Hold Uptime   SRTT   RTO  Q  Seq
                                                   (sec)         (ms)       Cnt Num
0   192.168.1.2             Et1/3                    14 01:17:39   31   186  0  17
R1#


R1#sh ip protocols
*** IP Routing is NSF aware ***

Routing Protocol is "eigrp 100"
  Outgoing update filter list for all interfaces is not set
  Incoming update filter list for all interfaces is not set
  Default networks flagged in outgoing updates
  Default networks accepted from incoming updates
  EIGRP-IPv4 Protocol for AS(100)
    Metric weight K1=1, K2=0, K3=1, K4=0, K5=0
    NSF-aware route hold timer is 240
    Router-ID: 10.0.0.1
    Topology : 0 (base)
      Active Timer: 3 min
      Distance: internal 90 external 170
      Maximum path: 4
      Maximum hopcount 100
      Maximum metric variance 1

  Automatic Summarization: disabled
  Maximum path: 4
  Routing for Networks:
    0.0.0.0
  Routing Information Sources:
    Gateway         Distance      Last Update
    192.168.1.2           90      01:09:55
  Distance: internal 90 external 170

R1#
```

ssdasdsdyll `_config.yml` configuration file.
