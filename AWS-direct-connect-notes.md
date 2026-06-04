# AWS Direct Connect

## What is AWS Direct Connect?

AWS Direct Connect is a dedicated private network connection between an on-premises network and AWS.

---

## Benefits

* Lower latency
* Consistent performance
* Private connectivity
* Improved reliability

---

## Direct Connect Gateway

A Direct Connect Gateway allows a Direct Connect connection to access multiple VPCs.

Example:

Data Center
↓
Direct Connect
↓
DX Gateway
↓
Multiple VPCs

---

## Virtual Interfaces (VIF)

### Private VIF

Used to access private VPC resources.

### Public VIF

Used to access AWS public services such as:

* Amazon S3
* DynamoDB

---

## Direct Connect vs VPN

Direct Connect:

* Private dedicated connection
* Better performance
* Higher cost

VPN:

* Uses Internet
* Encrypted tunnel
* Lower cost

---

## Enterprise Use Cases

* Hybrid Cloud
* Data Center Connectivity
* Application Migration
* Backup and Disaster Recovery

---

## Key Points

* Direct Connect bypasses the public Internet
* Provides private AWS connectivity
* Supports multiple VPCs through DX Gateway
* Uses Private and Public VIFs
