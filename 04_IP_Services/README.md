# 04 — IP Services

---

## Overview

IP Services covers the network protocols and features that support real-world enterprise deployments. Four labs are included:

- **NAT (PAT Overload)** — configured R1 to translate private inside addresses to a single public IP, allowing PC1 to reach a public server at `8.8.8.8`
- **DHCP** — configured a Cisco router as a DHCP server to dynamically assign IP addresses, subnet masks, and default gateways to end hosts without manual configuration
- **HSRP** — deployed between two routers sharing a virtual gateway IP of `192.168.1.1`, ensuring LAN connectivity is maintained if the active router fails
- **NTP + DNS** — configured Server1 as an NTP and DNS server, synchronizing R1's clock and enabling PC1 to resolve `www.salims-lab` to an IP address

---

## Labs

| # | Lab | Description |
|---|-----|-------------|
| 01 | NAT — PAT Overload | Configured PAT on R1 to translate inside private addresses to a single public IP, allowing PC1 to reach a public server at `8.8.8.8` |
| 02 | DHCP| Configured a Cisco router as a DHCP server to dynamically assign IP addresses, subnet masks, and default gateways to end hosts |
| 03 | HSRP | Configured Hot Standby Router Protocol between two routers to provide default gateway redundancy for the LAN |
| 04 | NTP + DNS | Configured NTP for clock synchronization across routers and DNS for hostname-to-IP resolution |

---

## Skills Demonstrated

| Category | Skills |
|----------|--------|
| NAT / PAT | Inside/outside interface config, access lists, overload translation |
| DHCP | DHCP pool configuration, excluded addresses, dynamic IP assignment |
| HSRP | Virtual IP, priority, preempt, active/standby election |
| NTP | NTP server and client configuration, clock synchronization |
| DNS | DNS server setup, hostname resolution |
| Verification | `show ip nat translations`, `show ip dhcp binding`, `show standby`, `show ntp status` |

---

## Tools Used

- Cisco Packet Tracer
- Cisco IOS CLI

---

*Documented by Salim Aden*
