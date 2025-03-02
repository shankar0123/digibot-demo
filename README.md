# digibot-demo

# RAG Chatbot for SOC Analysts

## Overview

This project introduces a **Retrieval-Augmented Generation (RAG) chatbot** designed specifically for **Security Operations Center (SOC) analysts**. The chatbot allows analysts to **query documentation** like Customer-Facing Service Guides, runbooks, and other operational manuals using natural language, eliminating the need for manual searches and significantly improving response times.

This repo demonstrates the steps for setting up an LLM locally on your machine, however, it does not go into the steps of RAG implementation.

### Why This Matters

SOC analysts often spend **valuable time manually searching** through documents for critical information. This chatbot **accelerates access** to relevant content, improving incident response efficiency.

Additionally, a key concern with AI in security operations is **data privacy**. Many AI solutions rely on cloud-hosted models, which can pose security risks. **This RAG chatbot runs entirely locally**, ensuring:

- **No API calls** – All queries are processed in-memory.
- **No external dependencies** – The model runs completely on your local machine.
- **Full control** over security and compliance.

---

## Deployment Options

This solution can be deployed in multiple ways:
1. **Locally on an analyst’s machine** – This demo is using this solution, ensuring complete data isolation.
2. **Hosted in a private cloud environment** – Providing centralized access while maintaining security.
3. **Using third-party RAG-as-a-Service solutions** – Though external providers claim not to train on customer data, an in-house solution ensures full control and security.

---

## Setup Instructions

### Step 1: Install Dependencies

1. **Install Docker** → [Download Docker](https://www.docker.com/)
2. **Install Ollama** → [Download Ollama](https://ollama.com/download)
3. **Pull an LLM Model** from the [Ollama Library](https://ollama.com/library)

   Example:
   ```bash
   ollama run llama3.2:1b
   ```

### Step 2: Install OpenWebUI

1. **Pull OpenWebUI Docker Image**
   ```bash
   docker pull ghcr.io/open-webui/open-webui:main
   ```
2. **Run OpenWebUI**
   ```bash
   docker run -d -p 3000:8080 -v open-webui:/app/backend/data --name open-webui ghcr.io/open-webui/open-webui:main
   ```
3. **Access OpenWebUI**
   - Open a browser and go to → [http://localhost:3000](http://localhost:3000)

---

## Demo Walkthrough

Once everything is set up, you can:
1. Load the chatbot interface via OpenWebUI.
2. Enter queries related to your **Customer-Facing Service Guide**.
3. See real-time responses retrieved from your documents using the locally running model.

### Key Features
- **Runs 100% locally** – No external API calls, ensuring security.
- **Fast document retrieval** – Uses a RAG pipeline to fetch relevant information instantly.
- **Flexible deployment** – Can run locally or in a private cloud.

---

## Why This Matters for SOC Teams

1. **Faster Decision-Making** – Analysts can quickly find critical information without sifting through documents.
2. **Better Response Times** – Reducing time spent on documentation lookup enhances incident resolution speed.
3. **Complete Data Sovereignty** – Since everything runs locally, there are **no concerns about proprietary data being leaked**.

---

## Conclusion

This **RAG-powered chatbot** is a game-changer for SOC teams, ensuring **quick, secure, and efficient access to crucial operational documents**. Whether running locally or hosted in a controlled environment, this solution guarantees **total privacy** and **full control** over data.
