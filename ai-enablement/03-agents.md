# 03 - AI Agents

## What is an agent

Simple definition:

> An agent is an AI system that can take actions, not just generate text.

## Difference from normal LLM

Normal LLM:

Input → Output

Agent:

Input → Reason → Take action → Observe → Repeat → Output

## Agent loop

1. Understand task
2. Plan steps
3. Use tools
4. Observe results
5. Repeat until done

## Tools

Agents use tools like:

- search
- database queries
- APIs
- code execution

## Example

User: "Find best flights"

Agent:

- calls flight API
- compares options
- returns recommendation

## Risks

- infinite loops
- wrong tool usage
- high cost
- unpredictable behavior

## Guardrails needed

- limit steps
- restrict tools
- add confirmations

## Interview answer

I would use an agent when a task requires multiple steps or external tools. I would control it using limits, logging, and evals to ensure reliability.
