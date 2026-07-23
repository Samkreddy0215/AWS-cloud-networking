# AWS VPC Lattice Target Groups and Listeners

## Overview

AWS VPC Lattice uses **Listeners** to receive client requests and **Target Groups** to route those requests to healthy backend resources. This architecture enables secure, scalable, and highly available application communication across VPCs and AWS accounts.

---

# Architecture Diagram

```
                  Client Request
                        │
                        ▼
              AWS VPC Lattice Service
                        │
                   Listener (HTTPS)
                        │
                        ▼
                 Target Group
          ┌──────────┼──────────┐
          ▼          ▼          ▼
       EC2 App     ECS Task    EKS Pod
```

---

# Key Components

## Listener

A Listener accepts incoming traffic on a specified protocol and port.

Example:

- HTTPS : 443
- HTTP : 80

---

## Target Group

A Target Group contains backend resources that receive application traffic.

Supported targets include:

- Amazon EC2
- Amazon ECS
- Amazon EKS
- AWS Lambda (supported integrations)

---

## Health Checks

Health checks determine whether a backend target can receive traffic.

Common parameters:

- Protocol
- Port
- Health check path
- Interval
- Timeout
- Healthy threshold
- Unhealthy threshold

---

## Routing

The Listener forwards requests to a Target Group based on configured rules.

---

# Configuration Workflow

1. Create a VPC Lattice Service.
2. Create a Target Group.
3. Register backend targets.
4. Configure health checks.
5. Create a Listener.
6. Associate the Listener with the Target Group.
7. Test application connectivity.

---

# Enterprise Use Cases

- Microservices platforms
- Internal APIs
- Shared application services
- Multi-account service connectivity
- Containerized workloads

---

# Best Practices

- Use HTTPS listeners whenever possible.
- Configure meaningful health check paths.
- Monitor target health with CloudWatch.
- Register only healthy backend resources.
- Use descriptive Listener and Target Group names.
- Review health check thresholds regularly.

---

# Common Troubleshooting Scenarios

## Targets Unhealthy

Verify:

- Application is running
- Security Groups allow traffic
- Health check path is valid
- Backend port is correct

---

## Listener Not Receiving Requests

Check:

- Listener port
- Protocol configuration
- Service association
- DNS resolution

---

## Intermittent Traffic Failures

Review:

- Target health
- CloudWatch metrics
- Backend application logs

---

## High Response Time

Verify:

- Backend application performance
- Resource utilization
- Network latency

---

# Advantages

- Managed traffic distribution
- Automatic health monitoring
- High availability
- Native AWS integration
- Simplified application networking
- Scalable service architecture

---

# Summary

AWS VPC Lattice Target Groups and Listeners provide the foundation for routing application traffic to healthy backend services, enabling secure, scalable, and highly available communication across enterprise AWS environments.
