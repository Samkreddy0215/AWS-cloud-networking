# AWS Transit Gateway (TGW)

## What is Transit Gateway?

AWS Transit Gateway is a central networking hub that connects multiple VPCs, VPNs, and Direct Connect connections.

---

## Why Use Transit Gateway?

Transit Gateway simplifies network connectivity by providing a hub-and-spoke architecture.

Benefits:

* Centralized connectivity
* Simplified routing
* Easier management
* Enterprise scalability

---

## Hub-and-Spoke Architecture

Example:

```
       TGW
     /  |  \
    /   |   \
 VPC-A VPC-B VPC-C
```

All VPCs connect to a central Transit Gateway.

---

## Transit Gateway Attachments

Transit Gateway supports:

* VPC Attachments
* VPN Attachments
* Direct Connect Attachments

---

## Route Propagation

Transit Gateway can automatically learn routes from attached networks.

Example:

10.0.0.0/16

192.168.0.0/16

These routes are propagated into the Transit Gateway Route Table.

---

## Transit Gateway vs VPC Peering

VPC Peering:

* Best for small environments
* Point-to-point connectivity

Transit Gateway:

* Best for enterprise environments
* Centralized connectivity
* Easier management

---

## Enterprise Use Cases

* Multi-VPC environments
* Hybrid cloud connectivity
* VPN integration
* Direct Connect integration
* Centralized network architecture

---

## Key Points

* TGW is a central networking hub
* Connects multiple VPCs
* Supports VPN and Direct Connect
* Uses route tables
* Scales better than VPC Peering
