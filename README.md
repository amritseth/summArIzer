<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:161b22,100:0d1117&height=200&section=header&text=AI%20Summarizer%20Pro&fontSize=50&fontColor=58a6ff&animation=fadeIn" width="100%"/>
</div>

<div align="center">
  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
</div>

<br/>

## 🚀 Project Overview
**AI Summarizer Pro** is a full-stack, serverless application built on AWS that leverages Large Language Models (LLMs) to transform long-form content into concise, actionable summaries. It supports raw text, URLs, and PDF documents (including scanned files via OCR).

### ✨ Key Features
* **Multi-Source Input:** Summarize text, web articles (via URL), or uploaded PDFs.
* **OCR Support:** Integrated Amazon Textract for processing scanned or image-based PDFs.
* **Audio Synthesis:** Converts the summary into an MP3 file using Amazon Polly.
* **Keyword Extraction:** Uses Amazon Comprehend to identify top 10 key phrases and entities.
* **Secure Uploads:** Utilizes S3 Pre-signed URLs for direct, secure client-to-S3 uploads.
* **History Tracking:** All summaries are indexed and stored in DynamoDB.

---

## 🏗️ Architecture
The project follows a modern **Serverless First** architecture, ensuring high scalability and cost-efficiency.



| Service | Role |
| :--- | :--- |
| **AWS SAM** | Infrastructure as Code (IaC) & Deployment |
| **Amazon API Gateway** | RESTful API Endpoints (/summarize, /generate-upload-url) |
| **AWS Lambda** | Python-based compute for orchestration & text processing |
| **Amazon S3** | Storage for document uploads and generated MP3 summaries |
| **Amazon SageMaker** | Hosting the LLM (T5/BART) for summarization |
| **Amazon Comprehend** | Natural Language Processing for keyword extraction |
| **Amazon Polly** | Neural Text-to-Speech (TTS) for audio playback |
| **Amazon DynamoDB** | NoSQL database for summary metadata and history |

---

## 🛠️ Tech Stack
* **Backend:** Python 3.11, Boto3, PyPDF2, Newspaper3k
* **Frontend:** React.js, Vite, CSS3 (Modern Flex/Grid)
* **DevOps:** AWS SAM CLI, Docker (Containerized Builds), CloudFormation

---

## ⚙️ Installation & Deployment

### 1. Prerequisites
* AWS CLI & SAM CLI installed and configured.
* Docker Desktop running (for building Lambda layers).
* An active SageMaker Endpoint or Bedrock Model Access.

### 2. Backend Deployment
```bash
# Navigate to project root
cd summarizer-project

# Build with Docker to handle Linux-specific dependencies
sam build --use-container

# Deploy to AWS
sam deploy --guided
