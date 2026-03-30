# 05 — Security Fundamentals

---

## Overview

Security Fundamentals covers the essential tools and techniques used to protect network infrastructure. Three labs are included:

- **ACL Security** — configured Standard and Extended ACLs on R1 to block traffic from LAN2 reaching LAN1 and deny HTTP traffic, verified with hit counters and blocked pings
- **SSH** — hardened remote access on R1 by enabling SSH with RSA encryption, local user authentication, and restricting VTY lines to SSH-only transport
- **Port Security** — enabled sticky MAC learning and shutdown violation mode on SW1's `Fa0/1` to prevent unauthorized devices from connecting to the switch port

---

## Labs

| # | Lab | Description |
|---|-----|-------------|
| 01 | ACL Security| Standard ACL blocks LAN2 from reaching LAN1; Extended ACL blocks HTTP traffic from LAN2 |
| 02 | SSH| Secure router management configured with RSA encryption, local authentication, and SSH-only VTY access |
| 03 | Port Security| Switch port hardened with sticky MAC learning and shutdown violation mode to block unauthorized devices |

---

## Skills Demonstrated

| Category | Skills |
|----------|--------|
| ACLs | Standard ACL, Extended ACL, ACL placement, `ip access-group`, hit counter verification |
| SSH | RSA key generation, domain name config, local user auth, VTY hardening |
| Port Security | Sticky MAC, violation mode, `show port-security`, access port lockdown |
| Verification | `show access-lists`, `show ip ssh`, `show crypto key mypubkey rsa`, `show port-security` |

---

## Tools Used

- Cisco Packet Tracer
- Cisco IOS CLI

---

*Documented by Salim Aden*
