# 01 - LLM Basics (Mastery Level)

## Mastery definition

A Large Language Model (LLM) is a neural network trained to predict the next token in a sequence. Because it learns patterns from massive amounts of text and code, it can perform many language-based tasks such as summarization, question answering, coding, classification, and reasoning-like problem solving.

Simple version:

> An LLM reads text and predicts what text should come next.

## Mental model

Do not think of an LLM as a database.

Think of it as a powerful pattern engine.

```txt
Input tokens
   ↓
Model processes context
   ↓
Model predicts next token
   ↓
Repeat many times
   ↓
Final answer
```

## Token

A token is a small piece of text.

Examples:

```txt
"hello"        → maybe 1 token
"unbelievable" → could be multiple tokens
"AI systems"   → could be 2 or more tokens
```

Why tokens matter:

- pricing is based on tokens
- context windows are measured in tokens
- latency increases with more tokens

## Prompt

A prompt is the input you send to the model.

Example:

```txt
Summarize this incident report in 3 bullets.
```

## Completion

The completion is the model's output.

## System prompt

A system prompt is the highest-level instruction that tells the model how to behave.

Example:

```txt
You are an internal engineering assistant. Answer only using the provided documents. If the answer is not in the documents, say you do not know.
```

## Context window

The context window is the maximum amount of text the model can process at once.

Tradeoff:

```txt
Bigger context window
   → more information
   → higher cost
   → often slower
   → still may miss details
```

## Temperature

Temperature controls randomness.

Low temperature:

- more consistent
- better for facts
- better for code

High temperature:

- more creative
- less predictable

## What LLMs are good at

- summarization
- classification
- drafting
- code generation
- question answering
- data extraction
- brainstorming

## What LLMs are bad at

- knowing exact private facts
- staying fully up to date
- always admitting uncertainty
- doing exact math without tools
- following long instructions perfectly
- guaranteeing truth

## Basic API shape

```python
from openai import OpenAI

client = OpenAI()

response = client.chat.completions.create(
    model="gpt-4.1-mini",
    messages=[
        {"role": "system", "content": "You are a helpful engineering assistant."},
        {"role": "user", "content": "Explain latency in simple terms."}
    ],
    temperature=0.2,
)

print(response.choices[0].message.content)
```

## Bad interview answer

> An LLM is basically AI that knows everything.

Why this is bad:

- sounds vague
- ignores hallucinations
- ignores systems concerns

## Strong interview answer

> An LLM is a model that predicts tokens based on context. In production, the hard part is not just calling the model. You need to provide the right context, control behavior with prompts and guardrails, connect tools when needed, evaluate outputs, and monitor cost, latency, and quality.

## Quiz

1. What is a token?
2. Why is an LLM not the same as a database?
3. What does temperature control?
4. Why does context window size matter?
5. Why do production LLM systems need evals and monitoring?

## Answer key

1. A token is a small piece of text processed by the model.
2. A database stores exact facts. An LLM predicts likely text and can be wrong.
3. Randomness or creativity of the output.
4. It controls how much text the model can read and affects cost and latency.
5. Because outputs can fail, hallucinate, become expensive, or degrade over time.
