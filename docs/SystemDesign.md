User (Browser)
     |
     | HTTP Requests
     v
Frontend (Vercel)
 ├── index.html      (onboarding form)
 ├── dashboard.html  (learning roadmap view)
 └── chat.html       (RAG chat interface)
     |
     | REST API Calls
     v
Backend (FastAPI on Render)
 ├── /api/plan
 │     └── Claude generates personalized roadmap
 │
 └── /api/chat
       ├── Generate query embedding
       │      ↓
       │   Gemini Embedding API
       │
       ├── Similarity Search
       │      ↓
       │   Supabase pgvector
       │
       └── Claude API
              ↓
         Context-Aware Response
     |
     v
Supabase
 └── documents table
      ├── content
      ├── metadata
      └── embedding vector