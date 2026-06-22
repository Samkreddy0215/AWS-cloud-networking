# AWS CloudFront Networking

## What is Amazon CloudFront?

Amazon CloudFront is AWS's Content Delivery Network (CDN) service that delivers content through globally distributed edge locations.

## Benefits

- Low latency
- Global content delivery
- Reduced origin load
- Improved performance
- Enhanced security

## Components

### Edge Locations

Global points of presence that serve cached content closer to users.

### Origins

Sources of content.

Examples:

- Amazon S3
- Application Load Balancer
- EC2 Instances

### Cache Behavior

Determines how CloudFront handles requests and cached content.

### Cache Policies

Control cache duration and request handling.

## Origin Access Control (OAC)

Provides secure access between CloudFront and S3.

## AWS WAF Integration

Supports:

- SQL Injection Protection
- Cross-Site Scripting Protection
- Bot Protection
- DDoS Mitigation

## CloudFront vs Global Accelerator

| Feature | CloudFront | Global Accelerator |
|----------|-----------|-------------------|
| Caching | Yes | No |
| CDN | Yes | No |
| TCP/UDP Support | No | Yes |
| Static Content Delivery | Yes | No |

## Enterprise Use Cases

- Website Acceleration
- Video Streaming
- API Delivery
- Software Distribution
- Global Content Delivery

## Best Practices

- Use OAC for S3 origins
- Enable HTTPS
- Use AWS WAF
- Optimize cache policies
- Monitor CloudFront metrics
