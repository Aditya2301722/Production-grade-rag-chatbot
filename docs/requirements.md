# Requirements: Production-Grade RAG + CAG Customer Support Chatbot

## Project Overview
This project aims to build a production-grade AI customer support chatbot capable of answering customer queries in German and English, using RAG (Retrieval-Augmented Generation) and CAG (Cache-Augmented Generation). The system retrieves information from a knowledge base (FAQs, guides, policy docs) and provides accurate, grounded answers with sources. It also supports session memory, structured responses, and multilingual output.

## Project Goals
- Automate 60–80% of common customer support queries.
- Support German and English automatically.
- Provide accurate, evidence-based responses.
- Reduce human agent workload and improve response time.
- Enable safe demo access for recruiters or stakeholders.
- Showcase end-to-end skills (LLM, backend, frontend, MLOps, architecture).

## Target Users
Primary: External customers (orders, shipping, refunds, product info).
Secondary: Support agents (suggested replies), recruiters, stakeholders.

## Functional Requirements
1. Authentication
   - Email OTP OR Order number OR recruiter code required.
   - Prevent anonymous use.

2. Multilingual Support
   - Detect user language (DE/EN) automatically and respond in same language.

3. Chatbot Core
   - Accept queries via frontend; use session memory (CAG) + retrieval (RAG).
   - Ground answers on retrieved sources; show citations.
   - Handle follow-ups and maintain context.

4. Knowledge Base
   - FAQs, manuals, order/shipping data, returns, troubleshooting guides.

5. Retrieval & Embeddings
   - Chunk documents, generate embeddings, store in vector DB, top-k retrieval.

6. Session Management
   - Redis for session history, summaries, and query/result caches.

7. Safety & Guardrails
   - PII detection & redaction, hallucination prevention,
   - Escalation when uncertain; rate-limiting and logging.

8. Observability
   - Latency, token usage/cost, cache hit rate, retrieval accuracy, error rate, language distribution.

9. Frontend Features
   - Login, chat UI, response sources, session history, loading & error states.

## Non-Functional Requirements
- Performance: p95 < 2s (response)
- Reliability: graceful fallback; robust logging
- Security: HTTPS, key protection, OTP auth, rate-limits
- Scalability: horizontal backend, scalable vector DB
- Maintainability: clean structure, docs, CI/CD

## Assumptions & Constraints
- Use synthetic/anonymized data for public demo.
- MVP uses a mock order-lookup API.
- API budget is limited; implement caching & quotas.
