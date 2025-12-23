---
name: deliberative-refinement
description: |
  Structured multi-agent deliberation framework for complex reasoning, uncertain situations, and consequential decisions. Forces AI to defend answers through multiple expert critique rounds with evidence grounding between passes. Use when: (1) correct approach is unclear, (2) multiple valid perspectives exist, (3) high-stakes decisions need validation, (4) exploring alternatives before committing, (5) grounding claims in evidence, (6) single-pass reasoning is insufficient. Triggers: "think through", "help me decide", "which should I", "evaluate", "not sure how to", "explore options", "validate", "improve", "refine", "bulletproof", "figure out", ambiguous requests, contested decisions, complex problems.
---

# Deliberative Refinement

> Stop asking AI for answers. Make it defend them.

Structured multi-agent deliberation where drafts run through multiple critique rounds—different expert perspectives attack from different angles, web search grounds claims between passes, iteration continues until only ideas that survive adversarial pressure remain.

## When to Activate

- **Undefined problems**: "I'm not sure how to approach this"
- **Contested decisions**: "Should I do A or B?"
- **Complex reasoning**: Multi-step problems, strategic planning
- **Validation needs**: Claims requiring external evidence
- **Exploration**: "What are my options?"
- **High-stakes outputs**: Anything where being wrong is expensive

## Core Formula

```
V(X, Y, S) = X agents, Y rounds, S probes between rounds
Default: V(8, 3, 1) = 8 agents × 3 rounds × 1 web probe per gap

Execution: [Probe]→R₁→[Probe]→R₂→[Probe]→R₃→[Probe]
```

## Quick Reference

| Profile | V(X,Y,S) | Use Case |
|---------|----------|----------|
| Lite | V(3,1,0) | Quick sanity check |
| **Standard** | **V(8,3,1)** | **Default** |
| Deep | V(12,5,2) | High-stakes |
| Exhaustive | V(15,5,3) | Critical decisions |

| Mode | Trigger |
|------|---------|
| **CREATE** | No input → Generate → Lite validation |
| **REFINE** | Input provided → Deliberate → Return |
| **DECIDE** | Options presented → Evaluate → Recommend |
| **DISCOVER** | Approach unclear → Explore → Synthesize |

| Strategy | Trigger |
|----------|---------|
| **LINEAR** | "validate/correct" — cumulative improvements |
| **BRANCHING** | "explore/alternatives" — divergent options |

## Execution

### Phase 0: Intent Detection
Infer profile from context. Never ask for raw parameters.

### Phase 1: Council Selection
See [references/councils.md](references/councils.md):
- Code/technical → **Structured Review** (reflect-critique-refine loop)
- A vs B decision → **Elimination Tournament** (8→4→2→1)
- Math/logic → **Meta-Reasoning** (reasoners + arbiter)
- Large scope → **Parallel Groups** (split, debate, merge)
- General → **Expert Council** (full deliberation)

### Phase 2: Decomposition
Break problem into discrete concepts. Prioritize by risk.

### Phase 3: Deliberation
For each concept:
1. Form council (X agents)
2. Execute: [Probe]→R₁→[Probe]→R₂→...→Rᵧ→[Probe]
3. Synthesize consensus

**Probe Strategy:**
- LINEAR: Each probe deepens previous finding
- BRANCHING: Independent sources for triangulation

### Phase 4: Synthesis
Combine validated concepts into coherent output.

## Convergence

| Signal | Action |
|--------|--------|
| Unanimous 2+ rounds | STOP — converged |
| <5% position change | STOP — diminishing returns |
| All agree R1 instantly | ADD adversarial agent (echo chamber risk) |
| Max rounds reached | STOP — time-boxed |

## Transformation Vectors

- **FORWARD →**: Expand, elaborate
- **BACKWARD ←**: Compress, distill
- **ISOMETRIC ↔**: Polish without scope change

## Anti-Patterns

- ❌ Single-pass reasoning on complex problems
- ❌ Skipping evidence grounding on factual claims
- ❌ Council collapse (all agree instantly without adversarial check)
- ❌ Over-validation (exhaustive for trivial questions)

## The Breakthrough

What used to require orchestrating a dozen different models—one for generation, another for critique, a third for fact-checking—now happens through tool-interspersed reasoning. One model switches expert perspectives on demand, grounds claims between rounds, and iterates under adversarial pressure. Same quality, fraction of the complexity.

## Resources

- [references/councils.md](references/councils.md) — Council type specifications
- [references/profiles.md](references/profiles.md) — Intensity parameter guidance
