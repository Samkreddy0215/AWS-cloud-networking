# AWS VPC Lattice Weighted Routing

## Overview

AWS VPC Lattice Weighted Routing allows traffic to be distributed across multiple backend target groups based on assigned percentage weights. This enables gradual application deployments while reducing deployment risk.

Example:

- Version 1 → 90% of traffic
- Version 2 → 10% of traffic

As confidence increases, traffic can gradually shift to the new version.

---

# Architecture Diagram

```
                  Client Requests
                        │
                        ▼
              AWS VPC Lattice Service
                        │
                 HTTPS Listener
                        │
              Weighted Routing Rule
             ┌──────────┴──────────┐
             ▼                     ▼
      Target Group A         Target Group B
      Version 1 (90%)        Version 2 (10%)
             │                     │
             ▼                     ▼
          EC2/ECS/EKS          EC2/ECS/EKS
```

---

# Key Components

## Listener

Receives incoming HTTP or HTTPS requests.

---

## Weighted Routing Rule

Defines how traffic is distributed between target groups.

Example:

- Target Group A = 80
- Target Group B = 20

---

## Target Groups

Contain backend application instances.

Supported targets:

- Amazon EC2
- Amazon ECS
- Amazon EKS
- AWS Lambda (supported integrations)

---

## Health Checks

Traffic is sent only to healthy targets.

---

## CloudWatch

Monitors:

- Request count
- Error rate
- Response latency
- Healthy targets

---

# Configuration Workflow

1. Create a VPC Lattice Service.
2. Create two or more Target Groups.
3. Register backend resources.
4. Configure health checks.
5. Create a Listener.
6. Configure weighted routing rules.
7. Test traffic distribution and monitor metrics.

---

# Enterprise Use Cases

- Blue/Green deployments
- Canary releases
- A/B testing
- Progressive application upgrades
- Risk-controlled software releases

---

# Best Practices

- Start with a small percentage for new releases.
- Monitor CloudWatch metrics during rollouts.
- Ensure health checks are configured correctly.
- Keep rollback procedures documented.
- Increase traffic gradually after validation.

---

# Common Troubleshooting Scenarios

## New Version Receives No Traffic

Verify:

- Routing weights
- Listener rule configuration
- Target Group association

---

## Unhealthy Targets

Check:

- Health check path
- Backend application
- Security Groups

---

## Uneven Traffic Distribution

Review:

- Weight configuration
- Target availability
- CloudWatch metrics

---

## Increased Error Rate

Verify:

- Application logs
- Deployment changes
- Backend resource health

---

# Advantages

- Safer deployments
- Reduced production risk
- Controlled traffic migration
- Easy rollback
- High availability
- Native AWS integration

---

# Summary

AWS VPC Lattice Weighted Routing enables controlled traffic distribution across multiple application versions, making enterprise deployments safer and easier to manage through gradual rollouts and continuous monitoring.
