☁️ **Exam Guide:** Solutions Architect Associate
**Technologies And Concepts Cheat Sheet**
📘 *Cheat Sheet*

> **Note:** The SAA-C03 exam guide lists technologies and concepts across all four domains. This cheat sheet consolidates that information into a **compact, exam-aligned reference.** Organized domain by domain.  Designed for quick review and efficient study.

---

## 📖 Exam Overview

| # | Detail | Info |
|---|--------|------|
| 1 | **Exam Code** | SAA-C03 |
| 2 | **Questions** | 65 total (50 scored, 15 unscored) |
| 3 | **Passing Score** | 720 / 1000 |
| 4 | **Question Types** | Multiple choice & Multiple response |
| 5 | **Experience Required** | 1+ year hands-on designing cloud solutions on AWS |

---

## Domain Weightings

| # | Domain | Weight |
|---|--------|--------|
| 1 | **Design Secure Architectures** | 30% |
| 2 | **Design Resilient Architectures** | 26% |
| 3 | **Design High-Performing Architectures** | 24% |
| 4 | **Design Cost-Optimized Architectures** | 20% |

---

## 🔒 Domain 1
### Design Secure Architectures

#### **1.1** Secure Access to AWS Resources

| # | Concept | What to Know |
|---|---------|--------------|
| 1 | **IAM** | Users, Groups, Roles, Policies: Design flexible authorization models |
| 2 | **IAM Identity Center** | Centralized SSO across multiple AWS accounts |
| 3 | **MFA** | Apply to IAM users and root users as a security best practice |
| 4 | **Cross-Account Access** | Use IAM Roles + STS for role switching and cross-account patterns |
| 5 | **AWS Organizations & SCPs** | Manage multi-account security strategy with Service Control Policies |
| 6 | **AWS Control Tower** | Automate landing zones and guardrails across accounts |
| 7 | **Resource Policies** | Determine when to use resource-based vs identity-based policies |
| 8 | **Federated Access** | Directory service + IAM roles for external identity federation |
| 9 | **Least Privilege** | Core security principle: grant only minimum required permissions |
| 10 | **Shared Responsibility Model** | AWS secures the cloud & you secure what's in it |

#### **1.2** Secure Workloads and Applications

| # | Concept | What to Know |
|---|---------|--------------|
| 1 | **VPC Architecture** | Security groups, route tables, NACLs, NAT gateways |
| 2 | **Subnets** | Public vs private subnet segmentation strategies |
| 3 | **AWS Shield** | DDoS protection (Standard free, Advanced paid) |
| 4 | **AWS WAF** | Web Application Firewall for Layer 7 (SQL injection, XSS) |
| 5 | **AWS Secrets Manager** | Rotate, manage, retrieve secrets (DB credentials, API keys) |
| 6 | **Amazon Cognito** | User authentication for web/mobile apps |
| 7 | **AWS GuardDuty** | Threat detection using ML on logs/events |
| 8 | **Amazon Macie** | Discover and protect sensitive data (PII) in S3 |
| 9 | **VPN** | Site-to-Site VPN and Client VPN for encrypted connectivity |
| 10 | **AWS Direct Connect** | Dedicated private network connection to AWS |

#### **1.3** Data Security Controls

| # | Concept | What to Know |
|---|---------|--------------|
| 1 | **KMS** | Managed key creation, rotation, and control for encryption at rest |
| 2 | **ACM** | Certificate Manager: TLS/SSL for encryption in transit |
| 3 | **CloudHSM** | Hardware Security Module for customer-managed key control |
| 4 | **Data Classification** | Categorize data by sensitivity to apply appropriate controls |
| 5 | **S3 Versioning & MFA Delete** | Protect object data from accidental deletion |
| 6 | **Backup & Replication** | Implement data backup, point-in-time recovery, cross-region replication |
| 7 | **Data Lifecycle Policies** | Manage retention and expiry of data at rest |
| 8 | **Compliance** | Align AWS services to regulatory requirements (GDPR, HIPAA, etc.) |

---

## 🏗️ Domain 2
### Design Resilient Architectures

#### **2.1** Scalable and Loosely Coupled Architectures

| # | Concept | What to Know |
|---|---------|--------------|
| 1 | **Amazon SQS** | Decouple components with message queuing (Standard and FIFO) |
| 2 | **Amazon SNS** | Pub/sub messaging for fan-out patterns |
| 3 | **Amazon EventBridge** | Event-driven routing across AWS services and SaaS apps |
| 4 | **AWS Step Functions** | Workflow orchestration for distributed applications |
| 5 | **API Gateway** | Create, publish, and manage REST/HTTP/WebSocket APIs |
| 6 | **Amazon AppFlow** | Managed data integration between SaaS apps and AWS |
| 7 | **AWS AppSync** | Managed GraphQL API service |
| 8 | **Serverless Patterns** | Lambda + API Gateway + SQS/SNS for event-driven design |
| 9 | **Microservices** | Stateless vs stateful workloads & Independent scaling of components |
| 10 | **Caching Strategies** | Reduce load & know when to use caching vs direct reads |
| 11 | **Horizontal vs Vertical Scaling** | Scale out (add instances) vs scale up (bigger instance) |
| 12 | **Load Balancers** | ALB (Layer 7), NLB (Layer 4), GLB (Layer 3/4 for appliances) |
| 13 | **Amazon MQ** | Managed message broker (ActiveMQ/RabbitMQ) for migrations |
| 14 | **Multi-tier Architectures** | Web / App / DB tiers with distinct roles |
| 15 | **CDN / Edge Accelerators** | CloudFront for caching, Global Accelerator for routing performance |

#### **2.2** Highly Available and Fault-Tolerant Architectures

| # | Concept | What to Know |
|---|---------|--------------|
| 1 | **Availability Zones** | Deploy across ≥2 AZs for high availability |
| 2 | **AWS Regions** | Choose regions based on latency, compliance, and redundancy |
| 3 | **Disaster Recovery Strategies** | Backup & Restore → Pilot Light → Warm Standby → Active-Active |
| 4 | **RPO / RTO** | Recovery Point Objective (data loss tolerance) vs Recovery Time Objective (downtime tolerance) |
| 5 | **Amazon Route 53** | DNS with health checks, failover routing, latency-based routing |
| 6 | **RDS Proxy** | Pooled DB connections for Lambda and high-concurrency apps |
| 7 | **Distributed Design Patterns** | Retry with backoff, circuit breaker, bulkhead patterns |
| 8 | **Service Quotas & Throttling** | Plan for limits in standby environments |
| 9 | **AWS X-Ray** | Distributed tracing for workload visibility |
| 10 | **Immutable Infrastructure** | Replace rather than patch: ensures consistency |
| 11 | **Auto Scaling** | EC2 Auto Scaling + AWS Auto Scaling for elastic capacity |
| 12 | **Storage Durability** | S3 (11 9s), EBS (99.999%), choose appropriate tier |

---

## ⚡ Domain 3
### Design High-Performing Architectures

#### **3.1** Storage Solutions

| # | Service / Concept | Use Case |
|---|-------------------|----------|
| 1 | **Amazon S3** | Object storage: scalable, durable, lifecycle policies |
| 2 | **Amazon EBS** | Block storage for EC2: SSD (gp3, io2) or HDD (st1, sc1) |
| 3 | **Amazon EFS** | Managed NFS: shared file storage for Linux workloads |
| 4 | **Amazon FSx** | Managed file systems: Windows (SMB), Lustre (HPC), NetApp, OpenZFS |
| 5 | **AWS Storage Gateway** | Hybrid storage: file, volume, tape gateway types |
| 6 | **Storage Types** | Object vs File vs Block: know performance and use-case differences |
| 7 | **S3 Storage Classes** | Standard, Intelligent-Tiering, IA, Glacier, Glacier Deep Archive |

#### **3.2** Compute Solutions

| # | Service / Concept | Use Case |
|---|-------------------|----------|
| 1 | **Amazon EC2** | Virtual machines: choose instance type/family for workload |
| 2 | **EC2 Auto Scaling** | Automatically add/remove instances based on demand |
| 3 | **AWS Lambda** | Serverless functions: event-driven, scale to zero |
| 4 | **AWS Fargate** | Serverless containers: no EC2 management needed |
| 5 | **Amazon ECS** | Container orchestration on EC2 or Fargate |
| 6 | **Amazon EKS** | Managed Kubernetes: supports Anywhere and Distro variants |
| 7 | **AWS Batch** | Managed batch processing: compute-intensive jobs |
| 8 | **Amazon EMR** | Big data on managed Hadoop/Spark clusters |
| 9 | **AWS Elastic Beanstalk** | PaaS: deploy web apps without managing infrastructure |
| 10 | **AWS Outposts** | AWS infrastructure on-premises (hybrid) |
| 11 | **AWS Wavelength** | Deploy workloads at the edge of 5G networks |

#### 3.3 Database Solutions

| # | Service / Concept | Use Case |
|---|-------------------|----------|
| 1 | **Amazon RDS** | Managed relational DB: MySQL, PostgreSQL, SQL Server, Oracle, MariaDB |
| 2 | **Amazon Aurora** | High-performance relational DB (MySQL/PostgreSQL compatible) |
| 3 | **Aurora Serverless** | On-demand autoscaling for Aurora (v2 generally available) |
| 4 | **Amazon DynamoDB** | Serverless NoSQL: millisecond latency at any scale |
| 5 | **Amazon ElastiCache** | In-memory caching: Redis (complex data) vs Memcached (simple) |
| 6 | **Amazon Redshift** | Data warehouse: columnar storage for analytics queries |
| 7 | **Amazon DocumentDB** | Managed MongoDB-compatible document database |
| 8 | **Amazon Neptune** | Graph database for connected data (social graphs, fraud detection) |
| 9 | **Amazon Keyspaces** | Managed Apache Cassandra-compatible service |
| 10 | **Read Replicas** | Offload read traffic & know when to use vs Multi-AZ |
| 11 | **Caching Patterns** | Cache-aside, write-through, TTL strategies |
| 12 | **DB Capacity Planning** | Capacity Units (DynamoDB), Provisioned IOPS, instance sizing |

#### **3.4** Network Architectures

| # | Service / Concept | Use Case |
|---|-------------------|----------|
| 1 | **Amazon VPC** | Isolated virtual network: subnets, route tables, IGW, NAT |
| 2 | **Amazon CloudFront** | CDN: cache content at edge locations globally |
| 3 | **AWS Global Accelerator** | Route users to optimal endpoints using AWS global network |
| 4 | **Elastic Load Balancing** | ALB (HTTP/S), NLB (TCP/UDP), GLB (appliances) |
| 5 | **AWS Direct Connect** | Dedicated private line to AWS (predictable performance) |
| 6 | **AWS Transit Gateway** | Hub-and-spoke for connecting many VPCs and on-prem networks |
| 7 | **VPC Peering** | Direct VPC-to-VPC connectivity (no transitive routing) |
| 8 | **AWS PrivateLink** | Private access to AWS services and third-party services |
| 9 | **Amazon Route 53** | DNS. Routing policies: simple, weighted, latency, failover, geolocation |
| 10 | **Network Topology** | Global, hybrid, multi-tier & design for scale |

#### **3.5** Data Ingestion and Transformation

| # | Service / Concept | Use Case |
|---|-------------------|----------|
| 1 | **Amazon Kinesis** | Real-time streaming data: Data Streams, Data Firehose, Video Streams |
| 2 | **Amazon Data Firehose** | Load streaming data to S3, Redshift, OpenSearch |
| 3 | **AWS Glue** | Serverless ETL: transform and catalog data |
| 4 | **Amazon Athena** | Serverless SQL queries on S3 data |
| 5 | **AWS Lake Formation** | Build, secure, and manage data lakes on S3 |
| 6 | **Amazon EMR** | Process large datasets with Hadoop, Spark, Hive |
| 7 | **Amazon MSK** | Managed Apache Kafka for streaming pipelines |
| 8 | **AWS DataSync** | Automate data transfer between on-prem and AWS storage |
| 9 | **AWS Transfer Family** | Managed SFTP/FTPS/FTP to S3 or EFS |
| 10 | **Amazon QuickSuite** | BI and data visualization service |
| 11 | **Amazon OpenSearch** | Search and analytics & also supports vector similarity (RAG) |
| 12 | **Amazon Redshift** | Query structured data at petabyte scale |

---

## 💰 Domain 4
### Design Cost-Optimized Architectures

#### **4.1** Cost-Optimized Storage

| # | Concept | What to Know |
|---|---------|--------------|
| 1 | **S3 Storage Classes** | Match class to access frequency & Glacier for archival |
| 2 | **S3 Lifecycle Policies** | Automate transitions between storage classes |
| 3 | **S3 Intelligent-Tiering** | Auto-move objects between tiers based on access patterns |
| 4 | **EBS Volume Types** | gp3 vs io2 vs st1 vs sc1 & match to IOPS and cost needs |
| 5 | **Requester Pays** | Transfer cost charged to requester, not bucket owner |
| 6 | **Data Lifecycle Management** | Retain only what's needed & expire or archive the rest |
| 7 | **Hybrid Storage** | DataSync, Transfer Family, Storage Gateway for on-prem cost reduction |
| 8 | **Backup Strategy** | Balance recovery needs with cost (snapshots, replication) |

#### 4.2 Cost-Optimized Compute

| # | Concept | What to Know |
|---|---------|--------------|
| 1 | **On-Demand Instances** | Pay per use: highest flexibility, highest per-hour cost |
| 2 | **Reserved Instances** | 1 or 3 year commitment: up to 72% savings |
| 3 | **Savings Plans** | Flexible commitment (Compute, EC2, SageMaker) |
| 4 | **Spot Instances** | Up to 90% savings for fault-tolerant/interruptible workloads |
| 5 | **AWS Compute Optimizer** | ML-based recommendations for right-sizing EC2, Lambda, EBS |
| 6 | **AWS Serverless Application Repository** | Pre-built serverless apps: reduce build cost |
| 7 | **EC2 Hibernation** | Save instance state to EBS: resume without full reboot |
| 8 | **Containerization** | ECS/EKS/Fargate for higher density and cost efficiency |
| 9 | **Instance Families** | General purpose, compute optimized, memory optimized, storage optimized |
| 10 | **VMware Cloud on AWS** | Extend VMware workloads to AWS without refactoring |

#### **4.3** Cost-Optimized Databases

| # | Concept | What to Know |
|---|---------|--------------|
| 1 | **DynamoDB On-Demand vs Provisioned** | On-demand for unpredictable; provisioned for predictable + cheaper |
| 2 | **Aurora Serverless** | Pay per ACU-hour: ideal for intermittent workloads |
| 3 | **RDS Reserved Instances** | Commit to 1 or 3 years for significant savings |
| 4 | **Read Replicas** | Offload reads to reduce primary DB load (and cost) |
| 5 | **DB Snapshot Policies** | Balance frequency vs storage cost |
| 6 | **Caching** | ElastiCache reduces DB query load and cost |
| 7 | **Data Retention Policies** | Define how long to keep data: archive vs delete |
| 8 | **Right-Sized DB Instances** | Don't over-provision: use metrics to guide sizing |

#### 4.4 Cost-Optimized Network Architectures

| # | Concept | What to Know |
|---|---------|--------------|
| 1 | **NAT Gateway vs NAT Instance** | NAT Gateway scales automatically but costs more & NAT instance is cheaper at low traffic |
| 2 | **VPC Endpoints** | Eliminate NAT costs for S3/DynamoDB & use Gateway Endpoints (free) |
| 3 | **Direct Connect vs VPN** | Direct Connect more expensive but predictable; VPN cheaper for low volume |
| 4 | **Region-to-Region Transfer** | Data egress fees apply & minimize cross-region traffic |
| 5 | **Same-AZ Traffic** | Free & architect to keep traffic within same AZ where possible |
| 6 | **CloudFront** | Reduce origin data transfer costs with edge caching |
| 7 | **Transit Gateway Pricing** | Attachment + data processing fees & evaluate vs VPC peering |
| 8 | **Throttling Strategy** | Use API Gateway throttling to control overuse and cost spikes |

---

## 🛠️ AWS Cost Management Tools

| Tool | Purpose |
|------|---------|
| **AWS Cost Explorer** | Visualize and analyze historical spend and forecast costs |
| **AWS Budgets** | Set spend/usage thresholds with alerts |
| **AWS Cost and Usage Report** | Granular billing data exportable to S3 |
| **Savings Plans** | Flexible commitment model for compute savings |
| **Cost Allocation Tags** | Tag resources to attribute costs to teams/projects |
| **AWS Compute Optimizer** | Right-sizing recommendations based on usage |
| **AWS Trusted Advisor** | Best-practice checks across cost, security, performance |
| **AWS Well-Architected Tool** | Review architecture against the Well-Architected Framework |

---

## 💡 Disaster Recovery Strategy Comparison

| Strategy | RPO | RTO | Cost | Description |
|---|---|---|---|---|
| **Backup & Restore** | Hours | Hours | 💰 Lowest | Back up to S3/Glacier & restore on failure |
| **Pilot Light** | Minutes | 10s of minutes | 💰💰 | Core services always running &scale up on failure |
| **Warm Standby** | Seconds/Minutes | Minutes | 💰💰💰 | Scaled-down live environment & quickly scale to full |
| **Active-Active** | Near zero | Near zero | 💰💰💰💰 Highest | Full duplicate environment & traffic split between sites |

---

## 🔑 Key Abbreviations

| Abbreviation | Full Term |
|---|---|
| **IAM** | Identity and Access Management |
| **SCP** | Service Control Policy |
| **MFA** | Multi-Factor Authentication |
| **STS** | Security Token Service |
| **ACM** | AWS Certificate Manager |
| **KMS** | Key Management Service |
| **VPC** | Virtual Private Cloud |
| **NACL** | Network Access Control List |
| **ALB** | Application Load Balancer |
| **NLB** | Network Load Balancer |
| **GLB** | Gateway Load Balancer |
| **CDN** | Content Delivery Network |
| **RPO** | Recovery Point Objective |
| **RTO** | Recovery Time Objective |
| **DR** | Disaster Recovery |
| **EBS** | Elastic Block Store |
| **EFS** | Elastic File System |
| **FSx** | Amazon FSx (managed file systems) |
| **SQS** | Simple Queue Service |
| **SNS** | Simple Notification Service |
| **ETL** | Extract, Transform, Load |
| **HDD** | Hard Disk Drive |
| **SSD** | Solid State Drive |
| **IOPS** | Input/Output Operations Per Second |
| **RI** | Reserved Instance |
| **ACU** | Aurora Capacity Unit |
| **PII** | Personally Identifiable Information |
| **SSO** | Single Sign-On |

---

## 🚀 In Scope AWS Services Quick Reference
### Compute
Amazon EC2 · EC2 Auto Scaling · AWS Lambda · AWS Fargate · AWS Elastic Beanstalk · AWS Batch · AWS Outposts · VMware Cloud on AWS · AWS Wavelength · AWS Serverless Application Repository

### Containers
Amazon ECR · Amazon ECS · ECS Anywhere · Amazon EKS · EKS Anywhere · Amazon EKS Distro

### Storage
Amazon S3 · Amazon EBS · Amazon EFS · Amazon FSx · AWS Storage Gateway · AWS Snow Family

### Database
Amazon RDS · Amazon Aurora · Aurora Serverless · Amazon DynamoDB · Amazon ElastiCache · Amazon Redshift · Amazon DocumentDB · Amazon Neptune · Amazon Keyspaces

### Networking & Content Delivery
Amazon VPC · Amazon CloudFront · AWS Direct Connect · Elastic Load Balancing · AWS Global Accelerator · AWS PrivateLink · Amazon Route 53 · AWS Site-to-Site VPN · AWS Client VPN · AWS Transit Gateway

### Analytics
Amazon Athena · Amazon EMR · AWS Glue · Amazon Kinesis · Amazon Data Firehose · Amazon Kinesis Video Streams · Amazon MSK · Amazon OpenSearch Service · Amazon QuickSuite · Amazon Redshift · AWS Lake Formation · AWS Data Exchange

### Application Integration
Amazon SQS · Amazon SNS · Amazon EventBridge · Amazon MQ · AWS Step Functions · Amazon AppFlow · AWS AppSync

### Security, Identity & Compliance
AWS IAM · AWS IAM Identity Center · Amazon Cognito · AWS KMS · AWS CloudHSM · AWS ACM · Amazon GuardDuty · Amazon Macie · Amazon Detective · AWS Shield · AWS WAF · AWS Secrets Manager · AWS Directory Service · AWS Artifact · AWS Audit Manager

### Management & Governance
AWS Organizations · AWS Control Tower · AWS CloudFormation · AWS CloudTrail · Amazon CloudWatch · AWS Config · AWS Systems Manager · AWS Auto Scaling · AWS Compute Optimizer · AWS Trusted Advisor · AWS Well-Architected Tool · AWS Service Catalog · AWS Health Dashboard · AWS License Manager · Amazon Managed Grafana · Amazon Managed Service for Prometheus

### Migration & Transfer
AWS DMS · AWS DataSync · AWS Snow Family · AWS Transfer Family · AWS Application Migration Service

### Machine Learning
Amazon SageMaker AI · Amazon Comprehend · Amazon Kendra · Amazon Lex · Amazon Polly · Amazon Rekognition · Amazon Textract · Amazon Transcribe · Amazon Translate

### Cost Management
AWS Budgets · AWS Cost Explorer · AWS Cost and Usage Report · Savings Plans

### Developer Tools
AWS X-Ray

### Serverless
AWS Lambda · AWS Fargate · Amazon API Gateway · Amazon DynamoDB · Amazon EventBridge · Amazon SQS · Amazon SNS

---

> ⚠️ **Important:** Always refer to the official exam guide for the most up-to-date list of in-scope and out-of-scope services.

---

## 📚 Additional Resources

1. [AWS Certified Solutions Architect – Associate (SAA-C03) Exam Guide (PDF)](https://docs.aws.amazon.com/pdfs/aws-certification/latest/solutions-architect-associate-03/solutions-architect-associate-03.pdf)
2. [AWS Certification: All Exam Guides](https://docs.aws.amazon.com/pdfs/aws-certification/latest/examguides/aws-certification-exam-guides.pdf)
3. [Exam Guide: Solutions Architect Associate Series](https://dev.to/ntombizakhona/series/35366)

---

**Good luck with your exam! 🚀**

---

# The Original

**Blog:** [Ntombizakhona Mabaso](https://dev.to/ntombizakhona)
<br>
**Article Link:** [Technologies and Concepts](https://dev.to/aws-builders/technologies-and-concepts-cheat-sheet-for-solutions-architect-associate-saa-c03-h52)
<br>
Originally Published by [Ntombizakhona Mabaso](https://dev.to/ntombizakhona)
<br>
**22 April 2026**
