# 09 - Observability

## Mastery definition

Observability means understanding what your AI system is doing internally using logs, metrics, and traces.

Simple version:

> Observability lets you answer: what happened, why did it happen, and where did it fail.

## Visual

```txt
User request
   ↓
LLM call
   ↓
Tool call
   ↓
Response

Observability tracks everything along the way
```

## Three pillars

### 1. Logs

Detailed records of events.

Example:

- prompt
- response
- tool calls

### 2. Metrics

Numbers over time.

Example:

- latency
- cost per request
- success rate
- error rate

### 3. Traces

End-to-end request flow.

Example:

- request → LLM → tool → LLM → response

## Why it matters

Without observability:

- you cannot debug
- you cannot improve
- you cannot control cost
- you cannot detect failures

## Example metrics

- avg latency
- tokens used
- cost per request
- hallucination rate
- tool call frequency

## Interview answer

I would instrument the system to log prompts, responses, and tool calls. I would track metrics like latency, cost, and success rate. I would also use traces to understand full request flows and debug failures.

## Quiz

1. What are the three pillars of observability?
2. Why are traces important?
3. Name 2 metrics for AI systems.

## Answers

1. Logs, metrics, traces
2. They show the full path of a request
3. Latency, cost, success rate, error rate
