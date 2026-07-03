# AWS Hybrid DNS Architecture

## What is Hybrid DNS?

Hybrid DNS enables seamless DNS resolution between AWS and on-premises environments using Amazon Route 53 Resolver.

## Components

- Route 53 Resolver
- Inbound Resolver Endpoints
- Outbound Resolver Endpoints
- Resolver Rules
- Private Hosted Zones
- Conditional Forwarding

## DNS Flow

### On-Premises to AWS

On-premises DNS queries are forwarded to Route 53 Resolver inbound endpoints.

### AWS to On-Premises

AWS workloads use outbound endpoints to resolve on-premises domains.

## Enterprise Use Cases

- Hybrid Cloud
- Active Directory
- Multi-VPC DNS
- Disaster Recovery
- Application Migration

## Best Practices

- Use conditional forwarding
- Deploy endpoints across multiple Availability Zones
- Secure DNS traffic with least-privilege access
- Monitor Resolver query logs
- Test DNS failover regularly
