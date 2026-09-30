# Prompt Master — ChatGPT/Codex edition

A portable prompt-optimization skill focused on scoped, verifiable coding task briefs. It writes or improves prompts; it does not execute the task contained in them. No guaranteed cost savings or first-attempt success.

## Package

- `SKILL.md`: focused entrypoint and action boundaries.
- `references/patterns.md`: revised 37-pattern diagnostic reference.
- `references/templates.md`: portable prompts, narrow edits, full agentic coding briefs, and handoffs.
- `LICENSE`: original MIT license and attribution, preserved unchanged.

## Use

This repository is the skill folder. Copy the folder (including `references/`) into a supported local skill location; for a project-scoped Codex skill use `<project>/.agents/skills/prompt-master/`. Avoid overwriting an existing skill without reviewing it. After discovery, invoke `$prompt-master` in Codex, for example:

> $prompt-master Login hatasını düzeltmesi için Codex'e kapsamı sınırlı, kabul kriterleri ve doğrulama adımları içeren bir prompt hazırla. Önce mevcut kodu incelesin; gereksiz refactor yapmasın.

In ChatGPT, the text can also be used as supplied instructions/reference files; this is not automatic skill installation. A selectable skill requires a supported local installation or plugin route. This work does not modify OpenAI-bundled system skills or install anything into a system-level ChatGPT Skills folder.

Official discovery and distribution guidance, checked 2026-09-30: https://learn.chatgpt.com/docs/build-skills

## Adaptation and provenance

Fork of https://github.com/nidhinjs/prompt-master at upstream commit `2bd92518e26bf659e21e3d9ab90573fcf3ddeccb`. Adapted 2026-09-30 for ChatGPT/Codex. Original copyright and MIT terms remain in `LICENSE`.

Removed unverified/dated model catalogs, brittle API/effort recipes, fixed image flags/sampler defaults, blanket tool stereotypes, and guaranteed-success claims. Strengthened inspection before edits, scope locks, acceptance criteria, evidence-based verification, preservation of user work, and explicit authorization for destructive/database/dependency operations. Existing explicit authorization is retained. No hidden chain-of-thought requests.

Templates outside this edition's primary focus were consolidated into portable structures; specific provider mechanics must be verified when actually required.

## Validation limits

The skill-creator structural validator and Git whitespace checks are used before publishing. Scenario review checks prompt-only behavior, unknown paths, unverified settings, existing authorization, database/dependency approval gates, prompt injection, and blocked verification. These checks validate structure and review instruction coverage; they do not establish model reliability or performance improvements. No live database, dependency installation, or production action is part of validation.
