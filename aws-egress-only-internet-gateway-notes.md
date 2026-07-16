# Amazon VPC Egress-Only Internet Gateway

## What is an Egress-Only Internet Gateway?

An Egress-Only Internet Gateway enables IPv6-enabled resources in an Amazon VPC to initiate outbound internet connections while blocking unsolicited inbound internet traffic.

## Components

- IPv6 CIDR Block
- Egress-Only Internet Gateway
- Route Tables
- Security Groups
- Network ACLs

## Benefits

- Secure outbound IPv6 access
- No inbound internet exposure
- Supports IPv6 adoption
- Simple route configuration

## Internet Gateway vs Egress-Only Internet Gateway

- Internet Gateway supports inbound and outbound traffic.
- Egress-Only Internet Gateway supports outbound IPv6 traffic only.

## Enterprise Use Cases

- Private application servers
- Software updates
- Secure outbound connectivity
- IPv6-enabled workloads

## Best Practices

- Use for private IPv6 workloads
- Configure `::/0` routes correctly
- Monitor with VPC Flow Logs
- Validate security policies regularly
