# VidPromptix

**VidPromptix** is a web application that allows users to interact with an **AI-powered chatbot** capable of answering questions based on YouTube video transcripts.  

The application uses **React** for the frontend, **Node.js with Express** for the backend, and integrates with **LangChain** and **Anthropic's Claude model** for natural language processing. It also leverages **Bright Data** for YouTube video scraping and a **vector store** for efficient transcript retrieval.

---

## 🚀 Features

- **Chat Interface**: Modern, responsive chat UI built with React and TypeScript.
- **YouTube Transcript Analysis**: Fetches and processes YouTube video transcripts to answer user queries.
- **AI-Powered Responses**: Uses Anthropic's Claude model via LangChain to generate accurate and context-aware answers.
- **Vector Store Integration**: Stores and retrieves transcript chunks using a PostgreSQL-based vector store for efficient similarity search.
- **Bright Data Integration**: Dynamically scrapes YouTube videos to fetch transcripts.

---

## 🛠️ Tech Stack

### Frontend
- **React** with **TypeScript**
- **Tailwind CSS** (via CDN)
- **Vite** for build and development

### Backend
- **Node.js** with **Express**
- **LangChain** for AI agent creation
- **Anthropic's Claude model** for NLP
- **PostgreSQL** with **PGVector** for vector storage
- **OpenAI Embeddings** for text embedding
- **Bright Data API** for YouTube scraping

### Deployment
- **Genezio** for deploying backend and frontend
- **Environment variables** for configuration

---

## ✅ Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v18 or higher)
- **npm** (v9 or higher)
- **PostgreSQL** (with PGVector extension)
- **Genezio CLI**  
  ```bash
  npm install -g genezio
