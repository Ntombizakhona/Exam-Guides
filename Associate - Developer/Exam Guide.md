## What Is the AWS Certified Developer – Associate?

The AWS Certified Developer – Associate (DVA-C02) validates your ability to develop, test, deploy, and debug cloud-based applications using AWS. It's aimed at developers with at least one year of hands-on experience building and maintaining AWS applications.

This isn't a theory-only exam. The questions are scenario-based. You'll be given a situation and asked to pick the best approach. 

That means you need to understand not just *what* a service does, but *when* and *how* to use it in real code.

---

## Exam Format

| Detail | Value |
|--------|-------|
| Exam code | DVA-C02 |
| Questions | 65 |
| Duration | 130 minutes |
| Format | Multiple choice + multiple select |
| Passing score | 720 / 1000 |
| Cost | $150 USD |
| Validity | 3 years |

Multiple choice questions have one correct answer out of four. 
Multiple select questions tell you how many answers to pick (usually two out of five).

---

## The Four Domains

The exam is split into four domains, each with a different weight:

| Domain | Weight | ~Questions |
|--------|--------|------------|
| 1. Development with AWS Services | 32% | ~21 |
| 2. Security | 26% | ~17 |
| 3. Deployment | 24% | ~16 |
| 4. Troubleshooting and Optimization | 18% | ~11 |

**Development** is the biggest chunk, but **Security** is close behind. 
Don't sleep on **Deployment.**
Nearly a quarter of the exam is CI/CD, IaC, and deployment strategies.

---

## Domain 1
### Development with AWS Services 
**(32%)**

This is the core of the exam. 
You need to write code that works with AWS services, not just click through the console.

#### **Task 1.1 Develop code for applications hosted on AWS**
- Architectural patterns: event-driven, microservices, fanout, choreography vs orchestration
- Stateful vs stateless, tightly vs loosely coupled, sync vs async
- Building and maintaining APIs with API Gateway
- Writing unit tests with SAM
- Using messaging services (SQS, SNS, EventBridge)
- Working with AWS SDKs
- Handling streaming data (Kinesis)
- Resilient code: retry logic, circuit breakers, error handling

#### **Task 1.2: Develop code for AWS Lambda**
- VPC access from Lambda
- Configuration: memory, timeout, concurrency, layers, extensions, triggers, destinations
- Error handling: DLQs, Lambda Destinations
- Testing Lambda functions
- Performance tuning
- Real-time data processing

#### **Task 1.3: Use data stores in application development**
- DynamoDB: partition keys, GSIs, LSIs, query vs scan, consistency models
- Data serialization and persistence
- Data lifecycle management (TTL)
- Caching with ElastiCache and DAX
- Specialized stores like OpenSearch

---

## Domain 2
### Security 
**(26%)**

Security is woven into everything on this exam. 
Expect questions that combine security with development scenarios.

#### **Task 2.1: Implement authentication and authorization**
- Cognito User Pools and Identity Pools
- JWT tokens and bearer token validation
- IAM roles, policies, and STS AssumeRole
- Lambda authorizers
- Cross-service auth in microservices

#### **Task 2.2: Implement encryption using AWS services**
- Encryption at rest vs in transit
- KMS: key creation, rotation, cross-account access
- Client-side vs server-side encryption
- AWS Encryption SDK
- Certificate management

#### **Task 2.3: Manage sensitive data in application code**
- Secrets Manager vs SSM Parameter Store
- Encrypting Lambda environment variables
- Data classification (PII, PHI)
- Data masking and sanitization
- Multi-tenant data isolation

---

## Domain 3
### Deployment 
**(24%)**

This domain is all about getting code from your machine to production safely and repeatably.

#### **Task 3.1: Prepare application artifacts for deployment**
- Packaging Lambda functions with dependencies
- Container images and ECR
- AWS AppConfig for feature flags and configuration
- Project structure for SAM/CloudFormation

#### **Task 3.2: Test applications in development environments**
- SAM local testing
- Integration tests against API Gateway stages
- Mocking external dependencies
- Testing event-driven applications

#### **Task 3.3: Automate deployment testing**
- Test events for Lambda and API Gateway
- Lambda aliases and versions
- IaC templates (SAM, CloudFormation)
- Environment management
- Amazon Q Developer for test generation

#### **Task 3.4: Deploy code using AWS CI/CD services**
- CodePipeline, CodeBuild, CodeDeploy
- Deployment strategies: blue/green, canary, rolling
- Rollback strategies
- API Gateway stages and custom domains
- Dynamic deployments with staging variables

---

## Domain 4
### Troubleshooting and Optimization 
**(18%)**

The smallest domain, but the questions can be tricky because they require you to diagnose problems from logs and metrics.

#### **Task 4.1: Assist in root cause analysis**
- Debugging code and interpreting error messages
- CloudWatch Logs, metrics, and traces
- CloudWatch Logs Insights queries
- Custom metrics with Embedded Metric Format
- Troubleshooting deployment failures

#### **Task 4.2: Instrument code for observability**
- Logging vs monitoring vs observability
- Structured logging with correlation IDs
- X-Ray tracing: segments, subsegments, annotations
- CloudWatch alarms and SNS notifications
- Health checks and readiness probes

#### **Task 4.3: Optimize applications**
- Lambda concurrency and performance tuning
- CloudFront caching strategies
- ElastiCache for application-level caching
- SNS subscription filter policies
- Identifying bottlenecks from logs and metrics

---

## Key AWS Services to Know

Here's a quick reference of the services that come up most on this exam:

**Compute:** Lambda, EC2, ECS, Fargate, Elastic Beanstalk

**API & Integration:** API Gateway, EventBridge, Step Functions, SQS, SNS, Kinesis

**Data:** DynamoDB, S3, ElastiCache, DAX, RDS, OpenSearch

**Security:** IAM, Cognito, KMS, Secrets Manager, SSM Parameter Store, ACM

**CI/CD:** CodePipeline, CodeBuild, CodeDeploy, CloudFormation, SAM, AppConfig

**Observability:** CloudWatch (Logs, Metrics, Alarms, Dashboards), X-Ray, CloudTrail

**Developer Tools:** AWS SDK, AWS CLI, SAM CLI, Amazon Q Developer

---

## How This Series Is Structured

Each article in this series maps directly to an exam task. We'll (You and I...and perhaps your AI Assistant, since that's how we do things these days) cover the concepts you need to know, then get hands-on with real code and CLI commands. 

The goal is that by the end of the series, you've not only studied the material but you've built things with it...

---

## Before You Start

**Recommended experience:**
- At least 1 year developing and maintaining AWS applications
- Comfortable with at least one programming language (Python, JavaScript/TypeScript, Java, C#, or Go)
- Familiar with the AWS Console, CLI, and at least one AWS SDK

**What you'll need to follow along:**

**1.** An AWS account (free tier covers most of what we'll do)
**2.** AWS CLI v2 installed and configured
**3.** SAM CLI installed
**4.** A code editor (VS Code recommended)
**5.** Python 3.12+ or Node.js 20+ (we'll use both in examples)

---

## Additional Resources
1. [AWS Certified Developer Associate Exam Guide](https://d1.awsstatic.com/training-and-certification/docs-dev-associate/AWS-Certified-Developer-Associate_Exam-Guide.pdf)
2. [AWS Certified Developer - Associate Exam Guide (DVA-C02)](https://docs.aws.amazon.com/aws-certification/latest/developer-associate-02/developer-associate-02-domain1.html)

🚀

---

# The Original

**Blog:** [Ntombizakhona Mabaso](https://dev.to/ntombizakhona)
<br>
**Article Link:** [Developer Associate Exam Guide](https://dev.to/aws-builders/developer-associate-exam-guide-56ln)
<br>
Originally Published by [Ntombizakhona Mabaso](https://dev.to/ntombizakhona)
<br>
**24 April 2026**

