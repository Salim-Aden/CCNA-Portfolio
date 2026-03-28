# 02 Network Access

## Overview
This section covers switching technologies including VLANs, trunking, STP, EtherChannel using LACP , and port security.

---
## Labs in This Section

| Lab | Technology | What I Configured |
|-----|------------|-------------------|
| **01_VLANs_Trunking** | VLANs | Created VLAN 10 (Engineering) and VLAN 20 (Sales). Assigned access ports to separate broadcast domains. |
| **02_STP_Configuration** | Spanning Tree | Set SW1 as root bridge, SW2 as secondary. Verified blocked ports to prevent loops. |
| **03_EtherChannel_LACP** | Link Aggregation | Bundled two physical links into one logical trunk using LACP. |
| **04_Port_Security** | Access Security | Limited MAC addresses to 2 per port, configured violation shutdown, enabled sticky MAC learning. |

---

## Skills Demonstrated

| Category | Skills |
|----------|--------|
| **VLANs** | Creation, naming, access port assignment, broadcast domain segmentation |
| **Trunking** | 802.1Q encapsulation, allowed VLANs |
| **STP** | Root bridge election, priority values, port states (Root, Designated, Alternate), PortFast, BPDUguard |
| **EtherChannel** | LACP protocol, port-channel interface, load balancing |
| **Port Security** | Maximum MAC addresses, violation modes (shutdown, restrict, protect), sticky MAC |

---
*Documented by Salim Aden — CCNA Certified*
