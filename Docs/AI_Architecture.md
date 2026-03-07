# AI Architecture

## Components
- Embedding Pipeline: Text chunking, vectorization.
- RAG Retrieval: FAISS similarity, reranking, contextual assembly.
- Generation: GPT-4 prompts with retrieved context; citation and source tracking.
- Adaptive Models: BKT for topic mastery; RL/bandit for question selection.
- Summarization: Map-reduce summarization of document sections.

## Input/Output
- Inputs: Document text, user questions, quiz attempts, timing data.
- Outputs: Answers with citations, summaries, selected quiz items, mastery scores, recommendations.

## Model Stack
- Embeddings: OpenAI or local transformer embeddings via LangChain.
- Generator: GPT-4 for QA and summarization.
- Skill Estimation: BKT parameters per skill; ML regression/classification for difficulty prediction.
- RL: Contextual bandit for item selection balancing exploration/exploitation.

## Prompting Strategies
- Grounded QA: Provide top-N chunks with metadata; require citations.
- Summarization: Section-aware prompts; concise learning objectives.
- Quiz Generation: Topic, difficulty constraints; avoidance of duplication; STEM-friendly formats.

## Data Flow (Textual Diagram)
- Text → Chunker → Embedder → FAISS
- Question → Retriever → Reranker → Prompt Builder → GPT-4 → Answer
- Quiz attempt → Mastery updater (BKT) → RL selector → Next item
- Mastery → Recommender → Study plan

## Scaling
- Precompute embeddings; parallel chunk processing.
- Streaming retrieval logs; performance telemetry.
- Graceful degradation: fallback to precomputed summaries when LLM unavailable.
