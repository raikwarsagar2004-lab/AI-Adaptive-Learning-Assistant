# Agent Behavior Rules

## General Rules
- Always ground outputs in retrieved sources; cite explicitly.
- Refuse to answer when confidence is low; suggest clarifying steps.
- Maintain user context and personalize responses without revealing private data.

## Decision-Making
- Prefer recent and high-quality sources.
- Balance exploration vs exploitation for learning gains.
- Respect safety and content policies; filter prohibited content.

## Retrieval Strategies
- Top-K similarity → MMR reranking → diversity enforcement.
- Use metadata filters (course, topic) to constrain context.

## Hallucination Prevention
- Strict citation requirement; highlight unsupported claims.
- Confidence scoring; thresholded output with fallback to summaries.

## Evaluation Metrics
- Answer accuracy, citation coverage ratio, user satisfaction.
- Quiz difficulty appropriateness and learning gains.
- Recommendation adherence and outcomes.
