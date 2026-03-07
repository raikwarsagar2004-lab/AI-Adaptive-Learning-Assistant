# Recommendation System

## Purpose
- Generate personalized study plans targeting weak skills and optimizing reinforcement.

## Inputs
- Mastery per topic, recent performance, document coverage, time on task.

## Outputs
- Study plan with prioritized topics, recommended readings (document sections), practice quiz sets.

## Algorithm
- Weak Topic Detection: Identify skills below threshold.
- Coverage Mapping: Link skills to document sections and example questions.
- Plan Assembly: Mix review and practice; spaced repetition scheduling.

## Textual Flow
- Mastery → Weak topics → Map to docs → Assemble plan → Present

## Scaling
- Cache per-user plan; invalidate on significant profile changes.
- Batch recompute nightly; on-demand recompute after major events.
