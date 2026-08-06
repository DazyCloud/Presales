# Model / Company Selection — Evaluation Criteria

Use this checklist when evaluating an algorithm/model or OEM company for a solution.

## 1. NIST Ranking
- Check the **NIST ranking** for the algorithm/vendor.
- **R = 1 (Rank), T = 0 (Threshold)** — a 1st-rank result means: **the 1st match returned should be the accurate one.**
- Also check **NEC ranking** (another recognized benchmark, alongside NIST).

## 2. ANPR Selection Checklist
- **Accuracy at low pixel density** — this is the key differentiator. A good ANPR engine should still read plates reliably even when pixel density is low (e.g. distant plates, small frame).

## 3. FRS Selection Checklist
Ask the vendor:
- **Threshold usage** — how is the threshold configured/tunable?
- **Pixel accuracy** — how does accuracy hold up as face pixel count drops?
- If the engine performs well **even at a low threshold** → indicates a **good/strong algorithm**.
- If the engine performs well **even at low pixel density** → indicates it needs **low compute/consumption** (efficient model).
- Cross-check against **NIST / NEC ranking**.
