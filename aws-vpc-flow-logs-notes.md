# Amazon VPC Flow Logs

## What are VPC Flow Logs?

Amazon VPC Flow Logs capture metadata about IP traffic flowing to and from resources in a VPC for monitoring, troubleshooting, and security analysis.

## Components

- VPC
- Subnet
- Elastic Network Interface (ENI)
- CloudWatch Logs
- Amazon S3
- IAM Role

## Traffic Types

- Accepted
- Rejected
- All

## Common Log Fields

- Source IP
- Destination IP
- Source Port
- Destination Port
- Protocol
- Action
- Bytes
- Packets

## Enterprise Use Cases

- Network troubleshooting
- Security monitoring
- Compliance
- Incident response
- Capacity planning

## Best Practices

- Enable Flow Logs on production VPCs
- Store logs in CloudWatch or S3
- Review rejected traffic
- Integrate with Athena or OpenSearch
- Monitor continuously
