# AWS Transit Gateway Route Tables

## Overview

AWS Transit Gateway route tables control traffic flow between VPCs, VPNs, and Direct Connect attachments connected to a Transit Gateway.

## Key Components

- Transit Gateway
- Route Tables
- Attachments
- Route Propagation
- Route Association

## Route Association

An attachment can be associated with only one Transit Gateway route table.

## Route Propagation

Allows routes from attached networks to be automatically learned by the route table.

## Common Design Example

Production VPC → Production Route Table

Development VPC → Development Route Table

On-Premises VPN → Shared Services Route Table

## Benefits

- Centralized routing management
- Simplified multi-VPC connectivity
- Scalable hybrid cloud architecture
- Improved traffic segmentation

## Verification

- Check attachment status
- Verify route propagation
- Review route table associations
- Test end-to-end connectivity

## Best Practices

- Separate environments using dedicated route tables
- Use least-privilege routing principles
- Document all associations and propagations
- Monitor route changes regularly
