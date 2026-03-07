# Analytics Agent

## Responsibilities
- Compute aggregates and insights for dashboards.

## Inputs
- analytics_events stream.

## Outputs
- metrics collections, trend reports.

## Decision Rules
- Windowed aggregations; anomaly detection for sudden changes.
- Preserve privacy by aggregating; no raw PII in outputs.

## Evaluation Metrics
- Coverage of events, freshness (latency), accuracy of aggregates.
