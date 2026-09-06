# Multilingual RAG System

Engineered a cross-lingual Retrieval-Augmented Generation pipeline capable of semantic retrieval and response generation across language boundaries — decoupling information retrieval from source-document language.

## Architecture

 **Ingestion Layer** — Unified preprocessing pipeline handling heterogeneous, multi-language document corpora without language-specific branching logic

 **Cross-Lingual Vectorization Layer** — Dense embedding generation via Google Gemini's multilingual embedding model, projecting semantically equivalent text across languages into a shared high-dimensional vector space — independent of surface-level lexical differences

 **Retrieval Layer** — Similarity-based semantic search operating natively in cross-lingual vector space, enabling accurate retrieval regardless of query-document language mismatch

 **Response Governance Layer** — Deterministic language-matching logic enforced at the system-prompt level, ensuring output language defaults to query language while supporting explicit language-override instructions

## Tech Stack
`n8n` (self-hosted orchestration) | `Google Gemini` (multilingual embeddings + generation) | `Vector Store` | `Agentic AI Workflows`

## Core Engineering Challenge

The primary challenge was not retrieval accuracy — Gemini's multilingual embedding space handles cross-lingual similarity natively — but **response-language governance**. Without explicit constraints, the agent defaulted to mirroring the retrieved source document's language rather than the query language, producing an inconsistent user experience in mixed-language corpora.

This was resolved by embedding a deterministic language-matching directive into the agent's system prompt, with a secondary override clause for explicit language requests — decoupling *retrieval language* from *generation language* as independent, controllable dimensions of the pipeline.

## Demonstrated Capability
- Cross-lingual semantic retrieval (e.g., English query → Urdu-language source → accurate retrieval)
- Query-language-matched response generation by default
- Explicit language-override support via natural language instruction
- Single embedding model serving multiple languages — no per-language infrastructure required

#AI #RAG #Multilingual #CrossLingualNLP #n8n #AgenticAI #AIEngineering
