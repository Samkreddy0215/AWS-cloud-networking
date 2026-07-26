# AWS VPC Lattice Path-Based Routing

## Overview

AWS VPC Lattice Path-Based Routing allows incoming requests to be directed to different backend services based on the URL path. This simplifies API management and microservices architectures by allowing multiple applications to share a single endpoint.

Example:

https://api.company.com/orders

https://api.company.com/payments

https://api.company.com/users

Each request can be routed to a different backend service.

---

# Architecture Diagram

```
                   Client Request
                         │
                         ▼
              AWS VPC Lattice Service
                         │
                  HTTPS Listener
                         │
             ┌───────────┼────────────┐
             │           │            │
             ▼           ▼            ▼
        /orders     /payments      /users
             │           │            │
             ▼           ▼            ▼
       Orders API   Payment API   User API
```

---

# Key Components

## Listener

Receives incoming client requests.

Common ports:

- HTTPS (443)
- HTTP (80)

---

## Listener Rules

Evaluate request paths and determine where traffic should be forwarded.

Examples:

```
/orders/*
```

```
/payments/*
```

```
/users/*
```

---

## Target Groups

Each application or microservice has its own Target Group.

Examples:

- Orders Service
- Payment Service
- User Service

---

## Backend Services

Supported compute platforms include:

- Amazon EC2
- Amazon ECS
- Amazon EKS
- AWS Lambda (supported integrations)

---

# Configuration Workflow

1. Create a VPC Lattice Service.
2. Create Target Groups for each application.
3. Register backend targets.
4. Create an HTTPS Listener.
5. Add path-based routing rules.
6. Associate each rule with its Target Group.
7. Test routing using different URL paths.

---

# Enterprise Use Cases

- API Gateways
- Enterprise microservices
- Internal business applications
- Shared application platforms
- Multi-team application deployments

---

# Best Practices

- Use meaningful URL paths.
- Keep routing rules simple.
- Configure health checks for every Target Group.
- Enable CloudWatch monitoring.
- Use HTTPS for production workloads.
- Document routing rules.

---

# Common Troubleshooting Scenarios

## Incorrect Backend Receives Traffic

Verify:

- Listener rule priority
- Path pattern
- Target Group association

---

## 404 Not Found

Check:

- Listener configuration
- Backend application routes
- URL path

---

## Unhealthy Targets

Verify:

- Health check path
- Security Groups
- Application availability

---

## High Response Time

Review:

- Backend application
- Target health
- CloudWatch metrics

---

# Advantages

- Simplified application routing
- Centralized traffic management
- Better microservices organization
- Native AWS integration
- Scalable architecture
- Reduced operational complexity

---

# Summary

AWS VPC Lattice Path-Based Routing enables efficient request routing by forwarding traffic to different backend services based on URL paths, making it an ideal solution for enterprise APIs and microservices.
