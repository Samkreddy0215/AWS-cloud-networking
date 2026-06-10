# AWS PrivateLink

## What is AWS PrivateLink?

AWS PrivateLink enables private connectivity between VPCs, AWS services, and third-party applications without exposing traffic to the public internet.

## Benefits

- Private communication
- Improved security
- No Internet Gateway required
- No NAT Gateway required
- Reduced attack surface

## Components

### Service Provider

Provides an application or service through a Network Load Balancer (NLB).

### Service Consumer

Connects privately using an Interface Endpoint.

### Interface Endpoint

Creates Elastic Network Interfaces (ENIs) inside a VPC.

## How It Works

Consumer VPC
↓
Interface Endpoint
↓
AWS PrivateLink
↓
Provider Service

Traffic remains on the AWS private network.

## Use Cases

- Access SaaS applications privately
- Connect applications between VPCs
- Share internal services across accounts
- Secure partner connectivity

## PrivateLink vs VPC Peering

| Feature | PrivateLink | VPC Peering |
|----------|-------------|-------------|
| Private Connectivity | Yes | Yes |
| Transitive Routing | No | No |
| Service Sharing | Yes | No |
| CIDR Overlap Support | Yes | No |

## Key Points

- Uses Interface Endpoints
- Supports private application access
- Enhances security
- Commonly used for SaaS connectivity
