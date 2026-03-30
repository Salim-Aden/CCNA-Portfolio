# 06 — Automation & Programmability

---

## Overview

This section covers the **Automation & Programmability**. These topics involve APIs, scripting, and automation tools that go beyond router/switch CLI. Understanding is demonstrated through concept documentation and practical examples — there are no Packet Tracer labs for this domain.

---

## What I Learned and Can Demonstrate (Conceptual)

- Traditional CLI-based networking vs. controller-based SDN architecture
- REST APIs and how network devices expose them for programmatic management
- HTTP methods (GET, POST, PUT, DELETE, PATCH) and their role in CRUD operations
- JSON and YAML data formats for API communication and automation
- Configuration management tools: Ansible, Terraform, Puppet, Chef
- NETCONF/RESTCONF protocols for network device configuration
- Cisco DNA Center as an enterprise SDN controller
- End-to-end automation workflow from engineer intent to device configuration

---

## Traditional vs Controller-Based Networking

| Feature | Traditional Networking | Controller-Based (SDN) |
|---------|----------------------|------------------------|
| **Configuration** | Device-by-device via CLI | Centralized via controller |
| **Management** | Manual, per-device | Automated, policy-driven |
| **Scalability** | Limited — time-intensive | High — changes pushed at scale |
| **Visibility** | Per-device `show` commands | Centralized dashboard |
| **Consistency** | Prone to human error | Enforced through automation |
| **Control Plane** | Distributed on each device | Centralized on controller |
| **Examples** | Cisco IOS CLI | Cisco DNA Center, APIC |

In traditional networking, each router and switch is configured individually. In controller-based networking, a central SDN controller holds network intelligence and pushes configuration to devices automatically — separating the **control plane** from the **data plane**.

---

## REST APIs

A **REST API** (Representational State Transfer) allows software applications to communicate with network devices over HTTP. Modern network platforms like Cisco DNA Center and Meraki expose REST APIs for automation of configuration, monitoring, and troubleshooting without CLI.

### HTTP Methods (CRUD Mapping)

| HTTP Method | CRUD Operation | Purpose | Example |
|-------------|---------------|---------|---------|
| **GET** | Read | Retrieve data from device | `GET /device` |
| **POST** | Create | Add new configuration | `POST /device` |
| **PUT** | Update (full) | Replace entire resource | `PUT /device/1` |
| **PATCH** | Update (partial) | Modify part of resource | `PATCH /device/1` |
| **DELETE** | Delete | Remove configuration | `DELETE /device/1` |

### Example REST Request (Cisco DNA Center)
"https://sandboxdnac.cisco.com/dna/intent/api/v1/network-device"
-"Authorization: Bearer <token>"
-"Content-Type: application/json"


### Example JSON Response

```json
{
  "response": [
    {
      "hostname": "R1",
      "managementIpAddress": "192.168.1.1",
      "platformId": "CISCO2911/K9",
      "softwareVersion": "15.1",
      "reachabilityStatus": "Reachable"
    }
  ]
}
The API returns structured data that can be parsed and acted upon programmatically — no manual CLI output parsing required.

Data Formats: JSON & YAML
JSON (JavaScript Object Notation)
Standard data format for REST APIs. Uses key-value pairs, brackets {} for objects, brackets [] for arrays.

json
{
  "interface": {
    "name": "GigabitEthernet0/0",
    "ip_address": "192.168.1.1",
    "subnet_mask": "255.255.255.0",
    "status": "up",
    "description": "LAN interface"
  }
}

###YAML(YAML Ain't Markup Language)

Used by Ansible for playbooks. Uses indentation instead of brackets — more human-readable.

yaml
---
interface:
  name: GigabitEthernet0/0
  ip_address: 192.168.1.1
  subnet_mask: 255.255.255.0
  status: up
  description: LAN interface
Configuration Management Tools
Tool	Type	Architecture	Use Case
Ansible	Agentless	Push model via SSH/API	Most popular for network automation — no agent required on devices
Terraform	Infrastructure as Code	Declarative	Provision network infrastructure — defines desired end state
Puppet	Agent-based	Pull model	Enforce consistent config across large environments
Chef	Agent-based	Pull model	Automate infrastructure using Ruby-based recipes
Ansible is the most widely used tool for network automation due to its agentless architecture and native support for Cisco IOS, NX-OS, and other network platforms.

Example Ansible Playbook (YAML)
yaml
---
- name: Configure OSPF on Router
  hosts: routers
  connection: network_cli
  tasks:
    - name: Enable OSPF on interface
      ios_config:
        lines:
          - router ospf 1
          - network 192.168.1.0 0.0.0.255 area 0
        parents: interface GigabitEthernet0/0


### NETCONF & RESTCONF
Protocol	Transport	Data Format	Use Case
NETCONF	SSH (port 830)	XML	Standard for network configuration — replaces CLI
RESTCONF	HTTP/HTTPS	JSON/XML	RESTful version of NETCONF for web APIs
These protocols provide structured configuration management, unlike CLI which relies on text parsing. They are programmable, transactional, and provide built-in validation.

###Cisco DNA Center

Cisco DNA Center is the SDN controller for enterprise networks. It provides:

Feature	Purpose
Automation=Day to Day operations
Assurance	Network health monitoring and analytics
SDA (Software-Defined Access)=Fabric-based network segmentation
REST API=Programmatic access for automation
DNA Center's northbound REST API=allows applications to request network services without manual CLI configuration.

End-to-End Automation Workflow

Network Engineer
      │
      ▼
Automation Tool (Ansible Playbook)
      │
      ▼
REST API Call (HTTP + JSON/YAML payload)
      │
      ▼
Network Controller (Cisco DNA Center)
      │
      ▼
NETCONF/RESTCONF to individual devices
      │
      ▼
R1, SW1, SW2, etc. configured simultaneously
Engineer defines desired state in a playbook or script

Automation tool formats request and sends via REST API

Controller receives and validates the payload

Configuration is deployed to all target devices simultaneously via NETCONF/RESTCONF

API response confirms success or returns error details


Concepts that i learned
SDN	Control plane separated from data plane; centralized management
REST API	HTTP methods (GET, POST, PUT, PATCH, DELETE) for CRUD operations
JSON	Key-value pair data format; used in REST APIs
YAML	Indentation-based format; used in Ansible playbooks
Ansible	Agentless, push model, YAML playbooks, SSH/API
NETCONF/RESTCONF	Structured protocols for network configuration (vs CLI)
Cisco DNA Center	Enterprise SDN controller with northbound REST API


*Documented by Salim Aden *
