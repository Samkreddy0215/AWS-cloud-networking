# AWS VPC Sharing

## What is AWS VPC Sharing?

AWS VPC Sharing allows multiple AWS accounts to use subnets from a centrally managed VPC through AWS Resource Access Manager (RAM).

## Components

- AWS Resource Access Manager (RAM)
- Shared VPC
- Shared Subnets
- Owner Account
- Participant Accounts
- AWS Organizations

## Benefits

- Centralized networking
- Improved governance
- Reduced IP address duplication
- Consistent security
- Simplified management

## Architecture

Networking Account
        │
Shared VPC
        │
 ├── Development Account
 ├── QA Account
 └── Production Account

## Enterprise Use Cases

- Multi-account environments
- Landing Zones
- Shared Services
- Enterprise governance

## Best Practices

- Use AWS Organizations
- Share only required subnets
- Monitor with CloudTrail
- Follow least-privilege IAM
- Plan CIDR ranges carefully
