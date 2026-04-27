# 01 - LLM Basics

## What is an LLM

LLM means Large Language Model.

Simple definition:

> An LLM predicts the next token based on the tokens before it.

A token is a small piece of text. It can be a word, part of a word, punctuation, or space.

## What an LLM is good at

LLMs are good at tasks that involve language, patterns, and reasoning over text.

Examples:

- summarize text
- answer questions
- write code
- classify text
- extract structured data
- explain concepts
- brainstorm solutions

## What an LLM is bad at

LLMs can struggle with:

- exact facts
- private company data
- recent information
- math without tools
- following long instructions perfectly
- knowing when it is wrong

## Prompt

A prompt is the input you send to the model.

Example:

```txt
Summarize this support ticket in 3 bullets.
```

## Completion

The completion is the output the model returns.

## System prompt

The system prompt tells the model how to behave.

Example:

```txt
You are a helpful internal engineering assistant. Answer only using the provided docs. If unsure, say you do not know.
```

## Context window

The context window is how much text the model can read at once.

Large context windows help with long documents, but they cost more and can make outputs slower.

## Temperature

Temperature controls randomness.

Low temperature:

- more consistent
- better for facts and coding

High temperature:

- more creative
- less predictable

## Interview answer

If asked what an LLM is, say:

An LLM is a model that predicts text token by token based on context. In real systems, the important part is not just calling the model. You need to give it the right context, constrain its behavior, evaluate outputs, and monitor cost, latency, and quality.
