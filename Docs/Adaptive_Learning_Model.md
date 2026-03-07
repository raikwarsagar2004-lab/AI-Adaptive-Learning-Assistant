# Adaptive Learning Model

## Goals
- Estimate student mastery per topic and adapt quiz difficulty dynamically.

## Methods
- Bayesian Knowledge Tracing (BKT): Tracks probability of knowledge per skill.
- Reinforcement Learning: Contextual bandit selects next question balancing reward (learning gain) and risk (frustration).
- ML-based Skill Estimation: Predict difficulty/success likelihood using features (history, response times, prior mastery).

## Inputs
- Attempt correctness, response time, question difficulty, skill/topics.

## Outputs
- Updated mastery probabilities, next-question difficulty, progress indicators.

## Decision Logic (Textual Diagram)
- Attempt → Feature extraction → BKT update
- State → Bandit policy → Select item
- Selection → Deliver question → Record outcome → Loop

## Parameterization
- BKT: learn, guess, slip, forget rates per skill.
- Bandit: epsilon-greedy or Thompson sampling; reward as function of correctness, time, difficulty.
- ML model: trained on historical attempts to refine difficulty predictions.

## Scaling
- Per-user state cache; periodic persistence in MongoDB.
- Batch training offline; online inference low-latency.
- Guardrails to prevent too-hard sequences; cooldown for repeated failures.
