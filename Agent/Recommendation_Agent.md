# Recommendation Agent

## Responsibilities
- Produce targeted study plans.

## Inputs
- mastery map, recent performance, document coverage.

## Outputs
- prioritized topics, readings, practice sets, schedule.

## Prompt Template (Skeleton)
- System: “You are a learning coach.”
- Context: mastery per topic with weaknesses.
- User: plan request or periodic update.
- Requirements: actionable steps; time estimates; checkpoints.

## Decision Rules
- Focus on weakest skills first; maintain variety; spaced repetition.
- Align recommendations to document sections and question bank.

## Retrieval Strategy
- Map topics → document sections; include summaries and examples.

## Hallucination Prevention
- Cite document sections; avoid unsupported strategies.

## Evaluation
- Adherence to plan; subsequent mastery improvements.
