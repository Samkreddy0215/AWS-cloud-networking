# AWS Cloud Map

## What is AWS Cloud Map?

AWS Cloud Map is a service discovery solution that allows applications to locate services using DNS names or APIs instead of hardcoded IP addresses.

## Benefits

- Automatic service discovery
- Dynamic DNS resolution
- Works with containers and EC2
- Simplifies application connectivity
- Supports cloud-native architectures

## Components

### Namespace

A logical domain for organizing services.

Examples:

- company.local
- internal.company.com

### Service

Represents an application.

Examples:

- frontend
- backend
- database

### Service Instance

An individual EC2 instance or container running a service.

## Service Discovery

### DNS-Based Discovery

Applications resolve service names through DNS.

### API-Based Discovery

Applications use AWS APIs or SDKs to discover services.

## ECS and EKS Integration

Cloud Map automatically registers and deregisters container instances.

## Enterprise Use Cases

- Microservices
- ECS Applications
- Kubernetes (EKS)
- Internal APIs
- Hybrid Cloud
- Dynamic Service Discovery

## Best Practices

- Use meaningful namespaces
- Enable health checks
- Integrate with ECS/EKS
- Avoid hardcoded IP addresses
