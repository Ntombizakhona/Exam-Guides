## 📘 The **AWS Certified DevOps Engineer – Professional (DOP-C02)**

The **AWS Certified DevOps Engineer – Professional (DOP-C02)** isn't an exam you pass by memorising AWS services. It's an exam about **building, automating, operating, and improving production systems**.

This series follows the **official DOP-C02 Exam Guide (Version 1.6)**, with every article mapped directly to one or more **official task statements**. Rather than covering services in isolation, each article focuses on the skills AWS expects a DevOps engineer to demonstrate in _real-world_ environments.

Unlike my [**Developer Associate**](url) series, this guide is unapologetically **terminal-first**.

At the Associate level, the AWS Management Console is a useful learning tool. But, at the Professional level, excessive **clickops** becomes a liability. DevOps is built on automation, repeatability, and Infrastructure as Code. Not clicking through web pages.


## 🏗️ Hands-On Principles

Every practical exercise in this series follows the same principles.

* **Terminal-first:** Everything is executed from your local machine or the AWS CloudShell.
* **Automation over clickops:** If it can be accomplished using the AWS CLI, Infrastructure as Code, or a script, that's the approach we'll take.
* **Reproducible by design:** Every command is copy-and-pasteable, and every environment can be recreated from version-controlled code.
* **Production mindset:** Infrastructure is treated as code, not something manually configured through the console.
* **Clean up after yourself:** Every hands-on lab includes teardown steps to avoid leaving billable resources running.

## Local Environment Prerequisites

Before beginning the series, you should have the following installed and configured:

* AWS CLI v2
* Git
* `jq`
* A code editor (Visual Studio Code recommended)
* AWS SAM CLI
* AWS CDK
* CloudFormation

Recommended tools:

* `cfn-lint` for CloudFormation template validation
* AWS Session Manager plugin for secure instance access without SSH keys or bastion hosts

---

# Exam Overview

| **Item**                       | Details                               |
| -------------------------- | ------------------------------------- |
| **Exam Code**              | DOP-C02 (Exam Guide Version 1.6)      |
| **Questions**              | 75 total (65 scored, 10 unscored)     |
| **Question Types**         | Multiple Choice and Multiple Response |
| **Duration**               | 180 minutes                           |
| **Scoring**                | 100–1,000 (Passing score: 750)        |
| **Exam Cost**              | USD $300                              |
| **Certification Validity** | 3 years                               |

AWS uses a **compensatory scoring model**, meaning you do not need to pass every domain individually. Strong performance in one domain can offset weaker performance in another.

---

## Target Candidate

AWS recommends at least **two years of experience** provisioning, operating, and managing AWS environments, along with practical experience in software development lifecycles, automation, and scripting.

The certification validates your ability to:

* Implement and manage CI/CD systems on AWS
* Build automated testing and deployment pipelines
* Implement Infrastructure as Code at scale
* Automate security controls, governance, and compliance
* Design highly available, scalable, and self-healing systems
* Build monitoring, logging, and observability solutions
* Automate operational and incident response workflows

### Topics Outside the Scope

The exam does **not** expect deep expertise in:

* Advanced networking theory and routing algorithms
* Database design or query optimization
* Full-stack application development
* Writing application business logic
* Deep security architecture beyond operational implementation

---

# Domains, Weightings, and Task Statements

| Domain                                                     | **`Weight`**  | Task Statements                                                                                             |
| ---------------------------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------- |
| **1. SDLC Automation**                                     | **`22%`** | **1.1** CI/CD pipelines · **1.2** Automated testing · **1.3** Artifact management · **1.4** Deployment strategies           |
| **2. Configuration Management and Infrastructure as Code** | **`17%`** | **2.1** IaC and reusable components · **2.2** Multi-account and multi-Region automation · **2.3** Automation at scale   |
| **3. Resilient Cloud Solutions**                           | **`15%`** | **3.1** High availability · **3.2** Scalability · **3.3** Automated recovery (RTO/RPO)                                  |
| **4. Monitoring and Logging**                              | **`15%`** | **4.1** Collecting logs and metrics · **4.2** Auditing and analysis · **4.3** Automated monitoring and event management |
| **5. Incident and Event Response**                         | **`14%`** | **5.1** Event sources · **5.2** Automated configuration changes · **5.3** Failure investigation and remediation         |
| **6. Security and Compliance**                             | **`17%`** | **6.1** IAM at scale · **6.2** Security controls and data protection · **6.3** Security monitoring and auditing         |

---

Throughout this series, you'll (we'll...I'll) build and manage AWS resources from **y(our) own local machine** using the tools professional engineers rely on every day:

* AWS CLI
* Infrastructure as Code (CloudFormation, AWS SAM, and AWS CDK)
* Shell scripting
* Git
* JSON tooling
* Automation workflows

The AWS Console still appears when it provides useful visibility or helps explain a concept, but it is never the primary way of completing a task.

> **💡The goal isn't simply to pass the exam. It's to build the habits and workflows expected of a professional DevOps engineer.**

---

🏗️



---

# The Original

**Blog:** [Ntombizakhona Mabaso](https://dev.to/ntombizakhona)
<br>
**Article Link:** [Exam Guide](https://dev.to/aws-builders/devops-engineer-professional-exam-guide-4j35)
<br>
Originally Published by [Ntombizakhona Mabaso](https://dev.to/ntombizakhona)
<br>
**24 July 2026**

