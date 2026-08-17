---
description: Local reasoning agent via Ollama. Placeholder — the model is chosen per machine by the supervisor's local-model evaluation; configure after setup.
mode: subagent
model: ollama/deepseek-r1:32b
steps: 14
permission:
  task:
    "*": allow
  edit: allow
  bash: allow
  railway_*: allow
---

Placeholder — configure your local Ollama model before use. Model choice depends on this machine: the supervisor evaluates the hardware and pulls an appropriate model (see the supervisor's Local Model Selection section).
