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

## Additional NAT Gateway Notes

### Why NAT Gateway is Needed

Private EC2 instances often require Internet access for:

* Operating system updates
* Package downloads
* Accessing external APIs

### Route Example

0.0.0.0/0 → NAT Gateway

This route allows outbound Internet traffic from a private subnet.

### Traffic Flow

Private EC2 → NAT Gateway → Internet Gateway → Internet

### Important Points

* NAT Gateway is used by Private Subnets.
* Internet cannot directly access Private EC2 instances.
* NAT Gateway provides outbound Internet access only.
* NAT Gateway must be placed in a Public Subnet.
