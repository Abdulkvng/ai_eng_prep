# 07 - Guardrails

## What are guardrails

Guardrails are rules and systems that control what an AI system is allowed to do.

Simple definition:

> Guardrails prevent bad outputs, unsafe behavior, or incorrect actions.

## Why guardrails matter

LLMs can:

- hallucinate
- produce harmful content
- give wrong answers confidently
- leak sensitive data

Guardrails reduce these risks.

## Types of guardrails

### 1. Input guardrails

Check user input before sending it to the model.

Examples:

- block malicious prompts
- remove sensitive data
- detect jailbreak attempts

### 2. Output guardrails

Check model output before returning to user.

Examples:

- filter harmful responses
- check factual accuracy
- enforce formatting rules

### 3. Tool guardrails

Control what tools the AI can use.

Examples:

- limit database queries
- restrict API access
- require confirmations before actions

### 4. Behavioral guardrails

Control how the model behaves.

Examples:

- "If unsure, say you don’t know"
- "Always cite sources"
- "Do not answer outside given context"

## Common techniques

### 1. Prompt constraints

Add rules directly in system prompt.

### 2. Validation layers

Run checks after output.

### 3. Rule-based filters

Regex, keyword filters, policy rules.

### 4. Model-based moderation

Use another model to evaluate output.

### 5. Structured outputs

Force JSON or schema.

## Example guardrail system

User asks question
→ check input
→ retrieve documents
→ generate answer
→ validate answer
→ return result

## Interview answer pattern

If asked:

"How do you make AI safer?"

Say:

I would add guardrails at multiple stages. First I would validate user input to detect malicious prompts. Then I would constrain the model using system instructions. After generation, I would validate outputs using rules or another model, and enforce structured formats. I would also log failures and continuously improve the guardrails based on real usage.

