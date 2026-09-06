# Contract Risk Intelligence Engine

Engineered an autonomous risk-assessment pipeline that transforms unstructured legal/contractual text into a structured, quantified risk profile — combining semantic retrieval with agentic reasoning to surface asymmetric or high-exposure clauses without human legal review.

## Architecture

 **Ingestion Layer** — Multi-format document preprocessing supporting mixed-language contractual text, feeding into a unified chunking pipeline

 **Vectorization Layer** — Dense embedding generation via Google Gemini's embedding model, projecting clause-level semantics into a shared vector space independent of document structure or drafting style

 **Retrieval Layer** — Category-targeted semantic search across a predefined risk taxonomy (termination, payment terms, auto-renewal, liability, confidentiality, dispute resolution, data ownership), enabling precision retrieval of clause-relevant context per risk category rather than generic top-K retrieval

 **Agentic Risk Reasoning Layer** — LLM-driven evaluation layer that reasons over retrieved clauses against an asymmetry heuristic — assessing not just clause presence but *directional imbalance* (e.g., disparate notice periods, one-sided cost allocation) — and classifies findings into a three-tier severity taxonomy (High / Medium / Low) with natural-language justification

 **Completeness Governance Layer** — A deterministic constraint enforced at the system-prompt level requiring exhaustive coverage across all risk categories prior to summary finalization, preventing silent omission of unassessed clause types

## Tech Stack
`n8n` (self-hosted orchestration) | `Google Gemini` (embeddings + agentic reasoning) | `Vector Store` | `Agentic AI Workflows`

## Core Engineering Challenges

**1. Retrieval-Ingestion State Ambiguity**
The agent intermittently prompted users to "upload" a contract despite the document already being indexed — a symptom of the agent lacking explicit awareness of pipeline state. Resolved by injecting an explicit state assertion into the system prompt, decoupling *ingestion status* from *conversational turn context*.

**2. Inconsistent Category Coverage**
Risk summaries exhibited non-deterministic omission of clause categories across otherwise-identical queries — a reliability gap stemming from unconstrained agentic exploration during retrieval. Resolved by enforcing a mandatory category-completeness checklist at the reasoning layer, converting an implicit expectation (exhaustive analysis) into an explicit, verifiable constraint — reinforcing that agentic reliability is frequently bottlenecked by prompt-level determinism rather than retrieval quality.

## Demonstrated Capability

**Input:** Vendor service agreement (mixed clause complexity)
**Query:** "Give me a summary report with a risk score out of 10"
**Output:** Quantified risk score (8/10) with itemized, category-tagged breakdown — each finding accompanied by a plain-language asymmetry rationale (e.g., 3-day vendor termination notice vs. 90-day client notice + 6-month penalty)

## Key Capabilities
- Category-targeted clause retrieval across a defined legal risk taxonomy
- Asymmetry-aware risk classification (High/Medium/Low) with justification
- Quantified overall risk scoring with supporting rationale
- Enforced exhaustive category coverage (no silent omissions)
- Multilingual query/response parity (inherited cross-lingual embedding architecture)

## Files
- `workflow.json` — Exported n8n workflow
- `screenshot.png` — Risk analysis output demo

---
#AI #RAG #AgenticAI #LegalTech #n8n #RiskIntelligence #AIEngineering #LLMOps
