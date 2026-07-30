## AWS Networking basics

# Cloud Basics

[Cloud] — renting someone else's computers (compute/storage/networking) by the hour instead of buying hardware.

# Service models (who manages what)
  - [IaaS] — you rent raw compute, manage OS/patches yourself (e.g., EC2). This is where most of DevOps lives.
  - [PaaS] — provider manages OS/runtime, you just deploy code (e.g., Heroku).
  - [SaaS] — fully finished product, no infra involved (e.g., Gmail).

# Deployment models
  - [Public] — shared infra rented from AWS/Azure/GCP.
  - [Private] — company's own dedicated infra.
  - [Hybrid] — mix of both, common for compliance/legacy reasons.

# Region vs AZ
  - [Region] = geographic area (e.g., us-east-1).
  - AZ (Availability Zone) = isolated data center within a region.
  - Spreading resources across AZs = why "high availability" exists.

# Four pillars in the console
  - [Compute] — VMs/containers (processing power).
  - [Storage] — object storage (S3/Blob) or block storage (like a hard drive).
  - [Networking] — VPC/VNet, subnets, security groups.
  - [IAM] — who's allowed to do what (users, roles, permissions).

# Billing
  - Resources cost money the moment they're running — even idle.
  - Know your free tier limits.
  - Know where the billing dashboard is.




# AWS Cloud Practitioner – Module 1 Summary

# 1. Cloud Computing ☁️
Cloud computing means using computers, storage, and other IT services over the internet instead of owning physical servers.

[Benefits:]

Pay only for what you use
Scale resources up or down easily
Access from anywhere
No need to maintain hardware


# 2. AWS Shared Responsibility Model 🔒
AWS is responsible for (Security of the Cloud):

Data centers
Physical servers
Networking
Hardware

You are responsible for (Security in the Cloud):

Your data
IAM users & passwords
Applications
Operating system updates (EC2)
Security settings

Easy to remember:

AWS secures the cloud.
You secure what you put in the cloud.

# 3. AWS Regions 🌍
A Region is a geographical location where AWS has data centers.

Examples:

Mumbai
Singapore
London
Sydney

Choose a region close to your users for better performance.


# 4. Availability Zones (AZs) 
An Availability Zone (AZ) is one or more data centers inside a Region.

A Region has multiple AZs.

Why?

If one AZ fails, another can keep your application running.
Improves reliability and availability.