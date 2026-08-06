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




# AWS Cloud Practitioner – Module 3 Summary.

# 1. Amazon EC2 🖥️

Provides virtual servers in AWS.
Gives full control over the operating system, software, and configuration.
Best when you need maximum control.

# 2. AWS Lambda ⚡

Serverless compute service.
Runs your code without managing servers.
AWS manages infrastructure, scaling, and servers.
Best for event-driven applications and short tasks.

# 3. Containers 📦

Containers package an application and its dependencies together so it runs consistently everywhere.

# Benefits:

Easy deployment
Same environment in development and production
Faster scaling

# 4. Amazon ECS 🚢

# Elastic Container Service

AWS-managed container orchestration service.
Helps deploy, manage, and scale containers.
Easier alternative to managing containers manually.

# 5. Amazon EKS ☸️

# Elastic Kubernetes Service

Managed Kubernetes service on AWS.
AWS manages the Kubernetes control plane.
Used for large-scale container applications.

# 6. AWS Fargate 🚀

Serverless compute engine for containers.
Runs containers without managing servers.
Works with ECS and EKS.

Simple idea:

ECS/EKS manage containers, Fargate runs them without servers.

# 7. AWS Elastic Beanstalk 🌱

Deploy and manage web applications easily.
AWS handles infrastructure, scaling, and deployment.
Good for developers who don't want to manage servers.


# 8. AWS Batch 🧪

Runs large-scale batch computing jobs.
Automatically schedules and scales compute resources.

Examples:

Scientific simulations
Data processing
Machine learning workloads


# 9. Amazon Lightsail 💡

Simple cloud platform with predictable pricing.
Provides:
Virtual servers
Containers
Databases

Best for:

Small websites
Simple applications
Beginners


# 10. AWS Outposts 🏢

Brings AWS infrastructure and services to your own data center.
Used for hybrid cloud environments.
Useful when companies need local data processing.


# AWS                       Service	Purpose
EC2	                        Virtual servers you manage.
Lambda	                    Runs code without managing servers.
ECS	                        Runs and manages Docker containers.
EKS	                        Runs and manages Kubernetes clusters.
Fargate	                    Runs containers without managing servers (works with ECS or EKS).
Elastic Beanstalk          	Deploys web applications automatically.
AWS Batch	                  Runs large-scale batch jobs.
Lightsail	                  Simple virtual private servers (VPS) for beginners.
Outposts	                  Brings AWS services to your own on-premises data center.




# AWS Cloud Practitioner – Module 4 Summary.

# 1. AWS Global Infrastructure 🌍

AWS has a worldwide network of infrastructure, including:

Regions – Geographic locations (e.g., Mumbai, Singapore).
Availability Zones (AZs) – Multiple isolated data centers within a Region.
Edge Locations – Locations closer to users that deliver content faster.

Purpose:

High availability
Fault tolerance
Low latency
Global reach

# 2. Choosing an AWS Region 📍

When selecting a Region, consider:

✅ Compliance – Data residency and legal requirements.
✅ Proximity to customers – Lower latency and better performance.
✅ Service availability – Not all AWS services are available in every Region.
✅ Pricing – Costs can vary between Regions.

# 3. Edge Locations ⚡

Edge locations are part of the AWS global network and are used to deliver content closer to users.

Benefits:

Faster content delivery
Lower latency
Better user experience

# 4. AWS CloudFormation 📜

CloudFormation is an Infrastructure as Code (IaC) service.

Instead of creating AWS resources manually, you write a template (YAML or JSON), and CloudFormation creates them automatically.

Benefits:

Automates infrastructure deployment
Saves time
Reduces human errors
Creates consistent environments



# AWS Cloud Practitioner – Module 5 Summary.


# 1. Amazon VPC (Virtual Private Cloud) 🌐

A VPC is a private, isolated network inside AWS.
It allows you to control your AWS resources' networking.
You decide:
IP addresses
Subnets
Security rules
Connections

# 2. Subnets 📂

A subnet is a smaller section inside a VPC.
Used to organize resources.

Types:

Public Subnet → Resources can access the internet.
Private Subnet → Resources are isolated from direct internet access.

# 3. Gateways 🚪

# Internet Gateway (IGW)

Connects a VPC to the public internet.
Allows public traffic to access resources in the VPC.

# Virtual Private Gateway (VGW)

Connects a VPC to a private network.
Used with VPN or Direct Connect for hybrid cloud.

# NAT Gateway

Allows resources in a private subnet to access the internet.
Prevents outside users from initiating connections to private resources.

# 4. Security in VPC 🔒

# Security Groups

Firewall at the EC2 instance level.
Controls inbound and outbound traffic.
Allow rules only.
Stateful (remembers connections).

# Network ACLs (NACLs)

Firewall at the subnet level.
Controls inbound and outbound traffic.
Supports Allow and Deny rules.
Stateless.

# 5. Connecting to AWS 🔗

# AWS Client VPN 👤

For remote employees.
Securely connects users to AWS resources.

Example:

Employee working from home → AWS


# AWS Site-to-Site VPN 🏢

Connects company offices/data centers to AWS.
Uses encrypted VPN connections.

Example:

Company network → AWS VPC

# AWS Direct Connect ⚡

Dedicated private connection between a company network and AWS.
Used for high bandwidth and consistent performance.

# AWS PrivateLink 🔐

Provides private access between VPCs and AWS services.
Keeps traffic inside AWS network.


# 6. DNS and Traffic Management 🌍

# DNS
Converts domain names into IP addresses.

Example:

google.com → 142.250.x.x

# Amazon Route 53

AWS DNS service.
[Provides:]
Domain registration
DNS routing
Health checks
Traffic policies

# Amazon CloudFront 🚀

AWS Content Delivery Network (CDN).
Uses Edge Locations to deliver content faster.

Benefits:

Lower latency
Faster websites
Secure content delivery

# AWS Global Accelerator 🌎

Improves application availability and performance worldwide.
Routes users to the best available endpoint.

# 7. Other Networking Services

# Transit Gateway

Connects multiple VPCs and on-premises networks.
Works like a central network hub.

# API Gateway

Creates, manages, and secures APIs.
Handles API requests between applications and backend services.