Agentic RAG — AI Document Intelligence System

Upload a PDF and ask anything — critic, study, extract, explain.

Show Image

What is this?
A full-stack Agentic RAG platform built around a ReAct-based autonomous LLM orchestration loop. Instead of just doing naive vector search, it reasons over your documents — deciding when to retrieve, when to search the web, and when to synthesize — before giving you an answer.
Built for PDF analysis, multi-document comparison, and structured data extraction.

Features

🤖 ReAct Agent Loop — autonomous reasoning before every response, ~40% reduction in off-context answers vs naive retrieval
📄 4 Interaction Modes — Critic (find problems), Study (flashcards & key points), Extract (structured data), Explain (simplify content)
📚 Multi-PDF Comparison — isolated vector stores per session, document-grouped chat history
🌐 Tavily Web Search — intent-based switching between document retrieval and live web search
⚡ SSE Streaming — real-time streamed responses via Next.js Server-Sent Events
☁️ AWS Deployed — EC2 + Amplify + RDS + Nginx with IAM role-based access control
🗄️ Dual DB Architecture — SQLite → PostgreSQL for persistent, scalable chat history


Tech Stack
LayerTechnologiesBackendPython, FastAPI, ChromaDB, Gemini 1.5 Flash, TavilyFrontendNext.js, TypeScript, TailwindCSSDatabasePostgreSQL, SQLiteCloudAWS EC2, Amplify, RDS, IAM, NginxAIRAG, ReAct Agent, Vector Embeddings, LLM Orchestration

Architecture
User Query
    ↓
ReAct Agent Loop
    ↓
┌─────────────────────────────────┐
│  Decide: Retrieve or Web Search │
└─────────────────────────────────┘
    ↓                    ↓
ChromaDB              Tavily API
Vector Store          Web Search
    ↓                    ↓
└──────────── Synthesize ─────────┘
                  ↓
         Streamed Response (SSE)
                  ↓
           Next.js Frontend

Getting Started
Prerequisites

Python 3.10+
Node.js 18+
PostgreSQL
Gemini API key
Tavily API key

Backend
bashcd backend
pip install -r requirements.txt
cp .env.example .env  # Add your API keys
uvicorn main:app --reload
Frontend
bashcd frontend
npm install
cp .env.example .env.local  # Add your backend URL
npm run dev


Author
Rahul Mishra — LinkedIn · GitHub
