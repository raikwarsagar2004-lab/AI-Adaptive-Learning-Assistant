# Deployment Architecture

## Environments
- Dev: local FastAPI/React, test MongoDB, mock LLM.
- Staging: Cloud, real FAISS and managed LLM, test data.
- Prod: Auto-scaled API, FAISS shards, observability stack.

## Components
- Containers: Backend, Frontend, Workers.
- Orchestration: Docker Compose (dev), Kubernetes (prod).
- Storage: MongoDB cluster, object store for PDFs, FAISS volume.

## Textual Diagram
- LB → API Pods ↔ MongoDB Cluster
- API ↔ Workers (embedding, analytics)
- API ↔ FAISS nodes
- Frontend (CDN) ↔ API

## CI/CD
- Build images, run tests, security scans.
- Canary deploys; feature flags for modules.

## Scaling
- Horizontal autoscaling per latency metrics.
- Queue-based backpressure for workers.
