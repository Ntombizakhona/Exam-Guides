**Exam Guide:** Developer - Associate
**Technologies And Concepts Cheat Sheet**
📘 Cheat Sheet

## 1 | Services

### Compute

| **Service** | _What It Does_ | Key Points |
|---------|-------------|-----------------|
| **Lambda** | _Serverless Functions_ | `15 min` timeout, `10240 MB` memory max, `1000` default concurrency |
| **EC2** | _Virtual Servers_ | Instance profiles for IAM roles, user data for bootstrap |
| **ECS/Fargate** | _Container Orchestration_ | Task roles for IAM, Fargate = serverless containers |
| **Elastic Beanstalk** | _PaaS Deployment_ | **`.ebextensions`** for config, supports rolling/immutable/blue-green |

### Storage & Databases

| **Service** | _What It Does_ | Key Points |
|---------|-------------|-----------------|
| **DynamoDB** | _NoSQL key-value_ | Partition keys, GSI/LSI, query vs scan, DAX for caching |
| **S3** | _Object Storage_ | SSE-S3/SSE-KMS/SSE-C, lifecycle policies, presigned URLs |
| **ElastiCache** | _In-memory Cache_ | **`Redis`** (complex types, persistence) vs **`Memcached`** (simple, multi-threaded) |
| **RDS** | _Relational Database_ | RDS Proxy for Lambda connection pooling, read replicas |
| **OpenSearch** | _Search & Analytics_ | Full-text search, log analytics |

### API & Integration

| **Service** | _What It Does_ | Key Points |
|---------|-------------|-----------------|
| **API Gateway** | _REST/HTTP/WebSocket APIs_ | Stages, authorizers, caching, request validation, throttling |
| **SQS** | _Message Queue_ | **`Standard`** (at-least-once) vs **`FIFO`** (exactly-once), visibility timeout, DLQ |
| **SNS** | _Pub/sub messaging_ | Fanout, filter policies, message attributes |
| **EventBridge** | _Event Bus_ | Pattern matching, content-based filtering, multiple targets |
| **Kinesis** | _Real-time Streaming_ | Shards, partition keys, parallelization factor |
| **Step Functions** | _Workflow Orchestration_ | **`Standard`** (long-running) vs **`Express`** (high-volume, short) |

### Security

| **Service** | _What It Does_ | Key Points |
|---------|-------------|-----------------|
| **IAM** | _Access Management_ | Policies, roles, least privilege, STS AssumeRole |
| **Cognito** | _User Auth_ | **`User Pools`** (tokens) vs **`Identity Pools`** (AWS credentials) |
| **KMS** | _Key Management_ | Envelope encryption, 4 KB limit, key rotation, cross-account |
| **Secrets Manager** | _Secret Storage_ | Auto-rotation, $0.40/secret/month |
| **SSM Parameter Store** | _Config Storage_ | **`Standard`** (free) vs **`Advanced`**, SecureString type |
| **ACM** | _SSL/TLS Certificates_ | Free public certs, auto-renewal, can't export |

### CI/CD

| **Service** | _What It Does_ | Key Points |
|---------|-------------|-----------------|
| **CodeCommit** | _Git Repository_ | Triggers pipelines on push |
| **CodeBuild** | _Build Service_ | **`buildspec.yml`**, supports Docker |
| **CodeDeploy** | _Deployment Service_ | **`appspec.yml`**, blue/green/canary/rolling |
| **CodePipeline** | _CI/CD Orchestration_ | Source → Build → Test → Deploy stages |
| **SAM** | _Serverless Framework_ | **`template.yaml`**, sam build/deploy, local testing |
| **CloudFormation** | _IaC_ | Templates, stacks, change sets, !Sub, !Ref, parameters |
| **AppConfig** | _Runtime Config_ | Feature flags, gradual rollout, validation |

### Observability

| **Service** | _What It Does_ | Key Points |
|---------|-------------|-----------------|
| **CloudWatch Logs** | _Log storage & Query_ | Logs Insights query language, log groups, retention |
| **CloudWatch Metrics** | _Metric Tracking_ | Custom metrics, EMF, math expressions |
| **CloudWatch Alarms** | _Alerting_ | Metric alarms, composite alarms, SNS actions |
| **X-Ray** | _Distributed Tracing_ | Segments, subsegments, annotations (indexed), metadata (not indexed) |
| **CloudTrail** | _API Audit Log_ | Who did what? when? & Debug permission issues |

---

## 2 | Numbers

| **Item** | `Limit` |
|------|-------|
| **Lambda timeout** | `15 minutes` |
| **Lambda memory** | `128 MB – 10,240 MB` |
| **Lambda /tmp storage** | `512 MB – 10,240 MB` |
| **Lambda deployment** (zip) | `50 MB` compressed, `250 MB` uncompressed |
| **Lambda deployment** (container) | `10 GB` |
| **Lambda layers** | `5` per function, `250 MB` total unzipped |
| **Lambda concurrency** (default) | `1,000` per region |
| **KMS direct encryption** | `4 KB` max |
| **SQS message size** | `256 KB` |
| **SQS visibility timeout** |` 0s – 12 hours` (default 30s) |
| **SQS retention** | `1 minute – 14 days` (default 4 days) |
| **SNS message size** | `256 KB` |
| **DynamoDB item size** | `400 KB` |
| **DynamoDB GSI** | `20` per table |
| **DynamoDB LSI** | `5` per table |
| **API Gateway timeout** | `29 seconds` |
| **API Gateway payload** | `10 MB` |
| **S3 object size** | `5 TB` (5 GB per PUT, use multipart for larger) |
| **Secrets Manager secret size** | `64 KB` |
| **SSM Parameter Store** (standard) | `4 KB` |
| **SSM Parameter Store** (advanced) | `8 KB` |
| **Step Functions Standard **| `1 year` execution |
| **Step Functions Express** | `5 minutes` execution |

---

## 3 | Patterns

### Decoupling
- **SQS:** point-to-point, one consumer, buffering
- **SNS:** fanout, multiple consumers
- **SNS + SQS:** fanout with reliable delivery
- **EventBridge:** complex routing, content-based filtering

### Caching
- **DAX:** DynamoDB reads only, microsecond latency
- **ElastiCache Redis:** general purpose, complex data types
- **ElastiCache Memcached:** simple caching, multi-threaded
- **CloudFront:** edge caching for APIs and static content
- **API Gateway cache:** per-stage, per-method caching

### Authentication
- **Cognito User Pool:** user sign-up/sign-in, JWT tokens
- **Cognito Identity Pool:** temporary AWS credentials
- **Lambda authorizer:** custom auth logic
- **IAM authorization:** service-to-service with SigV4

### Deployment
- **AllAtOnce:** fastest, highest risk
- **Canary:** small % first, then all (safest)
- **Linear:** gradual rollout over time
- **Blue/Green:** two environments, instant switch

### Error Handling
- **DLQ:** capture failed messages (SQS, Lambda async)
- **Lambda Destinations:** route success AND failure (preferred over DLQ)
- **ReportBatchItemFailures:** partial batch failure for SQS
- **BisectBatchOnFunctionError:** split Kinesis batch to isolate bad records
- **Step Functions:** retry and catch at the workflow level

---

## 4 | Versus

### SQS Standard vs FIFO

| **Feature** | _Standard_ | FIFO |
|---------|----------|------|
| **Throughput** | _Unlimited_ | 300 msg/s (3000 batched) |
| **Ordering** | _Best effort_ | Guaranteed |
| **Delivery** | _At least once_ | Exactly once |
| **Deduplication** | _No_ | Yes (5 min window) |

### Secrets Manager vs Parameter Store

| **Feature** | _Secrets Manager_ | Parameter Store |
|---------|----------------|-----------------|
| **Auto Rotation** | _Built-in_ | DIY |
| **Cost** | _$0.40/secret/month_ | Free (standard) |
| **Max Size** | _64 KB_ | 4 KB / 8 KB |
| **Cross-Account** | _Yes_ | Yes (advanced) |

### Step Functions Standard vs Express

| **Feature** | _Standard_ | Express |
|---------|----------|---------|
| **Max Duration** | _1 year_ | 5 minutes |
| **Execution Model** | _Exactly once_ | At least once |
| **Pricing** | _Per state transition_ | Per execution + duration |
| **Use Case** | _Long-running workflows_ | High-volume, short tasks |

---

## 5 | Cram
1. **Lambda in VPC** loses internet access → needs NAT Gateway or VPC endpoints
2. **DynamoDB FilterExpression** doesn't reduce read capacity consumed
3. **GSIs** are eventually consistent only. No strongly consistent reads
4. **DynamoDB uses Decimal, not float** in Python
5. **TTL deletion** can take up to 48 hours after expiration
6. **API Gateway timeout** is 29 seconds. Can't be increased
7. **SQS FIFO** throughput is 300 msg/s (3000 with batching) vs Standard (unlimited)
8. **Lambda Destinations** only work with async invocations
9. **Provisioned concurrency** costs money even when idle
10. **SSE-C:** you manage the key, AWS doesn't store it. Lose the key = lose the data.
11. **CloudFormation !Ref** returns different things for different resources (ARN, name, ID)
12. **SAM transforms** to CloudFormation: `sam build` is required before `sam deploy`
13. **X-Ray annotations** are indexed and searchable. **Metadata** is not.
14. **EMF** is cheaper than PutMetricData for Lambda custom metrics
15. **SQS long polling** `(WaitTimeSeconds > 0)` reduces empty responses and costs

---

🏗️

---

# The Original

**Blog:** [Ntombizakhona Mabaso](https://dev.to/ntombizakhona)
<br>
**Article Link:** [Technologies And Concepts](https://dev.to/aws-builders/technologies-and-concepts-cheat-sheet-for-developer-associate-dva-c02-2jbp)
<br>
Originally Published by [Ntombizakhona Mabaso](https://dev.to/ntombizakhona)
<br>
**21 July 2026**
