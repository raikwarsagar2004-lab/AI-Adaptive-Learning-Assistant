# System Architecture

## Responsibilities
- Orchestrate ingestion, retrieval, adaptive assessment, recommendation, and analytics.
- Provide secure APIs for user/session management and content operations.

## Modules
- User System: Authentication, profiles, learning history.
- Document Upload: Ingestion, chunking, embedding, indexing.
- AI Knowledge Assistant: Semantic search, QA, summarization.
- Adaptive Quiz Engine: Dynamic difficulty, generation, RL-based selection.
- Recommendation Engine: Study plan creation from mastery gaps.
- Analytics System: Progress tracking, skill estimation visualization.

## Logical Architecture (Textual Diagram)
- Frontend (React) ↔ Backend (FastAPI)
- Backend ↔ MongoDB (data) and FAISS (vectors)
- Backend ↔ LLM (GPT-4) and ML (PyTorch)
- Optional Voice services: Whisper (STT), ElevenLabs (TTS)

## Data Flow
- Ingestion: PDF → extract → chunk → embed → FAISS + MongoDB metadata.
- Query: Question → retrieve vectors → rerank → prompt LLM → grounded answer.
- Quiz: User starts → engine selects item → record attempt → update mastery.
- Recommendation: Aggregate mastery → generate plan → expose via API.
- Analytics: Events → aggregates → dashboard queries.

## Interfaces
- REST APIs (JSON) with OAuth/JWT auth.
- WebSocket for real-time tutor/quiz updates (optional).
- S3-compatible blob storage (optional) for large files.

## Scaling
- Stateless API workers behind load balancer.
- Vector index partitioning and replication.
- Background workers for embedding and analytics pipeline (task queue).
- CDN for frontend assets; caching for frequent queries.
