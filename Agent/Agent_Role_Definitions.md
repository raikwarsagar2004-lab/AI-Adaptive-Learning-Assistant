# Agent Role Definitions

## Knowledge Retrieval Agent
- Role: Retrieve, rerank, and ground answers with citations.
- Inputs: Question, context constraints.
- Outputs: Context bundle, grounded answer with sources.

## Quiz Generation Agent
- Role: Generate and select questions with dynamic difficulty.
- Inputs: Topics, mastery state, constraints.
- Outputs: Next question item, rationale.

## Recommendation Agent
- Role: Create personalized study plans.
- Inputs: Mastery map, performance history.
- Outputs: Plan with readings and practice sets.

## Analytics Agent
- Role: Aggregate events, compute metrics, feed dashboards.
- Inputs: Event stream.
- Outputs: Aggregated metrics and insights.
