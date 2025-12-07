---
title: "Event 4"
date: 2025-09-10
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Bài thu hoạch “AI/ML/GenAI on AWS”

### Mục Đích Của Sự Kiện

- Giới thiệu tổng quan về Foundation Models và nền tảng Amazon Bedrock
- Hướng dẫn các kỹ thuật Prompt Engineering từ cơ bản đến nâng cao
- Giải thích kiến trúc và quy trình hoạt động của RAG (Retrieval Augmented Generation)
- Giới thiệu hệ sinh thái các dịch vụ Pretrained AI của AWS và các Framework xây dựng AI Agents

### Danh Sách Diễn Giả

- **Lam Tuan Kiet**
- **Danh Hoanh Hieu Nghi**
- **Dinh Le Hoang Anh**

### Nội Dung Nổi Bật

#### Foundation Models & Amazon Bedrock

- **Foundation Models (FMs)**: Được huấn luyện theo phương pháp self-supervisor training, có khả năng xử lý đa nhiệm (many tasks).
- **Amazon Bedrock**: Nền tảng cung cấp quyền truy cập vào các mô hình hàng đầu như Luma, Deepseek...

#### Prompt Engineering (Kỹ thuật ra lệnh cho AI)

Quy trình cơ bản: Prompt → Bedrock → Response. Các kỹ thuật chính:
- **Zero-Shot Prompting**: Đặt câu hỏi trực tiếp mà không cần cung cấp dữ liệu mẫu.
- **Few-Shot Prompting**: Cung cấp một vài ví dụ (example frame) để mô hình học theo cấu trúc câu trả lời khi gặp câu hỏi tương tự.
- **Chain of Thought (CoT)**: Hướng dẫn AI cách suy luận từng bước (step-by-step reasoning), giúp AI đưa ra câu trả lời chính xác hơn dựa trên logic đã học.

#### Retrieval Augmented Generation (RAG)

Mô hình phổ biến hiện nay (dùng nhiều trong Banking). Quy trình gồm: **Retrieval → Augmentation → Generation**.
- **Embeddings**: Chuyển đổi ngôn ngữ con người thành Vector. Sử dụng Amazon Titan Embedding (hỗ trợ đa ngôn ngữ).
- **RAG in Action**:
    1. **Chuẩn bị dữ liệu**: Data source → Document chunk → Embeddings model → Vector store.
    2. **Xử lý truy vấn**: User input → Embeddings model → Vector → Semantic search (trong Vector store) → Context → Prompt augmentation → LLM → Response.

#### Các Dịch Vụ Pretrained AI Khác

AWS cung cấp các dịch vụ chuyên biệt với chi phí tối ưu:
- **Amazon Rekognition** (Computer Vision): Phân tích hình ảnh/video, nhận diện khuôn mặt, vật thể. Pricing: ~$0.0013/image.
- **Amazon Translate**: Dịch thuật văn bản thời gian thực hoặc theo lô (batch). Pricing: ~$15/million characters.
- **Amazon Textract**: Trích xuất văn bản và layout từ tài liệu (OCR). Pricing: ~$0.05/page.
- **Amazon Transcribe**: Chuyển đổi giọng nói thành văn bản (Speech-to-text), hỗ trợ streaming.
- **Amazon Polly**: Chuyển đổi văn bản thành giọng nói (Text-to-Speech), hỗ trợ Real-time TTS. Pricing: ~$4/million characters.
- **Amazon Comprehend** (NLP): Phân tích cảm xúc (Sentiment Analysis), trích xuất key phrase, phát hiện thông tin cá nhân (PII). Pricing: ~$0.0001/100 chars.
- **Amazon Kendra**: Dịch vụ tìm kiếm thông minh (Intelligent Search), hỗ trợ Natural Language Search và RAG.
- **Amazon Lookout Family**: Phát hiện bất thường (Anomalies) trong Metrics, Equipment (thiết bị) và Vision (hình ảnh).
- **Amazon Personalize**: Hệ thống gợi ý (Recommendation) cá nhân hóa cho người dùng.

#### AI Agents & Frameworks

- **Pipecat**: Framework cho voice/multimodal AI agents, tối ưu cho hội thoại thời gian thực (real-time conversation assistant).
- **Amazon Bedrock AgentCore**:
    - Frameworks hỗ trợ: Langgraph, Langchain, Strands Agents SDK.
    - Quy trình từ Idea → Production cần chú trọng: Performance, Scalability, Security, Governance.
    - Các thành phần cốt lõi: Runtime, Memory, Identity, Gateway, Code Interpreter, Browser tool, Observability.

### Những Gì Học Được

#### Tư Duy Prompting

- **Kỹ thuật tối ưu**: Hiểu rõ sự khác biệt giữa Zero-shot, Few-shot và Chain of Thought để áp dụng cho từng độ phức tạp của bài toán.
- **Cấu trúc hóa**: Việc cung cấp ví dụ (examples) giúp kiểm soát định dạng đầu ra của mô hình tốt hơn.

#### Kiến Trúc RAG

- **Vector Database**: Hiểu vai trò quan trọng của Vector Store và Semantic Search trong việc cung cấp ngữ cảnh (context) chính xác cho LLM.
- **Embedding Models**: Tầm quan trọng của việc chọn model embedding (như Amazon Titan) để hỗ trợ đa ngôn ngữ và độ chính xác khi tìm kiếm.

#### Lựa Chọn Dịch Vụ (Trade-offs)

- **Cost vs Flexibility**: Biết cách cân nhắc chi phí giữa việc dùng các Pretrained Services (tính tiền theo request/char) so với việc tự build model hoặc dùng LLM tổng quát.
- **Use case specific**: Mỗi dịch vụ (Rekognition, Textract...) giải quyết một bài toán cụ thể tốt hơn và rẻ hơn so với việc ép LLM làm tất cả.

### Ứng Dụng Vào Công Việc

- **Triển khai RAG**: Áp dụng mô hình Retrieval Augmented Generation để xây dựng hệ thống search nội bộ cho doanh nghiệp/ngân hàng.
- **Tích hợp Pretrained Services**: Sử dụng Amazon Textract và Comprehend để tự động hóa quy trình xử lý hồ sơ, giấy tờ.
- **Xây dựng Chatbot thông minh**: Kết hợp Amazon Lex/Bedrock với Pipecat framework để tạo trợ lý ảo hội thoại thời gian thực.
- **Tối ưu hóa chi phí**: Sử dụng Caching cho Amazon Polly hoặc chọn đúng tier của các dịch vụ AI để giảm thiểu chi phí vận hành.

### Trải nghiệm trong event

Tham gia sự kiện **“Generative AI with Amazon Bedrock”** giúp mình hệ thống hóa lại các kiến thức về GenAI và hệ sinh thái AWS. Một số điểm nhấn:

#### Kiến thức thực tiễn từ chuyên gia

- Các diễn giả đã chia sẻ những kinh nghiệm thực tế (Real-world examples) về việc áp dụng RAG và Prompt Engineering.
- Hiểu sâu hơn về **quy trình suy luận (reasoning)** của AI thông qua Chain of Thought.

#### Bức tranh toàn cảnh về AI Services

- Không chỉ dừng lại ở LLM, sự kiện cung cấp cái nhìn rộng về các dịch vụ AI chuyên biệt (Specialized AI Services) như Lookout, Kendra, Personalize... giúp giải quyết các bài toán ngách hiệu quả.
- Sự phân tích về giá (Pricing) giúp mình có thêm dữ liệu để ra quyết định khi thiết kế giải pháp.

#### Cập nhật xu hướng công nghệ

- Được giới thiệu về **Agentic AI** và các thành phần của Bedrock AgentCore, mở ra hướng đi mới trong việc xây dựng các ứng dụng AI có khả năng thực thi tác vụ phức tạp (Idea to Production).
- Tiếp cận với **Pipecat framework**, giải pháp tối ưu cho voice AI agents.

  > Tổng kết lại, sự kiện đã cung cấp một nền tảng kiến thức vững chắc về Amazon Bedrock và các kỹ thuật GenAI, từ đó giúp mình tự tin hơn trong việc đề xuất và triển khai các giải pháp AI cho dự án.