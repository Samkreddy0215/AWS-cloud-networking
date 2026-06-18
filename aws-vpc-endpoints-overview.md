# AWS VPC Endpoints Overview

## Purpose

AWS VPC Endpoints allow private connectivity between resources in a VPC and supported AWS services without traversing the public internet.

## Types of VPC Endpoints

### Gateway Endpoints
- Amazon S3
- DynamoDB
- Route table based

### Interface Endpoints
- Powered by AWS PrivateLink
- Uses Elastic Network Interfaces (ENIs)
- Supports many AWS services

## Benefits

- Enhanced security
- Reduced internet exposure
- Lower latency
- Simplified network architecture

## Common Use Cases

- Private access to S3 buckets
- Secure application communication
- Hybrid cloud connectivity
- Compliance-driven architectures

## Validation Steps

1. Verify endpoint status
2. Confirm route table associations
3. Test service connectivity
4. Review security group rules

## Best Practices

- Use least-privilege endpoint policies
- Restrict access with security groups
- Monitor endpoint utilization
- Document endpoint dependencies
