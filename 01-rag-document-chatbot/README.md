# RAG Document Chatbot

Designed and deployed an autonomous RAG (Retrieval-Augmented Generation) pipeline — turning unstructured documents into a queryable, context-aware knowledge system.

## Architecture

🔹 **Ingestion Layer** — automated document extraction and preprocessing

🔹 **Chunking Layer** — recursive text splitting to preserve semantic context across segments

🔹 **Vectorization Layer** — dense embedding generation via Google Gemini, mapping text into high-dimensional vector space

🔹 **Retrieval Layer** — similarity-based semantic search over a vector store for precise, context-aware document retrieval

🔹 **Generation Layer** — agentic LLM orchestration (Gemini) with autonomous tool-calling, where the model independently decides when to query the knowledge base vs. respond natively

## Tech Stack
`n8n` (self-hosted orchestration) | `Google Gemini` (embeddings + generation) | `Vector Store` | `Agentic AI Workflows`

## Files
- `workflow.json` — Exported n8n workflow
- `screenshot.png` — Workflow demo

---
#AI #RAG #Automation #n8n #AgenticAI #MachineLearning #AIEngineering
