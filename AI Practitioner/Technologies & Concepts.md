🤖 **Exam Guide:** AI Practitioner
**Technologies And Concepts Cheat Sheet**
📘_Cheat Sheet_

> **Note:** Unlike the CLF-C02 exam guide, AIF-C01 does not include a dedicated "Technologies & Concepts" section. Instead, services and concepts are embedded within task statements across all five domains.  
>  
> This cheat sheet consolidates that information into a **compact, exam-aligned reference** organized by domain—designed for quick review and efficient study.

---

## 📖 Domain 1
### Fundamentals of AI & ML

#### 1.1 **Key Terms**

| # | Term | Definition |
|---|------|------------|
| 1 | **AI** | Broad field of machine intelligence |
| 2 | **ML** | AI that learns patterns from data |
| 3 | **Deep Learning** | ML using multi-layer neural networks |
| 4 | **Model** | Trained artifact that maps inputs → outputs |
| 5 | **Algorithm** | Method for learning/inference (e.g., regression, trees, neural nets) |
| 6 | **Training vs Inference** | Learning parameters vs using the model to predict/generate |
| 7 | **Fit** | Underfitting vs overfitting |
| 8 | **Bias & Fairness** | Systematic skew and its impact on groups/outcomes |

#### 1.2 **Learning Types**

| # | Type | Description |
|---|------|-------------|
| 1 | **Supervised** | Uses labeled data: classification, regression |
| 2 | **Unsupervised** | Uses unlabeled data: clustering, dimensionality reduction |
| 3 | **Reinforcement Learning** | Agent maximizes reward via trial/error |

#### 1.3 **Inference Types**

| # | Type | Use Case |
|---|------|----------|
| 1 | **Real-time** | Low latency per request |
| 2 | **Batch** | High-throughput scoring on a schedule |

#### 1.4 **Data Types**

- **Structured** (tables) vs **Unstructured** (text/images/audio)
- Common formats: **Tabular**, **Time-series**, **Image**, **Text**
- Label status: **Labeled** vs **Unlabeled**

---

## 🧠 Domain 2 
### Fundamentals of Generative AI

#### 2.1 **Foundational GenAI Vocabulary**

| # | Concept | What It Means |
|---|---------|---------------|
| 1 | **Tokens** | Units the model reads/writes; cost + limits often token-based |
| 2 | **Context Window** | Max tokens model can consider at once (input + output) |
| 3 | **Chunking** | Splitting large text into smaller pieces (often for RAG) |
| 4 | **Embeddings** | Numeric representations of meaning |
| 5 | **Vectors** | Arrays of numbers (embeddings) used for similarity search |
| 6 | **Prompt Engineering** | Designing instructions/context/examples to steer outputs |
| 7 | **Transformers / LLMs** | Architecture powering many text models (attention-based) |
| 8 | **Foundation Models (FMs)** | Large general-purpose models adaptable to many tasks |
| 9 | **Multimodal Models** | Handle multiple modalities (e.g., text + image) |
| 10 | **Diffusion Models** | Commonly used for image generation |

#### 2.2 **Common GenAI Use Cases**

- Summarization
- Q&A Assistants
- Translation
- Code Generation
- Customer Service Agents
- Semantic Search
- Recommendations
- Image/Audio/Video Generation

#### 2.3 **FM Lifecycle**
**Data Selection → Model Selection → Pre-training → Fine-tuning → Evaluation → Deployment → Feedback**

---

## 🔧 Domain 3  
### Applications of Foundation Models

#### 3.1 **Model Selection Criteria**

| # | Factor | Why It Matters |
|---|--------|----------------|
| 1 | **Cost** | Often token-based pricing |
| 2 | **Latency** | Response time requirements |
| 3 | **Throughput** | Request volume capacity |
| 4 | **Model Size/Capability** | Balance between power and efficiency |
| 5 | **Multilingual** | Language support needs |
| 6 | **Modality** | Text, image, audio, multimodal |
| 7 | **Context Length** | Input/output token limits |
| 8 | **Customization Options** | Fine-tuning, prompting flexibility |
| 9 | **Constraints/Compliance** | Regulatory requirements |
| 10 | **Prompt Caching** | Efficiency for repeated prefixes |

#### 3.2 **Inference Parameters (Behavior Control)**

- **Temperature**: Higher = more random/creative, Lower = more consistent
- **Max Output Tokens**: Caps response length 
- Other sampling settings vary by provider

#### 3.3 **RAG (Retrieval Augmented Generation)**

| Aspect | Details |
|--------|---------|
| **Definition** | Retrieve relevant content from a knowledge store and provide it to the FM to generate grounded answers |
| **Why Use It** | Reduces hallucinations, keeps answers current, avoids retraining for new docs |
| **AWS Example** | Amazon Bedrock Knowledge Bases |

#### 3.4 **Vector Storage Options on AWS**

- **Amazon OpenSearch Service** (search + vector similarity)
- **Amazon Aurora**
- **Amazon RDS for PostgreSQL**
- **Amazon Neptune** (graph-driven retrieval patterns)
- **Amazon DocumentDB** (with MongoDB compatibility)

#### 3.5 **Customization Tradeoffs**

| Approach | Speed | Cost | Consistency | Best For |
|----------|-------|------|-------------|----------|
| **In-context learning (prompting/few-shot)** | ⚡ Fastest | 💰 More tokens | ⚠️ Variable | Quick iterations |
| **RAG** | ⚡ Fast | 💰💰 Retrieval + vectors | ✅ Good | Private/updating knowledge |
| **Fine-tuning** | ⏱️ Moderate | 💰💰💰 Training + maintenance | ✅✅ Best | Consistent behavior/style |
| **Pre-training** | ⏱️⏱️ Slowest | 💰💰💰💰 Extremely expensive | ✅✅ Custom | Rare/large orgs only |
| **Distillation** | ⚡ Fast (inference) | 💰💰 Training | ✅ Good | Reduce cost/latency |

#### 3.6 **Agents (Multi-Step Automation)**

- **Role**: LLM plans/executes multi-step tasks and calls tools/APIs
- **AWS Example**: Agents for Amazon Bedrock
- **Related Concepts**: Agentic AI, Model Context Protocol (MCP)

####  3.7 **Prompt Engineering**

#### **_1_** Techniques
- **Zero-shot:** no examples
- **One-shot** / **Few-shot:** with examples
- **Chain-of-thought:** step-by-step reasoning
- **Prompt Templates:** standardized with variables

#### **_2_** Key Constructs
- Instruction
- Context
- Negative prompts
- Prompt routing

#### _**3**_ Best Practices
1. Be specific and concise
2. Define output format (JSON/table)
3. Use examples when needed
4. Version and test prompts
5. Add guardrails in prompts

#### **_4_** Risks
- **Prompt Injection/Hijacking:** especially via retrieved docs in RAG
- **Jailbreaking**
- **Poisoning:** bad/malicious content in sources
- **Exposure/Leakage** system prompt or sensitive data

#### 3.8 **Evaluation Methods**

#### **_1_** Approaches
- Human evaluation
- Benchmark datasets
- **Amazon Bedrock Model Evaluation** (managed)

#### **_2_** Metrics
- **ROUGE**: Summarization
- **BLEU**: Translation
- **BERTScore**: Semantic similarity

#### **_3_** System-Level Evaluation
- **RAG**: Retrieval quality + grounded answer rate + citation accuracy
- **Agents/Workflows**: Task completion rate, tool-call correctness, cost/latency, safety

---

## ⚖️ Domain 4 
### Responsible AI

#### 4.1 **Responsible AI Features**

| Feature | What It Means |
|---------|---------------|
| **Bias** | Systematic unfairness |
| **Fairness** | Equitable outcomes across groups |
| **Inclusivity** | Works for diverse users |
| **Robustness** | Reliable under variability |
| **Safety** | Prevents harmful outputs |
| **Veracity** | Truthfulness and grounding |
| **Hallucination Awareness** | Understanding model limitations |

#### 4.2 **Dataset Characteristics for Responsibility**

- Diversity and inclusivity
- Curated sources
- Balanced representation
- High label quality
- Representativeness of real-world use

#### 4.3 **Bias/Variance Effects**
| Condition | Result | Impact |
|-----------|--------|--------|
| **High Bias** | Underfitting | Too simple; poor performance overall |
| **High Variance** | Overfitting | Too sensitive to training data; poor generalization |
| **Subgroup Impact** | Performance gaps | Different outcomes across demographic groups |

#### 4.4 AWS Tools for Responsible AI

| Tool | Purpose |
|------|---------|
| **Guardrails for Amazon Bedrock** | Policy/safety controls for GenAI |
| **Amazon SageMaker Clarify** | Bias detection + explainability |
| **Amazon SageMaker Model Monitor** | Monitor drift/data quality over time |
| **Amazon Augmented AI (A2I)** | Human review workflows |
| **SageMaker Model Cards** | Documentation for transparency |

### 4.5 Transparency & Explainability

- **Transparent**: Inherently understandable models (often simpler)
- **Explainable**: Complex models with explanations/documentation
- **Tradeoff**: Interpretability vs performance, transparency vs security

---

## 🔒 Domain 5 
### Security, Compliance, Governance

#### 5.1 **Core Security Building Blocks (AWS)**

| Component | Function |
|-----------|----------|
| **IAM** | Roles/policies/permissions (least privilege) |
| **Encryption** | At rest and in transit |
| **AWS PrivateLink** | Private connectivity to services |
| **Amazon Macie** | Discover sensitive data in S3 |
| **Shared Responsibility Model** | AWS secures cloud; you secure configs/data/apps |

#### 5.2 **AI-Specific Security/Privacy Concerns**

- Prompt injection
- Data leakage via prompts/logs
- Unsafe outputs
- Threat detection
- Vulnerability management
- Infrastructure protection

#### 5.3 **Governance Essentials**

- **Source Citation**: Document origins (trust + audit)
- **Data Lineage & Cataloging**: Track data flow and metadata
- **Data Governance Strategies**: Lifecycle, logging, residency, monitoring, retention

#### 5.4 **AWS Services for Audits/Governance**

| Service | Purpose |
|---------|---------|
| **AWS CloudTrail** | API audit logs |
| **AWS Config** | Configuration tracking/compliance rules |
| **AWS Audit Manager** | Collect evidence for audits |
| **AWS Artifact** | Download AWS compliance reports/agreements |
| **Amazon Inspector** | Vulnerability findings |
| **AWS Trusted Advisor** | Best-practice checks (security/cost) |

#### 5.5 **Governance Processes**

- Policies and review cadence
- Review strategies (human oversight, red-teaming)
- Transparency standards (model cards, disclosures, citations)
- Team training requirements
- **Framework Example**: Generative AI Security Scoping Matrix

---

## 💰 Pricing & Cost Concepts

| Factor | Impact |
|--------|--------|
| **Token-based Pricing** | Costs scale with input + output tokens |
| **Latency/Responsiveness** | Lower latency typically costs more |
| **Availability/Redundancy** | Multi-AZ/Region increases cost |
| **On-demand vs Provisioned Throughput** | Flexibility vs predictability tradeoff |
| **Customization Cost Ladder** | Prompting < RAG < Fine-tuning << Pre-training |

---

## 📝 Common Abbreviations

| Abbreviation | Full Term |
|--------------|-----------|
| **LLM** | Large Language Model |
| **FM** | Foundation Model |
| **GenAI** | Generative AI |
| **RAG** | Retrieval Augmented Generation |
| **NLP** | Natural Language Processing |
| **CV** | Computer Vision |
| **PII** | Personally Identifiable Information |
| **PHI** | Protected Health Information |
| **IAM** | Identity and Access Management |
| **VPC** | Virtual Private Cloud |
| **KMS** | Key Management Service |
| **TLS** | Transport Layer Security |
| **AUC** | Area Under the Curve |
| **F1** | F1 Score |
| **ROUGE** | Recall-Oriented Understudy for Gisting Evaluation |
| **BLEU** | Bilingual Evaluation Understudy |

---

## 🛠️ AWS AI/GenAI Service Quick Reference

| # | Service | Purpose |
|---|---------|---------|
| 1 | **Amazon Bedrock** | Use foundation models via API |
| 2 | **PartyRock** | Bedrock Playground for prototyping |
| 3 | **Agents for Amazon Bedrock** | Tool-using multi-step agents |
| 4 | **Bedrock Knowledge Bases** | Managed RAG building blocks |
| 5 | **Amazon Q** | GenAI assistant for work/dev/AWS contexts |
| 6 | **Amazon SageMaker** | Build/train/deploy ML; MLOps capabilities |
| 7 | **SageMaker JumpStart** | Pre-trained models/templates to start fast |
| 8 | **SageMaker Data Wrangler** | Data prep/EDA |
| 9 | **SageMaker Feature Store** | Consistent feature management |
| 10 | **SageMaker Model Monitor** | Production monitoring/drift |
| 11 | **Amazon Transcribe** | Speech-to-text |
| 12 | **Amazon Translate** | Language translation |
| 13 | **Amazon Comprehend** | Text analytics (entities, sentiment, etc.) |
| 14 | **Amazon Lex** | Chatbots/voice bots |
| 15 | **Amazon Polly** | Text-to-speech |

> ⚠️ **Important:** Always refer to the official exam guide for the most up-to-date list of in-scope and out-of-scope services.

---

## 📚 Additional Resources

1. [AWS Certified AI Practitioner (AIF-C01) Exam Guide (PDF)](https://d1.awsstatic.com/training-and-certification/docs-ai-practitioner/AWS-Certified-AI-Practitioner_Exam-Guide.pdf)
2. [AWS Certification: All Exam Guides (PDF)](https://docs.aws.amazon.com/pdfs/aws-certification/latest/examguides/aws-certification-exam-guides.pdf)
3. [Exam Guide: AI Practitioner Series Articles](https://dev.to/ntombizakhona/series/34979)

---

**Good luck with your exam! 🚀**



# The Original

**Blog:** [Ntombizakhona Mabaso](https://dev.to/ntombizakhona)
<br>
**Article Link:** [technologies & Concepts]()
<br>
Originally Published by [Ntombizakhona Mabaso](https://dev.to/ntombizakhona)
<br>
**27 January 2026**
