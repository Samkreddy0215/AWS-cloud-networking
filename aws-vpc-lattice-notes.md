# AWS VPC Lattice

## What is AWS VPC Lattice?

AWS VPC Lattice is an application networking service that enables secure communication between services across multiple VPCs and AWS accounts.

## Benefits

- Simplified service connectivity
- Secure service-to-service communication
- Centralized access management
- Built-in load balancing
- Service discovery

## Components

### Service Network

A logical grouping of application services.

### Service

Represents an application endpoint.

### Target Groups

Backend resources such as:

- EC2
- ECS
- EKS
- Lambda

## Security

Supports:

- IAM Authentication
- Security Policies
- TLS Encryption

## Traffic Management

Provides:

- Health Checks
- Load Balancing
- Service Discovery
- Traffic Routing

## Enterprise Use Cases

- Microservices
- Multi-VPC Applications
- Multi-Account Networking
- Internal APIs
- Hybrid Cloud

## Best Practices

- Use least-privilege IAM policies
- Group related services into Service Networks
- Enable health checks
- Monitor service performance
- Encrypt application traffic
