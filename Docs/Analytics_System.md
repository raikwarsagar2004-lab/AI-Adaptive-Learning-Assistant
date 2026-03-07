# Analytics System

## Metrics
- Learning Progress: mastery over time per skill.
- Topic Mastery: current mastery distribution.
- Quiz Performance: accuracy, response time, difficulty progression.
- Engagement: session counts, time on task.

## Data Flow (Textual Diagram)
- Events → Aggregation jobs → Metrics collections → React charts

## Visualizations (React)
- Line charts for mastery trends.
- Bar charts for topic mastery.
- Scatter plots for difficulty vs accuracy.
- Heatmaps for document coverage.

## Scaling
- Incremental aggregates; windowed computations.
- Precompute dashboards nightly; live deltas during sessions.
