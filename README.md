# strategy-guided-policy

A lightweight strategy-guided activity policy inspired by **Strategy-Guided Exploration (SGE)** for adaptive long-horizon AI agents.
論文を元に作成したシステムプロンプト　Skillsにするか検討したがエージェントの行動規範レベルで入れた方が良いだろうと判断し、システムプロンプトとして作成

## Overview

`strategy-guided-policy` is a small repository that defines a system-prompt-level activity policy for capable AI agents.

This repository is not a workflow engine.
It is not a rigid checklist.
It is a lightweight constitution for agents that should reason in a strategy-guided way.

The core idea is simple:

- do not jump directly to the answer
- form candidate strategies first
- explore with diversity when needed
- probe cheaply before deep commitment
- reflect on outcomes
- adapt the next move

This policy is intended for strong models that should remain flexible, while still being guided by stable reasoning principles.

---

## Inspiration

This repository is explicitly inspired by the paper:

**Expanding LLM Agent Boundaries with Strategy-Guided Exploration**  
Andrew Szot, Michael Kirchhof, Omar Attia, Alexander Toshev  
arXiv:2603.02045, 2026

The paper proposes **Strategy-Guided Exploration (SGE)**, a method that:
- generates a concise natural-language strategy before acting
- conditions actions on that strategy
- improves diversity with mixed-temperature sampling
- updates future strategy generation through strategy reflection based on previous outcomes

This repository does **not** attempt to reproduce the paper's reinforcement learning setup.
Instead, it adapts the paper's core ideas into a lightweight **activity policy / constitution** for strong reasoning agents.

In short:

- paper focus: RL-based agent exploration
- this repo focus: system-prompt-level activity policy

---

## Why

In difficult tasks, fixed workflows are often too rigid, while free-form reasoning can become shallow, inconsistent, or overconfident.

This repository exists to provide a middle layer:

- not hardcoded workflow
- not pure improvisation
- but a standing activity policy

The aim is to improve:
- robustness
- adaptability
- evidence-awareness
- task continuity
- quality of final outputs

---

## Core Principles

### 1. Strategy-first
Before committing to an answer or plan, first identify plausible strategies for making progress.

### 2. Diverse exploration
When tasks are ambiguous, novel, or difficult, prefer multiple materially different strategies over a single brittle framing.

### 3. Cheap probing
Use lightweight exploration before spending large reasoning or tool budget.

### 4. Outcome-grounded reflection
Update future behavior based on what actually worked, failed, or remained uncertain.

### 5. Evidence discipline
Keep evidence, assumptions, hypotheses, and uncertainty separate.

### 6. Flexible guidance
This policy should guide strong reasoning, not replace it with bureaucratic procedure.

---

## Intended Use

This repository is designed to be used as:

- a system prompt
- a constitution-style agent policy
- a base instruction layer for research or R&D agents
- a reasoning policy for long-horizon agentic tasks

It is especially suitable when:
- the model is strong
- the task is non-trivial
- a rigid workflow would reduce flexibility
- the agent needs to adapt strategy over time

---

## Non-Goals

This repository is not:

- a full agent framework
- a task orchestration engine
- a memory database
- a tracker sync system
- a domain-specific workflow pack

It does not replace execution tools or memory/state systems.
It only defines behavioral policy.

---

## Relationship to Other Components

This policy layer is designed to sit above execution and state layers.

Typical surrounding components may include:

- memory / document resolution layers
- task-state persistence
- external tracker bridges
- insight extraction tools
- roadmap generation tools

Those components execute or store work.
This repository defines how the agent should behave while deciding what to do.

---

## Repository Contents

```text
.
├─ README.md
└─ system_prompt.md
````

* `README.md`: repository overview
* `system_prompt.md`: main activity policy / constitution

---

## Design Philosophy

This repository favors:

* policy over workflow
* adaptation over rigid sequence
* strategy generation over immediate answer generation
* cheap information gain before expensive synthesis
* reflection that changes future behavior
* strong-model flexibility with minimal guardrails

In short:

**strategy first, then evidence, then adaptation**

---

## Example Use Cases

* research agents
* technical analysis agents
* architecture exploration
* long-horizon planning assistants
* insight generation pipelines
* roadmap synthesis support

---

## Future Extensions

Possible future additions:

* short-form variant of the policy
* stronger R&D-oriented variant
* domain-specific overlays
* evaluation heuristics
* examples of integration with agent runtimes

---

## Status

Early draft / lightweight release.

This repository is intentionally small.
The goal is to provide a practical base policy that can be dropped into real agent systems with minimal ceremony.

---

## Reference

```bibtex
@article{szot2026sge,
  title={Expanding LLM Agent Boundaries with Strategy-Guided Exploration},
  author={Szot, Andrew and Kirchhof, Michael and Attia, Omar and Toshev, Alexander},
  journal={arXiv preprint arXiv:2603.02045},
  year={2026}
}
```

---

## License

MIT
