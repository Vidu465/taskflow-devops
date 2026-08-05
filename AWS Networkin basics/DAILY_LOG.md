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





# AWS Cloud Practitioner – Module 2 Summary

[multitenancy] → sharing underlying hardware between virtual machines
[hypervisor]   → software running on the host machine to keep isolation


# AWS Cloud Practitioner – Module 2 Summary (Simple)

# Amazon EC2 🖥️
EC2 (Elastic Compute Cloud) is a virtual server in AWS.
It is used to run websites, applications, and databases.

# EC2 Instance Types ⚙️

# AWS provides different instance types for different needs:

General Purpose – Balanced performance
Compute Optimized – More CPU
Memory Optimized – More RAM
Storage Optimized – Faster storage

# Provisioning AWS Resources 🚀

Provisioning means creating and setting up AWS resources.

# You can create resources using:

AWS Management Console
AWS CLI
AWS SDK

# EC2 Pricing 💰

 AWS offers different pricing options:

On-Demand – Pay only when you use it
Reserved Instances – Lower cost with long-term commitment
Spot Instances – Cheapest option using unused AWS capacity
Savings Plans – Save money by committing to usage

# Auto Scaling 

Auto Scaling automatically adds or removes EC2 instances based on traffic.

Benefits:

Handles high traffic
Reduces cost
Improves availability

# Elastic Load Balancing (ELB) ⚖️

A Load Balancer distributes incoming traffic across multiple EC2 instances.

Benefits:

Prevents server overload
Improves performance
Increases reliability

# Amazon SNS 📢

Simple Notification Service (SNS) sends notifications through:

Email
SMS
Mobile push
Other AWS services

# Amazon SQS 📩

Simple Queue Service (SQS) stores messages in a queue so applications can communicate reliably without depending on each other.