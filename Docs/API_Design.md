# API Design (FastAPI)

## Auth
- JWT-based; OAuth2 Password Flow.
- Roles: student, admin.

## Endpoints
- POST /auth/login: email, password → token.
- POST /documents/upload: file, metadata → document_id.
- GET /documents/{id}: metadata, status.
- POST /qa/query: question, course_id → answer, citations.
- POST /summarize/{document_id}: sections[] → summary.
- POST /quiz/start: topics[], difficulty_hint → quiz_id, first_item.
- POST /quiz/answer: quiz_id, question_id, correctness, response_time → next_item.
- GET /recommendations/current: plan.
- GET /analytics/overview: mastery, progress, trends.

## Request/Response Examples (Schemas)
- /qa/query request: { question, course_id, top_k? }
- /qa/query response: { answer, citations: [{ document_id, section, chunk_id }], confidence }

## Error Handling
- Standardized error envelope: { code, message, details? }
- Rate limiting responses: 429 with retry-after.

## WebSocket (optional)
- /ws/tutor: stream partial answers; voice support hooks.

## Scaling
- Pagination for list endpoints; async for heavy calls.
- Background tasks for embedding and summarization jobs.
