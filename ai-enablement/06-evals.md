# 06 - Evaluations (Evals)

## What are evals

Simple definition:

> Evals measure how well your AI system performs.

## Why evals matter

Without evals, you are guessing.

With evals, you can:

- compare prompts
- compare models
- detect regressions
- improve quality

## Types of evals

### Offline evals

Test on saved examples.

Example:

- 100 questions
- expected answers
- compare outputs

### Online evals

Measure real usage.

Example:

- click rate
- user feedback
- success rate

## Metrics

- accuracy
- hallucination rate
- latency
- cost
- helpfulness

## How to run evals

1. collect dataset
2. define metrics
3. run model
4. compare outputs
5. iterate

## Interview answer

I would build an eval pipeline with both offline test cases and online metrics. I would track performance over time and use eval results to guide improvements.
