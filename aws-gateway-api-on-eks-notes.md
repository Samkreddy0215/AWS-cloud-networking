# AWS Gateway API on Amazon EKS

## Overview

AWS Gateway API is the next-generation Kubernetes networking API designed to provide more flexible, scalable, and role-oriented traffic management than the traditional Kubernetes Ingress resource.

On Amazon EKS, Gateway API integrates with the AWS Load Balancer Controller to provision and manage AWS Application Load Balancers (ALBs) and Network Load Balancers (NLBs), enabling enterprise-grade routing, security, and traffic management.

---

# Architecture Diagram

```
                    Internet
                        │
                        ▼
              AWS Load Balancer
                        │
                GatewayClass
                        │
                    Gateway
                        │
        ┌───────────────┼───────────────┐
        ▼               ▼               ▼
    HTTPRoute       TCPRoute       TLSRoute
        │               │               │
        ▼               ▼               ▼
     Service A      Service B      Service C
        │               │               │
        ▼               ▼               ▼
        Amazon EKS Worker Nodes
```

---

# Key Components

## GatewayClass

Defines which controller manages the Gateway.

Examples include:

- AWS Load Balancer Controller
- Other Kubernetes Gateway controllers

---

## Gateway

Represents the network entry point into the Kubernetes cluster.

It defines:

- Listener ports
- Protocols
- TLS configuration

---

## HTTPRoute

Defines routing rules for HTTP and HTTPS traffic.

Supports:

- Path-based routing
- Host-based routing
- Header matching
- Traffic splitting

---

## TCPRoute

Routes Layer 4 TCP traffic.

Commonly used for:

- Databases
- Enterprise applications
- Custom TCP services

---

## TLSRoute

Routes encrypted TLS traffic without terminating TLS at the Gateway.

Useful for secure enterprise workloads.

---

# Gateway API vs Kubernetes Ingress

| Ingress | Gateway API |
|----------|-------------|
| Basic routing | Advanced routing |
| Limited customization | Highly extensible |
| Single resource | Multiple resources |
| Less role separation | Better role separation |
| Limited policy support | Advanced policy model |

---

# Integration with Amazon EKS

Gateway API works with:

- Amazon EKS
- AWS Load Balancer Controller
- Application Load Balancer (ALB)
- Network Load Balancer (NLB)

This allows Kubernetes applications to securely expose services while leveraging native AWS networking capabilities.

---

# Enterprise Use Cases

- Microservices
- Multi-team Kubernetes clusters
- API platforms
- Internal enterprise applications
- Hybrid cloud deployments
- Multi-tenant environments

---

# Best Practices

- Use Gateway API instead of Ingress for new Kubernetes deployments.
- Use HTTPS wherever possible.
- Enable TLS certificates with AWS Certificate Manager (ACM).
- Monitor traffic using Amazon CloudWatch.
- Apply least-privilege IAM permissions.
- Document Gateway and Route configurations.
- Regularly update the AWS Load Balancer Controller.

---

# Common Troubleshooting

## Gateway Not Created

Verify:

- GatewayClass exists.
- AWS Load Balancer Controller is running.
- IAM permissions are configured correctly.

---

## Routes Not Working

Check:

- HTTPRoute configuration.
- Service selectors.
- Namespace permissions.
- Listener configuration.

---

## Load Balancer Not Provisioned

Verify:

- AWS Load Balancer Controller logs.
- IAM role permissions.
- Subnet tags.
- Security Groups.

---

## TLS Errors

Check:

- ACM certificate.
- Listener configuration.
- DNS records.
- Certificate validity.

---

# Advantages

- Modern Kubernetes networking
- Better scalability
- Flexible routing
- Improved security
- Native AWS integration
- Enterprise-ready architecture

---

# Summary

AWS Gateway API on Amazon EKS provides a modern, extensible networking model for Kubernetes applications, offering advanced routing, improved role separation, and seamless integration with AWS networking services.
