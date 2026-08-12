# AWS Network Firewall Domain List Rule Groups

## Overview

AWS Network Firewall Domain List Rule Groups allow organizations to filter HTTP and HTTPS traffic based on domain names instead of IP addresses. This helps enforce enterprise web access policies and protect workloads from malicious or unauthorized websites.

---

# Architecture Diagram

```text
Application VPC
      │
      ▼
Transit Gateway
      │
      ▼
Inspection VPC
      │
      ▼
AWS Network Firewall
      │
      ▼
Stateful Domain Rule Group
      │
 ┌────┴────┐
 ▼         ▼
HTTP     HTTPS
 │          │
HTTP_HOST TLS_SNI
 │          │
 └────┬─────┘
      ▼
Domain Matching
      │
 ┌────┼─────┐
 ▼    ▼     ▼
ALLOW DENY ALERT
```

---

# What are Domain List Rule Groups?

Domain List Rule Groups are Stateful Rule Groups that inspect domain names and allow or block traffic based on configured domain lists.

---

# Why Use Domain List Rule Groups?

Benefits include:

- Domain-based filtering
- Centralized web access control
- Malware protection
- Phishing prevention
- Enterprise security policy enforcement

---

# HTTP_HOST Inspection

For HTTP traffic, AWS Network Firewall inspects the **HTTP_HOST** header to determine the requested domain.

---

# TLS_SNI Inspection

For HTTPS traffic, AWS Network Firewall inspects the **TLS Server Name Indication (TLS_SNI)** field during the TLS handshake.

---

# Domain Allowlists

Allowlists permit access only to approved domains.

Example:

- company.com
- aws.amazon.com

---

# Domain Denylists

Denylists block access to specified domains.

Example:

- malicious-example.com
- phishing-site.com

---

# Wildcard Domains

Examples:

- .example.com
- .amazonaws.com

Wildcard domains include the base domain and all subdomains.

---

# Rule Actions

Supported actions:

- Allow
- Deny
- Reject
- Alert

---

# HOME_NET

HOME_NET defines which source networks are inspected.

In centralized firewall deployments, include the CIDRs of spoke VPCs so their traffic is also inspected.

---

# Centralized Inspection

Traffic from multiple VPCs can be forwarded through Transit Gateway into a centralized Inspection VPC containing AWS Network Firewall.

---

# Transit Gateway Integration

Transit Gateway routes traffic from spoke VPCs to the Inspection VPC where Domain List Rule Groups inspect HTTP and HTTPS traffic.

---

# Logging

Integrate with:

- Amazon CloudWatch Logs
- Amazon S3
- Amazon Kinesis Data Firehose

---

# Monitoring

Monitor using:

- CloudWatch Metrics
- Firewall Logs
- AWS CloudTrail

---

# Enterprise Use Cases

- URL filtering
- Internet access control
- Malware prevention
- Phishing protection
- Zero Trust security
- Regulatory compliance

---

# Best Practices

- Use centralized Inspection VPCs.
- Keep allowlists minimal.
- Regularly review deny lists.
- Configure HOME_NET correctly.
- Monitor firewall logs.
- Test policies before production deployment.

---

# Common Troubleshooting

## Domain Not Blocked

Check:

- Rule order
- HOME_NET
- TLS_SNI
- HTTP_HOST

---

## Traffic Not Inspected

Verify:

- Transit Gateway routing
- Firewall policy
- Rule group association

---

# Summary

AWS Network Firewall Domain List Rule Groups provide domain-based filtering for HTTP and HTTPS traffic using HTTP_HOST and TLS_SNI inspection. They help organizations implement centralized web filtering, improve security, and support enterprise Zero Trust architectures.
