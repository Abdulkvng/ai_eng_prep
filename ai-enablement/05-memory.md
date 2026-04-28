# 05 - Memory in AI Systems (Mastery Level)

## Mastery definition

Memory is the part of an AI system that stores information from previous interactions so the system can use it later.

Simple version:

> Memory lets an AI remember useful context instead of treating every request like a brand-new conversation.

## Why memory matters

Without memory, an AI assistant is stateless.

That means:

- it forgets previous preferences
- it cannot track long-running tasks
- it cannot personalize responses
- it cannot maintain project context

With memory, an AI system can feel more useful because it can carry context forward.

## Visual

```txt
User message
   ↓
AI system
   ↓
Should anything be remembered?
   ↓
Memory store
   ↓
Future request uses saved context
```

## Types of memory

### 1. Short-term memory

Short-term memory is context from the current conversation.

Example:

```txt
User: My project is called StackSense.
User later: Write a tagline for it.
```

The model can use the earlier message because it is still in the context window.

### 2. Long-term memory

Long-term memory persists across sessions.

Example:

```txt
The user prefers concise writing with no em dashes.
```

This can be reused later even if the current chat does not include it.

### 3. Episodic memory

Episodic memory stores specific past events or interactions.

Example:

```txt
The user practiced a Mercury AI Enablement interview on April 27.
```

### 4. Semantic memory

Semantic memory stores stable facts.

Example:

```txt
The user is a CS and Business student at USC.
```

### 5. Working memory

Working memory is temporary memory used while solving a task.

Example:

```txt
Step 1: retrieve docs
Step 2: summarize docs
Step 3: draft final answer
```

## Memory vs RAG

Memory and RAG are related, but not the same.

```txt
Memory = what the system remembers about the user or task
RAG    = external knowledge retrieved from documents or databases
```

Example:

- Memory: user likes concise answers
- RAG: company policy document about refunds

## Memory architecture

```txt
User request
   ↓
Retrieve relevant memory
   ↓
Retrieve external documents if needed
   ↓
Build prompt
   ↓
LLM response
   ↓
Decide what new memory to save
```

## Example memory object

```json
{
  "type": "preference",
  "content": "User prefers concise interview prep notes with simple examples.",
  "confidence": 0.92,
  "last_updated": "2026-04-27"
}
```

## Simple code example

```python
memory_store = []

def save_memory(user_id, key, value):
    memory_store.append({
        "user_id": user_id,
        "key": key,
        "value": value
    })


def get_memory(user_id):
    return [m for m in memory_store if m["user_id"] == user_id]

save_memory("user_123", "style", "prefers concise explanations")
print(get_memory("user_123"))
```

## Production memory concerns

Memory can be dangerous if handled poorly.

You must think about:

- privacy
- user consent
- data deletion
- stale memories
- incorrect memories
- sensitive data
- access control

## Memory guardrails

Good systems should:

- avoid saving sensitive information unless needed
- allow users to edit or delete memory
- attach confidence scores
- expire stale memories
- separate private user memory from shared company memory

## Failure cases

### Failure 1: Remembering wrong facts

The system saves:

```txt
User works at Mercury.
```

But the user only applied to Mercury.

Bad memory creates bad personalization.

### Failure 2: Remembering sensitive data

The system saves:

```txt
User's passport number is ...
```

This creates privacy risk.

### Failure 3: Using memory in the wrong context

A casual preference should not affect a legal, medical, or security-sensitive answer.

## Good interview answer

> Memory lets an AI system reuse useful context across interactions. I would separate short-term conversation memory from long-term user or task memory. I would also add guardrails around what gets stored, make memories editable or deletable, and avoid storing sensitive information unless there is a clear reason and permission.

## Bad interview answer

> Memory just means storing everything the user says.

Why this is bad:

- privacy risk
- expensive
- messy
- creates incorrect assumptions
- does not distinguish useful memory from noise

## Quiz

1. What is memory in an AI system?
2. What is the difference between memory and RAG?
3. Name two types of memory.
4. Why is storing everything dangerous?
5. What is one guardrail for memory?

## Answer key

1. Memory stores useful information from past interactions so the system can use it later.
2. Memory stores user/task context. RAG retrieves external knowledge from documents or databases.
3. Short-term, long-term, episodic, semantic, working memory.
4. It can store sensitive, wrong, stale, or irrelevant information.
5. Let users delete memory, avoid sensitive data, use confidence scores, or expire stale memories.
