# AWS NAT Gateway

## What is a NAT Gateway?
A NAT Gateway allows private subnet resources to access the internet securely.

## Why Use NAT Gateway?
Private resources may need outbound internet access for:
- Software updates
- Package downloads
- External API communication

## Key Benefit
Internet cannot directly initiate connections to private subnet resources.

## Traffic Flow
Private Subnet → NAT Gateway → Internet Gateway → Internet

## Public vs Private Routing

### Public Subnet
0.0.0.0/0 → Internet Gateway

### Private Subnet
0.0.0.0/0 → NAT Gateway
