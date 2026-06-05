# AWS VPC Endpoints

## What is a VPC Endpoint?

A VPC Endpoint allows private communication between a VPC and AWS services without using the public Internet.

---

## Why Use VPC Endpoints?

Benefits:

* Private connectivity
* Improved security
* Reduced Internet exposure
* Lower NAT Gateway costs

---

## Gateway Endpoints

Supported Services:

* Amazon S3
* Amazon DynamoDB

Example:

EC2
↓
Gateway Endpoint
↓
Amazon S3

---

## Interface Endpoints

Supported Services:

* CloudWatch
* Systems Manager
* Secrets Manager
* KMS
* SNS
* SQS

Interface Endpoints create Elastic Network Interfaces (ENIs) inside subnets.

---

## AWS PrivateLink

AWS PrivateLink provides private connectivity using Interface Endpoints.

Traffic remains inside the AWS network.

---

## Gateway vs Interface Endpoints

Gateway Endpoint:

* S3
* DynamoDB

Interface Endpoint:

* Most AWS Services
* Uses ENI
* Uses PrivateLink

---

## Enterprise Use Cases

* Secure S3 access
* Secure Secrets Manager access
* Private CloudWatch connectivity
* Hybrid cloud security

---

## Key Points

* VPC Endpoints keep traffic private
* No Internet Gateway required
* No NAT Gateway required
* Gateway Endpoints support S3 and DynamoDB
* Interface Endpoints support most AWS services
