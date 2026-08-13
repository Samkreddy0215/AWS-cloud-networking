# AWS Network Firewall Suricata Custom Rules

## Overview

AWS Network Firewall supports Suricata-compatible custom rules that enable advanced intrusion detection and intrusion prevention capabilities. These rules inspect network traffic and apply security actions based on administrator-defined signatures.

---

# Architecture Diagram

```text
Application VPC
       │
       ▼
Route Tables
       │
       ▼
Inspection VPC
       │
       ▼
AWS Network Firewall
       │
       ▼
Stateful Engine
       │
       ▼
Suricata Rule Group
       │
 ┌─────┼──────────┐
 ▼     ▼          ▼
Header Flow     Content
Match  Match     Match
 │      │          │
 └──────┼──────────┘
        ▼
PASS / DROP / REJECT / ALERT
        │
        ▼
Destination
```

---

# What is Suricata?

Suricata is an open-source Intrusion Detection System (IDS) and Intrusion Prevention System (IPS).

AWS Network Firewall uses Suricata-compatible syntax for advanced stateful inspection.

---

# Rule Structure

General format:

```text
ACTION PROTOCOL SOURCE_IP SOURCE_PORT -> DESTINATION_IP DESTINATION_PORT (OPTIONS)
```

Example:

```text
alert tcp $HOME_NET any -> $EXTERNAL_NET 443 (msg:"HTTPS Connection"; flow:to_server,established; sid:1000001; rev:1;)
```

---

# Rule Header

The rule header contains:

- Action
- Protocol
- Source IP
- Source Port
- Direction
- Destination IP
- Destination Port

---

# Rule Options

Common options include:

- msg
- flow
- content
- sid
- rev
- classtype
- priority

---

# HOME_NET

Represents trusted internal networks.

Example:

```text
$HOME_NET
```

---

# EXTERNAL_NET

Represents networks outside the trusted environment.

Example:

```text
$EXTERNAL_NET
```

---

# Flow Keywords

Examples:

- established
- to_server
- to_client

Flow keywords ensure rules inspect the correct direction of traffic.

---

# Content Matching

Rules can inspect:

- HTTP
- HTTPS
- DNS
- TCP
- UDP
- ICMP

---

# SID

SID (Signature ID) uniquely identifies each Suricata rule.

Example:

```text
sid:1000001;
```

---

# REV

REV indicates the rule revision.

Example:

```text
rev:1;
```

---

# Rule Actions

Supported actions:

- PASS
- DROP
- REJECT
- ALERT

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

- IDS
- IPS
- Malware Detection
- Threat Hunting
- Zero Trust Security
- Enterprise Firewall Policies

---

# Best Practices

- Use unique SID values.
- Test rules before production.
- Use Strict Order for sensitive environments.
- Review logs regularly.
- Minimize unnecessary rules.
- Document custom signatures.

---

# Limitations

- Some Suricata features are not supported by AWS Network Firewall.
- Always validate custom rules before production deployment.

---

# Common Troubleshooting

## Rule Not Matching

Verify:

- HOME_NET
- EXTERNAL_NET
- Flow keywords
- Rule order

---

## Unexpected Traffic Allowed

Review:

- Stateful Rule Groups
- Rule priorities
- Firewall policy

---

# Summary

AWS Network Firewall Suricata Custom Rules provide advanced IDS/IPS capabilities using Suricata-compatible syntax. They allow organizations to inspect, detect, block, and alert on malicious traffic while supporting enterprise-grade cloud security.
