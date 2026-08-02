# AWS Gateway API TCPRoute and GRPCRoute on Amazon EKS

## Overview

AWS Gateway API extends Kubernetes networking beyond HTTP traffic by supporting additional route types such as TCPRoute and GRPCRoute. These resources allow organizations to securely expose TCP-based applications and gRPC services running on Amazon EKS while leveraging AWS networking infrastructure.

Gateway API provides a modern, flexible, and scalable way to manage application traffic compared to traditional Kubernetes Ingress resources.

---

# Architecture Diagram

```
                    Client
                      │
                      ▼
          AWS Application Load Balancer
                      │
                GatewayClass
                      │
                  Gateway
        ┌─────────────┼─────────────┐
        ▼                           ▼
    TCPRoute                  GRPCRoute
        │                           │
        ▼                           ▼
   TCP Application           gRPC Service
        │                           │
        └──────── Amazon EKS ───────┘
```

---

# What is Gateway API?

Gateway API is the next-generation Kubernetes networking API that provides advanced routing, traffic management, and policy control for applications running in Kubernetes clusters.

Benefits include:

- Advanced routing
- Better security
- Role separation
- Traffic management
- Enterprise scalability

---

# What is TCPRoute?

TCPRoute routes Layer 4 TCP traffic directly to backend services.

Common workloads include:

- Databases
- Message queues
- Custom enterprise applications
- Legacy TCP services

---

# What is GRPCRoute?

GRPCRoute routes gRPC traffic between clients and backend services.

Common workloads include:

- Microservices
- Internal APIs
- Financial transaction systems
- High-performance applications

---

# HTTPRoute vs TCPRoute vs GRPCRoute

| Feature | HTTPRoute | TCPRoute | GRPCRoute |
|----------|-----------|----------|------------|
| Protocol | HTTP/HTTPS | TCP | gRPC |
| Layer | Layer 7 | Layer 4 | Layer 7 |
| Path Routing | Yes | No | Yes |
| Header Matching | Yes | No | Yes |
| gRPC Support | No | No | Yes |

---

# Gateway and GatewayClass

## GatewayClass

Defines which controller manages the Gateway.

Example:

AWS Load Balancer Controller

---

## Gateway

Acts as the entry point for incoming application traffic.

Responsible for:

- Listener configuration
- TLS
- Routing
- Security

---

# Listener Configuration

Gateway listeners define:

- Protocol
- Port
- TLS settings
- Route attachment

Example:

- HTTP
- HTTPS
- TCP
- TLS

---

# Integration with Amazon EKS

Gateway API integrates with:

- Amazon EKS
- Kubernetes Services
- Pods
- AWS Load Balancer Controller
- Application Load Balancer

---

# AWS Load Balancer Controller

The controller automatically provisions:

- Application Load Balancer
- Listener Rules
- Target Groups

It synchronizes Gateway API resources with AWS infrastructure.

---

# Enterprise Architecture

```
Internet
    │
    ▼
AWS Load Balancer
    │
 Gateway
    │
 ┌──┴─────────────┐
 ▼                ▼
TCPRoute     GRPCRoute
 │                │
 ▼                ▼
TCP App      gRPC Service
 │                │
 └──── Amazon EKS ────┘
```

---

# Security Considerations

- Use TLS encryption.
- Apply IAM least privilege.
- Use AWS Certificate Manager (ACM).
- Monitor traffic using CloudWatch.
- Enable logging.
- Restrict unnecessary listener ports.

---

# Enterprise Use Cases

- Banking
- Healthcare
- Government
- Retail
- SaaS Platforms
- Enterprise APIs
- Microservices

---

# Best Practices

- Use HTTPS whenever possible.
- Enable TLS certificates.
- Monitor application health.
- Use Gateway API instead of legacy Ingress for new deployments.
- Test routing changes before production rollout.
- Keep AWS Load Balancer Controller updated.

---

# Common Troubleshooting

## TCPRoute Not Working

Verify:

- Gateway configuration
- Listener configuration
- Backend service
- Security Groups

---

## GRPCRoute Fails

Check:

- gRPC service configuration
- TLS certificates
- Backend application health

---

## Load Balancer Not Created

Verify:

- AWS Load Balancer Controller
- IAM permissions
- GatewayClass configuration

---

## Connection Timeout

Review:

- Security Groups
- Network ACLs
- Route Tables
- Pod health

---

# Advantages

- Modern Kubernetes networking
- Native AWS integration
- High scalability
- Advanced routing
- Secure communication
- Enterprise-ready architecture

---

# Summary

AWS Gateway API TCPRoute and GRPCRoute extend Kubernetes networking beyond HTTP by supporting TCP and gRPC workloads. Combined with Amazon EKS and AWS Load Balancer Controller, they provide secure, scalable, and enterprise-grade networking for modern cloud applications.
