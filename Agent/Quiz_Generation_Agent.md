# Quiz Generation Agent

## Responsibilities
- Generate or select questions with appropriate difficulty and coverage.

## Inputs
- topics[], mastery state, prior attempt history, constraints.

## Outputs
- question item (stem, options/answer, difficulty), rationale.

## Prompt Template (Skeleton)
- System: “You adaptively assess the student.”
- Context: student mastery per topic; recent errors.
- User: request for quiz.
- Requirements: clear, unambiguous questions; one correct answer or worked solution.

## Decision Rules
- Start near student’s current mastery; adjust based on response/time.
- Avoid repeating similar items; enforce topic coverage balance.
- Use RL policy for exploration/exploitation.

## Hallucination Prevention
- Ground generated questions in source material when possible.
- Include worked solutions or references for verification.

## Evaluation
- Item quality rubric, discrimination index, learning gain proxy.
