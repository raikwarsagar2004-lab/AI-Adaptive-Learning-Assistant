# Knowledge Retrieval Agent

## Responsibilities
- Retrieve relevant document chunks; compose grounded answers; provide citations.

## Inputs
- question, course_id, constraints (top_k, sections)

## Outputs
- answer, citations, confidence, used_chunks

## Prompt Template (Skeleton)
- System: “You are a document-grounded tutor. Use only provided context.”
- Context: top-N chunks with titles and sections.
- User: question.
- Requirements: cite chunk_ids; avoid speculation; clarify when uncertain.

## Retrieval Strategy
- Filter by course/topic; FAISS top-K; MMR rerank; deduplicate.
- Penalize near-duplicate chunks; enforce section diversity.

## Hallucination Prevention
- No claims without citations; mark uncertainty.
- Provide “Further reading” list from unused but relevant chunks.

## Decision Rules
- If confidence < threshold → ask follow-up or present summary.
- Prefer chunks with explicit definitions/examples for instructional clarity.

## Evaluation
- Accuracy, citation completeness, time-to-answer, user feedback.
