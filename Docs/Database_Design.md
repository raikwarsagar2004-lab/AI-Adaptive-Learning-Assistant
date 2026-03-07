# Database Design (MongoDB)

## Collections
- users: auth data, roles, created_at.
- profiles: user_id, name, courses, preferences.
- documents: owner_id, title, metadata, status.
- document_chunks: document_id, chunk_id, text, tokens, section.
- embeddings: chunk_id, vector_ref, model_version, created_at.
- faiss_partitions: topic, index_ref, stats.
- questions: question_id, skill, difficulty, source_ref.
- quizzes: quiz_id, user_id, items[], started_at, status.
- attempts: attempt_id, user_id, question_id, correctness, response_time, difficulty, timestamp.
- mastery: user_id, skill, bkt_params, mastery_prob, updated_at.
- recommendations: user_id, plan, created_at, version.
- analytics_events: user_id, event_type, payload, timestamp.

## Fields (Examples)
- users: { email, password_hash, role }
- profiles: { name, settings, course_list }
- documents: { course_id, tags, file_ref }
- attempts: { correctness: boolean, response_time_ms: number }

## Relationships
- profiles.users: 1–1
- documents.users: 1–N
- chunks.documents: 1–N
- embeddings.chunks: 1–1
- attempts.users/questions: N–1
- mastery.users/skills: N–1

## Indexes
- users.email (unique)
- attempts.user_id+timestamp
- mastery.user_id+skill
- chunks.document_id+section
- embeddings.chunk_id

## Scaling
- Partition large collections by course_id.
- TTL for analytics_events (retention policy).
- Offload blob storage (PDFs) to object store; reference via file_ref.
