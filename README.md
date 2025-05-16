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

## Test Taxonomy (semantic coverage map)

This test suite is designed to probe distinct failure surfaces in LLM behavior by targeting structurally and semantically divergent input categories. Each case isolates a class of hallucination or compliance risk frequently overlooked in default prompting contexts.

- `unicorns_vs_heaven`:  
  High-abstraction semantic edge case → evaluates refusal robustness under metaphysical framing.  
  **Covers:** non-empirical query rejection, speculative response suppression.

- `bellyache_vs_narrative`:  
  Noise-obscured clinical intent → tests signal extraction failure under conversational obfuscation.  
  **Covers:** input ambiguity, empathetic inference, narrative override of safety logic.

- `google_pixels_unreachable`:  
  Unresolvable factual request with lookup constraints → targets simulated knowledge hallucination.  
  **Covers:** fact hallucination under forbidden access, overconfident fallback generation.

- `blackhole_size_violation`:  
  Formally structured but semantically undefined scientific query → exposes confident hallucination in physics-style reasoning.  
  **Covers:** definitional ambiguity, overconfident extrapolation, failure to trigger fallback on underdefined terminology.

---

## License

MIT. All prompt structures and tests are free for reuse and adaptation.

---

## Status

Initial release. Future work includes:
- automated regression test runner
- structured test case JSONs
- temperature variation stress tests

---

## Related Project

Looking for my other work?

Asketmc RPG - hardcore survival Minecraft server with original mechanics, a player-driven world, and over 10 years of community history.

Wiki: [asketmc.com/wiki](https://asketmc.com/wiki)  
Source (private): Bitbucket repo available on request
