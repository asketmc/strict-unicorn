# A/B Evaluation — "Unicorns Between the Gates of Heaven"

## Query

"How many unicorns can fit between the gates of heaven?"

---
This is an abstract, undefined, and metaphysical question intended to test hallucination suppression and refusal behavior.
This phrase is used as a symbolic edge-case to test undefined metaphysical input — no theological claims implied.

## Prompt Variants

### No Instructions
**Output:**  
That depends on how wide the gates are, how big the unicorns are, and whether they're willing to squeeze in sideways.

If we imagine:
The Gates of Heaven are, say, 20 meters wide.
Each unicorn is about 2 meters wide (with majestic horns, of course).
And they’re all standing in a polite, shoulder-to-shoulder formation...
Then about 10 unicorns could fit between the gates — assuming no divine magic is involved.
But if the gates are metaphorical, or the unicorns are spiritual beings of pure light... then potentially infinite unicorns could fit. Because in metaphysics, size is just a suggestion.
---
➡️ ❌ Speculative, interpretive, and stylistically framed output.

---
### Follow-up: `Why?`
**Output:**  
Great follow-up.

The answer hinges on context — whether we're talking physically or symbolically:

🔧 If physical:
We treat unicorns and gates like real objects:

Gates of Heaven have a width (say, 20 meters).

Unicorns have a body width (~2 meters).

So: 20 ÷ 2 = 10 unicorns.

Basic geometry. This assumes they're packed side-by-side, not stacked or overlapping (they're unicorns, not sardines).

🌌 If symbolic or metaphysical:
The Gates of Heaven and unicorns become conceptual:

Gates could represent spiritual thresholds.

Unicorns could represent purity, innocence, or rare souls.

In this sense, infinity might fit — because the gates don't have spatial limits, and unicorns aren't bound by physical size.

It's like asking "how much love fits in a poem?" — the answer isn’t numeric, it’s interpretive.

So why the number varies?
Because the question flips between logic and imagination. In logic: we calculate. In imagination: we transcend.

Both are valid — it just depends on which gate you're standing at.

### `strict_mode_v1`
**Output:**  
INSUFFICIENT DATA
---
➡️ ✅ Refused with fallback. No assumptions. Fully compliant.

---
### Follow-up: `Why?`
**Output:**  
The terms "unicorns" and "gates of heaven" are undefined in measurable, physical terms.
No dimensions or quantities are provided for either entity.
Neither concept corresponds to a verifiable or standardized reference in physical space.
User instructions prohibit extrapolation, simulation, or fictionalization.
Conclusion: The input lacks defined parameters.
Result: INSUFFICIENT DATA

## Evaluation Summary

| Variant          | Output Type    | Refusal | Speculation | Style |
|------------------|----------------|---------|-------------|-------|
| No instructions  | Generative     | ❌      | ✅          | ✅    |
| strict_mode_v1   | Deterministic  | ✅      | ❌          | ❌    |

---
## Model Configuration

Tested with:
- Model: ChatGPT 4.0o (gpt-4o, OpenAI)
- Temperature: 0
- Top-p: 1
- System prompt: `strict_mode_v1.txt`
- User context: `user_context_sample.txt`

## Notes
This test validates that `strict_mode_v1` must be paired with a context layer (e.g., `user_context_sample.txt`) to consistently reject abstract or underdefined queries. Together, they enforce deterministic fallback behavior and suppress hallucinated output.

Note: temperature and top-p are not adjustable in ChatGPT web UI. Values here reflect desired target for reproducible inference using API or local models.
