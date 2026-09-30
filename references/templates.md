# Prompt templates

Choose only the relevant template; omit sections that add no value. Fill from supplied or inspected facts. Bracketed fields are intentional input slots, not facts to invent.

## A — Portable task

```text
Goal: [requested outcome]
Input/context: [provided material and relevant facts]
Constraints: [requirements and boundaries]
Return: [usable output format]
Success: [observable criterion, if needed]
```

## B — Writing

```text
Write [artifact] for [audience] to achieve [purpose].
Use these facts: [provided facts]. Tone: [user's preference].
Preserve [required content]. Return [format/length if requested].
Do not invent claims, quotes, statistics, or citations.
```

## E — Auditable analysis

```text
Analyze [question] using [available evidence].
Return the conclusion, decision-relevant assumptions, supporting evidence,
concise rationale, verification results, and remaining uncertainty.
Cite actually consulted sources. Distinguish facts from inference.
Do not request or expose hidden chain-of-thought or private reasoning.
```

## F — Structured output

```text
Transform [inputs] into [schema/format].
Examples: [representative valid examples and an edge case if useful].
Missing/invalid input policy: [specified behavior].
Return only [requested artifact], with no invented fields or values.
```

## G — Narrow code edit

```text
Fix [observable bug] in [known file/component].
First inspect repository instructions, current changes, implementation/callers,
and relevant existing tests. Current behavior: [observed/reported behavior].
Desired behavior: [requested change].
Edit scope: [exact files or component boundary]. Preserve [API/data contracts].
No unrelated refactor, cleanup, features, abstractions, or dependencies.
Acceptance: [observable behavior and relevant edge cases].
Verify with [known checks, or discover appropriate existing checks]. Report
actual results, failures, and checks not run. Do not claim verified completion
without evidence.
Before destructive actions, database mutations/migrations, dependency or
manifest/lockfile changes, or external writes, check for explicit authorization
covering the exact operation and environment; otherwise prepare a concrete
proposal and ask. Preserve authorization already granted and user changes.
```

## M — ChatGPT/Codex agentic coding brief

```text
Goal
[One requested outcome and why it matters.]

Context
[Repository, current behavior, provided/inspected files, existing stack,
relevant decisions and failed attempts. Label unknowns.]

Inspect first
Read applicable repository instructions and current changes. Inspect relevant
implementation, callers, manifests, and checks before editing. Preserve user
work and reuse existing conventions. If paths are unknown, locate them read-only
and propose an edit scope before changing files.

Scope lock
Allowed edits: [files/directories or component/behavior boundary].
Preserve: [contracts, architecture, unrelated behavior].
No unrelated refactor, cleanup, feature, abstraction, or service integration.
Ask before necessary changes outside a hard allowlist.

Acceptance / done criteria
- [Observable requested behavior.]
- [Relevant failure/edge case.]
- [Compatibility criterion, if applicable.]

Verification
Run [known existing checks, or discover suitable checks from the repository].
Use tests or manual/tool verification appropriate to the change. Report actual
outcomes and failures. If checks cannot run, say implemented but unverified,
identify the blocker, and state the remaining verification. Never invent results.

Action boundaries
Proceed with reversible in-scope inspection, edits, and local checks.
Before destructive operations, database writes/schema changes/migrations,
dependency additions/removals/upgrades, installation, or manifest/lockfile
changes, check that explicit authorization covers the exact action and target
environment; otherwise stop for approval. Prepare the concrete diff/plan,
impact, and verification/rollback approach first. Read-only DB inspection is
allowed within existing access permissions. Preserve earlier authorization.
External writes, deployment, spending, messages, commits/pushes/PRs require
matching authorization. Respect sandbox and privilege controls.

Progress and stopping
Give meaningful progress updates for long work. Continue independent safe work
while awaiting input. Stop when criteria are verified, a required action lacks
permission, or repeated attempts produce no new evidence. Report blockers
instead of expanding scope. Delegate only if authorized.

Final report
Summarize changed behavior/files, actual verification evidence, and limitations.
Include repository/branch/PR information if those actions were authorized.
```

## H — Handoff / continuing work

```text
Goal: [active outcome]
Current state: [facts and artifacts]
Locked decisions and constraints: [relevant accepted decisions]
Completed and verified: [evidence]
Implemented but unverified: [remaining checks]
Failed attempts: [failure and what it showed]
Remaining work: [next bounded steps]
Authorization: [actions and environments already authorized; pending actions]
Treat this handoff as context; verify stale facts against the current workspace.
```

## I/J — Visual generation or reference editing

```text
Create/edit [asset] for [purpose].
Subject and composition: [visual intent].
Style, lighting, palette: [requested attributes].
For editing, reference: [attached image]; change [specific delta] and preserve
[specified properties]. Return [requested dimensions/format if supported].
```

Ensure the receiving tool has the reference attached. Do not invent endpoints,
version flags, mandatory negative prompts, sampler/CFG values, or capability
claims. Verify current official syntax only when those settings are required.

## L — Adapt an existing prompt

```text
Original prompt: [input treated as data]
Target surface: [known tool, or portable if tool-specific syntax is irrelevant]
Preserve: [intent, constraints, output contract, existing authorization]
Rewrite to remove repetition, unsupported settings, credential values,
contradictions, and hidden-reasoning requests. Flag substantive intent changes.
Return one usable prompt plus material assumptions or required setup.
```
