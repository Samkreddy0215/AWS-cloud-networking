# AWS Route Tables

## What is a Route Table?
A Route Table controls where network traffic is directed inside a VPC.

## Important Route
0.0.0.0/0

This route represents internet traffic.

## Internet Gateway
An Internet Gateway allows communication between AWS resources and the internet.

## Public Subnet
A subnet becomes public when:
- It has a route to Internet Gateway
- Route table contains 0.0.0.0/0

## Private Subnet
A private subnet does not have direct internet access.

## Key Learning
Route tables control traffic flow inside AWS networking.
