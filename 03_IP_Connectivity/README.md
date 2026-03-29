# 03 — IP Connectivity

## Overview

This section demonstrates a progressive understanding of how routers learn, store, and forward traffic across networks.
 
The labs begin with **Static Routing** — building a foundational understanding of how routes are manually defined and how routers make forwarding decisions. From there, the section moves into **OSPF**, covering both single-area and multi-area designs to show how dynamic routing protocols automate route exchange at scale. The section concludes with **Router on a Stick**, applying Layer 3 routing concepts to a switched environment by enabling communication between hosts on separate VLANs through a single router interface.
## Labs

| # | Lab | Description |
|---|-----|-------------|
| 01 | Static Routing| Two routers configured with static routes over a `/30` point-to-point link to achieve full end-to-end connectivity between two PC networks |
| 02 | OSPF — Single & Multi-Area)| Four routers running OSPF across Area 0 and Area 1, with R3 as the ABR enabling dynamic route exchange between all segments |
| 03 | Router on a Stick | Inter-VLAN routing configured on a single router using 802.1Q subinterfaces and a trunk link from the switch |

---

## Skills Demonstrated

| Category | Skills |
|----------|--------|
| Static Routing | `ip route`, next-hop addressing, bidirectional route configuration |
| OSPF | OSPFv2, single-area, multi-area, ABR, neighbor adjacencies, wildcard masks |
| Inter-VLAN Routing | 802.1Q trunking, `encapsulation dot1Q`, subinterface configuration |
| Switching | Access ports, trunk ports, VLAN assignment |
| Verification | `show ip route`, `show ip ospf neighbor`, `show vlan brief`, `ping` |

---

## Tools Used

- Cisco Packet Tracer
- Cisco IOS CLI

---

*Documented by Salim Aden*
