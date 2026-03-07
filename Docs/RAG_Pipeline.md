# RAG Pipeline

## Responsibilities
- Convert documents into searchable vectors and support grounded QA and summarization.

## Steps
- PDF Processing: Text extraction; preserve structure; detect headings and figures.
- Chunking: Overlapping windows with semantic-aware boundaries.
- Embedding: Generate vectors with embeddings model; store metadata.
- Indexing: Insert into FAISS; maintain topic/collection partitions.
- Retrieval: Top-K similarity, reranking with MMR; deduplicate overlaps.
- QA: Assemble context; source citations; confidence scoring.
- Summarization: Hierarchical map-reduce summaries per section/document.

## Input/Output
- Input: PDF files, metadata (course, topics), query text.
- Output: Retrieved context, answers with citations, summaries.

## Textual Sequence Diagram
- Student uploads → Backend → Extract → Chunk → Embed → FAISS
- Student asks → Backend → FAISS search → Rerank → Prompt → GPT-4 → Answer (+citations)

## Index Management
- Partition per course/topic; maintain index stats.
- Periodic rebuilds for corrupted entries; versioned embeddings.

## Scaling
- Batch embedding workers; GPU acceleration.
- Cached retrieval for popular queries; cold storage for old documents.
