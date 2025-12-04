# AI WhatsApp Support Agent (n8n Workflow)

This repository contains an automated **AI-powered WhatsApp Support Agent** built using **n8n**, **Google Gemini**, **Supabase Vector Store**, **Postgres Chat Memory**, and **Google Sheets**.

The system receives WhatsApp messages, retrieves relevant product/FAQ info from a vector database, and responds intelligently using an LLM — with fallback safety responses.

---

## 🚀 Features

- **WhatsApp Automation**  
  Incoming messages are captured using `WhatsApp Trigger` node.

- **AI Agent with System Prompt**  
  Uses `LangChain Agent` with a structured system message to keep replies concise and relevant.

- **RAG (Retrieval-Augmented Generation)**  
  Supabase Vector Store fetches matching content from:
  - Google Sheets product info  
  - FAQ entries  
  - Custom documents  
  (Workflow parsed and vectorized automatically)  

- **Multiple Embedding Models**
  - Google Gemini Embeddings  
  - OpenAI Embeddings  

- **Chat Memory**
  Uses Postgres-backed session memory to maintain conversation context per user.

- **Data Preprocessing**
  Dynamic JS Code node converts rows into clean, vector-ready documents.

---

## 📁 Files

- **AI Agent workflow.json** — Full n8n workflow  
  (Imported from your original source)  
  :contentReference[oaicite:1]{index=1}

---

## 🛠️ Tech Stack

- **n8n** (workflow engine)  
- **Google Gemini** (LLM + embeddings)  
- **Supabase** (vector storage)  
- **Postgres** (memory store)  
- **Google Sheets API** (data source)  
- **WhatsApp Cloud API**

---

## ▶️ How It Works (Flow Summary)

1. **User sends a WhatsApp message** → Trigger fires  
2. AI Agent reads user query  
3. Vector Store retrieves FAQ/Product data  
4. AI generates a short, helpful answer  
5. If no answer found → `"one of our team member will assist you on this"`  
6. Message is sent back instantly on WhatsApp

---

## 📦 Importing Into n8n

1. Download the JSON file  
2. Open n8n  
3. Go to **Workflows → Import from File**  
4. Upload `AI Agent workflow.json`  
5. Add credentials for:
   - WhatsApp
   - Google Gemini / Google Sheets
   - Supabase
   - Postgres

---

## 📄 License

MIT License
