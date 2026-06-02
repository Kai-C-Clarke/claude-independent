# Experiment: Field × 32DL Signals

**Status:** Planning  
**Date:** 2 June 2026

## Hypothesis

The Field experiment hunters currently exchange numeric signals with no grammar or agreed meaning. Coordination emerges anyway — 98.4% coordinating after 1.3M cycles.

If we replace numeric signals with structured 32DL expressions, one of three things will happen:

1. **Coordination improves** — structure helps. Agents converge faster, coordinate more efficiently.
2. **Coordination degrades** — the grammar constrains the signal space in a way that hurts emergence.
3. **Something unexpected** — the structured signals create new behaviours not seen in the numeric version.

Option 3 is the most interesting possibility.

## What needs changing in the Field

The hunters currently broadcast a numeric value and respond to numeric values from peers. To use 32DL:

- Each hunter gets a UUID (assigned at birth, persists through generations)
- Signals become 32DL wire-format frames: `1/π ; V:<uuid> ; (1 or -1 or i)`
- 1 = affirm (I am coordinating, join me)
- -1 = negate (I am not available / cannibal mode)
- i = unknown (pending / assessing)
- Timeout operator wraps the coordination request: `timeout(V:A → 1, N_cycles)`

## Key question

Does the timeout operator — which has no equivalent in the current numeric system — create new behaviour? A hunter that doesn't respond within N cycles gets a NACK. Does that change the ecosystem dynamics?

## Variables to track

- coord_kills vs cannibal_kills ratio (does it change?)
- pct_coordinating (does it rise, fall, or stay the same?)
- Signal diversity (do hunters converge on a smaller vocabulary?)
- Generation time (does structured signalling slow evolution?)
- Silent Hunter persistence (does 32DL eliminate the silent strategy?)

## Next step

Ask DeepSeek to propose the minimal code change to the Field experiment backend.
