# StreamCo DevOps Lab

## Environment Requirements

### VPC

Two public subnets, each in their own AZ

### Elastic Load Balancer

Serving traffic over TLS

### nginx Web Node

One spun up in each AZ for a total of two

### Elastic IP

One per AZ, for each web node

## 

1. Spin up VPC with two publicly available subnets, each in their own AZ, with an ELB.

2. Write a CFN template that spins this environment up.

3. Add spinning up one ec2 instance per subnet

4. Add the EIP in and associate them with each respective instance

5. Add in autoscaling rules, so if an instance dies, a new one spins up in its place

