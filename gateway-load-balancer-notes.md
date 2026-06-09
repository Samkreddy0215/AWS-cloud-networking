# AWS Gateway Load Balancer (GWLB)

## What is GWLB?

AWS Gateway Load Balancer (GWLB) enables deployment, scaling, and management of virtual network appliances such as firewalls, intrusion detection systems (IDS), and intrusion prevention systems (IPS).

## Features

- Traffic inspection
- Security appliance integration
- High availability
- Automatic scaling
- Transparent traffic forwarding

## Components

### Gateway Load Balancer

Distributes traffic across security appliances.

### Gateway Load Balancer Endpoint (GWLBE)

Provides a private connection between VPCs and GWLB.

### Security Appliances

Examples:

- Palo Alto VM-Series
- Fortinet FortiGate
- Check Point
- Cisco Secure Firewall

## Traffic Flow

Client
→ GWLB Endpoint
→ GWLB
→ Security Appliance
→ Application

## Benefits

- Centralized security
- High availability
- Traffic inspection
- Simplified architecture
- Scalable firewall deployments

## GWLB vs ALB vs NLB

| Feature | ALB | NLB | GWLB |
|----------|----------|----------|----------|
| Layer | Layer 7 | Layer 4 | Layer 3 |
| HTTP Routing | Yes | No | No |
| TCP/UDP Support | Limited | Yes | Yes |
| Security Inspection | No | No | Yes |
| Firewall Integration | No | No | Yes |

## Enterprise Use Cases

- Firewall insertion
- IDS/IPS deployment
- Threat inspection
- East-West traffic inspection
- Centralized security services
