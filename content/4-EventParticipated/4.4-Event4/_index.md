---
title: "Event 4"
date: 2025-09-10
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# “AI/ML/GenAI on AWS” Report

### Event Purpose

- Provide an overview of Foundation Models and the Amazon Bedrock platform
- Guide on Prompt Engineering techniques from basic to advanced
- Explain the architecture and operational workflow of RAG (Retrieval Augmented Generation)
- Introduce AWS's ecosystem of Pretrained AI services and Frameworks for building AI Agents

### Speaker List

- **Lam Tuan Kiet**
- **Danh Hoanh Hieu Nghi**
- **Dinh Le Hoang Anh**

### Highlights

#### Foundation Models & Amazon Bedrock

- **Foundation Models (FMs)**: Trained using self-supervised training, capable of processing many tasks.
- **Amazon Bedrock**: Platform providing access to leading models like Luma, Deepseek...

#### Prompt Engineering (AI Command Techniques)

Basic process: Prompt → Bedrock → Response. Key techniques:
- **Zero-Shot Prompting**: Asking questions directly without providing sample data.
- **Few-Shot Prompting**: Providing a few examples (example frame) for the model to learn the answer structure when encountering similar questions.
- **Chain of Thought (CoT)**: Guiding AI on step-by-step reasoning, helping AI provide more accurate answers based on learned logic.

#### Retrieval Augmented Generation (RAG)

Currently popular model (used widely in Banking). Process includes: **Retrieval → Augmentation → Generation**.
- **Embeddings**: Convert human language into Vectors. Using Amazon Titan Embedding (supports multiple languages).
- **RAG in Action**:
    1. **Data preparation**: Data source → Document chunk → Embeddings model → Vector store.
    2. **Query processing**: User input → Embeddings model → Vector → Semantic search (in Vector store) → Context → Prompt augmentation → LLM → Response.

#### Other Pretrained AI Services

AWS provides specialized services with optimal costs:
- **Amazon Rekognition** (Computer Vision): Image/video analysis, face and object detection. Pricing: ~$0.0013/image.
- **Amazon Translate**: Real-time or batch text translation. Pricing: ~$15/million characters.
- **Amazon Textract**: Extract text and layout from documents (OCR). Pricing: ~$0.05/page.
- **Amazon Transcribe**: Convert speech to text, supports streaming.
- **Amazon Polly**: Convert text to speech, supports Real-time TTS. Pricing: ~$4/million characters.
- **Amazon Comprehend** (NLP): Sentiment Analysis, key phrase extraction, PII detection. Pricing: ~$0.0001/100 chars.
- **Amazon Kendra**: Intelligent Search service, supports Natural Language Search and RAG.
- **Amazon Lookout Family**: Detect anomalies in Metrics, Equipment, and Vision.
- **Amazon Personalize**: Personalized recommendation system for users.

#### AI Agents & Frameworks

- **Pipecat**: Framework for voice/multimodal AI agents, optimized for real-time conversation assistants.
- **Amazon Bedrock AgentCore**:
    - Supported frameworks: Langgraph, Langchain, Strands Agents SDK.
    - Process from Idea → Production needs to focus on: Performance, Scalability, Security, Governance.
    - Core components: Runtime, Memory, Identity, Gateway, Code Interpreter, Browser tool, Observability.

### What I Learned

#### Prompting Mindset

- **Optimization Techniques**: Clearly understand the differences between Zero-shot, Few-shot, and Chain of Thought to apply to specific problem complexities.
- **Structuring**: Providing examples helps better control the model's output format.

#### RAG Architecture

- **Vector Database**: Understand the critical role of Vector Store and Semantic Search in providing accurate context for LLMs.
- **Embedding Models**: The importance of choosing embedding models (like Amazon Titan) to support multiple languages and search accuracy.

#### Service Selection (Trade-offs)

- **Cost vs Flexibility**: Know how to balance costs between using Pretrained Services (pay per request/char) versus building custom models or using general LLMs.
- **Use case specific**: Each service (Rekognition, Textract...) solves a specific problem better and cheaper than forcing an LLM to do everything.

### Application to Work

- **Deploy RAG**: Apply Retrieval Augmented Generation model to build internal search systems for enterprise/banking.
- **Integrate Pretrained Services**: Use Amazon Textract and Comprehend to automate document and record processing.
- **Build intelligent Chatbots**: Combine Amazon Lex/Bedrock with Pipecat framework to create real-time conversational virtual assistants.
- **Cost Optimization**: Use Caching for Amazon Polly or select the right tier of AI services to minimize operating costs.

### Event Experience

Participating in the **“Generative AI with Amazon Bedrock”** event helped me systematize knowledge about GenAI and the AWS ecosystem. Some highlights:

#### Practical Knowledge from Experts

- Speakers shared real-world experiences on applying RAG and Prompt Engineering.
- Deeper understanding of the AI **reasoning process** through Chain of Thought.

#### Overview of AI Services

- Not stopping at LLMs, the event provided a broad view of Specialized AI Services like Lookout, Kendra, Personalize... helping solve niche problems effectively.
- The Pricing analysis gave me more data to make decisions when designing solutions.

#### Tech Trend Updates

- Introduced to **Agentic AI** and components of Bedrock AgentCore, opening new directions in building AI applications capable of executing complex tasks (Idea to Production).
- Approached **Pipecat framework**, an optimal solution for voice AI agents.

  > In conclusion, the event provided a solid knowledge foundation about Amazon Bedrock and GenAI techniques, thereby helping me feel more confident in proposing and implementing AI solutions for projects.