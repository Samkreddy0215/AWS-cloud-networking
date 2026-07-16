# Amazon Route 53 Resolver Endpoints

## What are Resolver Endpoints?

Amazon Route 53 Resolver Endpoints enable DNS resolution between Amazon VPCs and on-premises DNS infrastructure.

## Endpoint Types

### Inbound Resolver Endpoint

Allows on-premises DNS servers to resolve AWS-hosted DNS records.

### Outbound Resolver Endpoint

Allows AWS resources to resolve DNS records hosted on-premises.

## Components

- Inbound Resolver Endpoint
- Outbound Resolver Endpoint
- Resolver Rules
- Private Hosted Zones
- Security Groups

## Enterprise Use Cases

- Hybrid cloud DNS
- Active Directory integration
- Multi-VPC DNS
- Enterprise migrations

## Best Practices

- Deploy across multiple Availability Zones
- Secure with Security Groups
- Use Resolver Rules for conditional forwarding
- Enable DNS Query Logging
- Test DNS resolution regularly
