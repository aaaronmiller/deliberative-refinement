# Deliberative Refinement

> Stop asking AI for answers. Make it defend them.

A structured multi-agent deliberation framework for complex reasoning, uncertain situations, and consequential decisions.

## What Is This?

**Deliberative Refinement** forces AI through multiple rounds of structured critique—different expert perspectives attack from different angles, web search grounds claims between passes, iteration continues until only ideas that survive adversarial pressure remain.

### The Core Idea

Instead of prompt → output → polish, you architect critique rounds:

1. **Expert councils** attack the draft from different angles (code reviewers, strategy councils, elimination tournaments)
2. **Web search** grounds claims with actual evidence between rounds
3. **Iteration** continues until weak ideas die and strong ones survive

### The Breakthrough

Six months ago, this required orchestrating a dozen different models—one for generation, another for critique, a third for fact-checking. **Tool-interspersed reasoning** collapsed all of that into a single model that switches roles on demand. Same quality, fraction of the complexity.

## Quick Start

### As a Claude Skill

```bash
# Clone this repo
git clone https://github.com/YOUR_USERNAME/deliberative-refinement.git

# Copy to your Claude skills directory
cp -r deliberative-refinement ~/.claude/skills/
```

Or install via marketplace:
```
/plugin marketplace add YOUR_USERNAME/deliberative-refinement
```

### As a Slash Command

Copy `slashcommand-deliberative-refinement.md` to your preferred slash command directory.

## How It Works

### The Formula

```
V(X, Y, S) = X agents, Y rounds, S probes between rounds
Default: V(8, 3, 1) = 8 agents × 3 rounds × 1 web probe per gap
```

### Profiles

| Profile | V(X,Y,S) | Use Case |
|---------|----------|----------|
| Lite | V(3,1,0) | Quick sanity check |
| **Standard** | **V(8,3,1)** | **Default** |
| Deep | V(12,5,2) | High-stakes decisions |
| Exhaustive | V(15,5,3) | Critical outcomes |

### Modes

| Mode | Trigger |
|------|---------|
| **CREATE** | No input → Generate → Validate |
| **REFINE** | Input provided → Deliberate → Return |
| **DECIDE** | Options presented → Evaluate → Recommend |
| **DISCOVER** | Approach unclear → Explore → Synthesize |

### Council Types

| Council | Best For |
|---------|----------|
| **Expert Council** | General problems, synthesis |
| **Structured Review** | Code, technical analysis |
| **Elimination Tournament** | Binary A vs B decisions |
| **Meta-Reasoning** | Math, proofs, sequential logic |
| **Parallel Groups** | Large scope, budget limits |

## Why This Matters

**Single-pass prompting** optimizes for *plausible*.

**Deliberative refinement** optimizes for *robust*.

It's the difference between "AI said so" and "survived peer review."

### Use Cases

- Strategy docs that survive executive review
- Technical specs that don't detonate in production
- Research that holds up to scrutiny
- Legal documents that don't need 3 revision cycles
- Architecture decisions that don't implode at scale

## File Structure

```
deliberative-refinement/
├── SKILL.md                              # Claude skill definition
├── slashcommand-deliberative-refinement.md  # Slash command version
├── marketplace.json                      # For marketplace installation
├── references/
│   ├── councils.md                       # Council type specifications
│   └── profiles.md                       # Intensity profiles
└── README.md                             # This file
```

## Contributing

PRs welcome. If you've found improvements to council configurations, probe strategies, or convergence criteria, open an issue or submit a PR.

## License

MIT

---

**Generation is table stakes. Making AI defend its ideas until they break or bend? That's the new standard.**
