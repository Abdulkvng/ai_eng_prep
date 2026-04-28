# 04 - Tool Calling

## Mastery definition

Tool calling is when an LLM chooses to use an external function, API, database, or service to complete a task.

Simple version:

> The model decides what tool to call, passes arguments, reads the result, and uses that result to answer.

## Visual

```txt
User asks question
      ↓
LLM decides it needs a tool
      ↓
Tool call: search_docs(query="refund policy")
      ↓
Tool returns result
      ↓
LLM writes final answer
```

## Why tool calling matters

LLMs alone cannot reliably:

- fetch live data
- query private databases
- send emails
- run code
- update systems
- check account balances

Tools let the model act on real systems.

## Example Python-style tool

```python
def get_customer_balance(customer_id: str) -> dict:
    return {
        "customer_id": customer_id,
        "balance": 245.50,
        "currency": "USD"
    }
```

The LLM might call:

```json
{
  "tool": "get_customer_balance",
  "arguments": {
    "customer_id": "cus_123"
  }
}
```

## Tool calling risks

Tool calling is powerful but risky.

Risks:

- wrong tool
- wrong arguments
- unauthorized action
- data leak
- expensive repeated calls
- destructive action without confirmation

## Guardrails for tools

Use:

- allowlists for tools
- permission checks
- confirmation before sensitive actions
- logging
- rate limits
- schema validation

## Good interview answer

If asked how you would build tool calling safely:

> I would expose only narrow, permissioned tools with strict schemas. I would validate tool arguments before execution, log each call, rate limit expensive tools, and require confirmation for destructive actions like sending money, deleting data, or changing account settings.

## Quiz

1. What is tool calling?
2. Why can’t an LLM just do everything by itself?
3. Name 3 risks of tool calling.
4. What is one reason to require human confirmation?

## Answer key

1. Tool calling is when an LLM uses external functions or APIs.
2. Because LLMs do not have direct access to live/private systems unless connected.
3. Wrong tool, wrong arguments, data leak, unauthorized action, high cost.
4. To prevent irreversible or sensitive actions from happening accidentally.
