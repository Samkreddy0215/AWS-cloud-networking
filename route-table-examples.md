# AWS Route Table Examples

## Public Route Table

Destination: 0.0.0.0/0
Target: Internet Gateway (IGW)

Purpose:
Allows internet access for resources in a public subnet.

## Private Route Table

Destination: 0.0.0.0/0
Target: NAT Gateway

Purpose:
Allows outbound internet access while preventing inbound internet connections.

## Local Route

Destination: VPC CIDR (10.0.0.0/16)
Target: local

Purpose:
Enables communication between subnets within the same VPC.

## Best Practice

- Separate public and private route tables.
- Use NAT Gateway for private subnet internet access.
- Keep databases in private subnets.
- Review routes regularly for security.
