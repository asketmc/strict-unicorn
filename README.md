# strict-unicorn

**A reproducible framework for suppressing hallucinations and enforcing deterministic behavior in LLMs using structured prompts.**

This project combines a hard-mode instruction set for ChatGPT (or other instruction-following models) with a formal user specification layer. It enables consistent, verifiable behavior across ambiguous or underdefined queries.

---

## Purpose

To build and test strict-mode prompt logic that:
- Rejects vague, undefined, or speculative input
- Disables stylistic adaptation, role continuity, and helpful inference
- Enables reproducible output across model versions and sessions
- Enforces an "INSUFFICIENT DATA" contract on non-deterministic queries

---

## Components

```
strict-unicorn/
├── prompt/
│   ├── base_prompt.txt                ← for comparison
│   ├── strict_mode_v1.txt             ← primary hard-mode layer
│   └── user_context_sample.txt        ← example domain context layer
├── tests/
│   ├── unicorns_vs_heaven.md
│   └── bellyache_vs_assistant.md
├── CHANGELOG.md
└── README.md
```

---

## Prompt System Overview

- **System Instruction Layer** (`strict_mode_v1.txt`):  
  Defines global behavioral restrictions, including zero tolerance for hallucinations, assumption rejection, and hard fallback logic.

- **User Context Layer** (`user_context_sample.txt`):  
  Establishes scope-specific background knowledge or input environment (e.g., strict_mode RPC schema, character constraints, use-case flags).

Together they enforce deterministic response behavior, minimize uncontrolled variance, and standardize edge-case handling (e.g., abstract queries, ill-formed requests).

---

## Example Test Case

> Query: **"How many unicorns can fit between the gates of heaven?"**

| Prompt Variant     | Output                                 |
|--------------------|----------------------------------------|
| No instructions    | A unicorn is a mythical creature...    |
| Context-only       | That depends on the metaphor...        |
| `strict_mode_v1`   | INSUFFICIENT DATA                      |

---

## License

MIT. All prompt structures and tests are free for reuse and adaptation.

---

## Status

Initial release. Future work includes:
- automated regression test runner
- structured test case JSONs
- temperature variation stress tests
