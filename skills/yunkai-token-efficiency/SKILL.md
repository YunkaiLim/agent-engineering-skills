---
name: yunkai-token-efficiency
description: Context- and token-efficiency control for large coding tasks, long-running projects, multi-agent workflows, repository analysis, large logs, handoffs, repeated verification, and abnormal agent usage. Use when ChatGPT should minimize repeated reading, duplicated research, oversized prompts, full-history handoffs, or redundant agent work without reducing delivery quality. Default to targeted retrieval, compact Task Capsules, execution, diff/decision/targeted evidence return, and incremental memory writeback. Prefer conclusions, constraints, source identifiers, blockers, and acceptance criteria over research diaries. Deduplicate overlapping agent investigations by assigning one owner and bounded review. Optimize Useful Work per Million Tokens, not token volume, and avoid creating heavy telemetry merely to measure efficiency.
---

# Yunkai Token Efficiency

Optimize for **Useful Work per Million Tokens**, not for token volume or visible activity.

## Default flow

Use:

`knowledge/repo -> targeted retrieval -> compact Task Capsule -> agent execution -> diff + decisions + targeted evidence -> incremental memory writeback`

Do not default to replaying full project history.

## Task Capsule

Include only what materially changes execution:

- current goal;
- necessary architecture context;
- directly relevant files or source identifiers;
- explicit constraints;
- acceptance criteria;
- known failure evidence;
- required interface or protocol details.

Do not automatically resend the full project history, every handoff, entire repository tree, full build log, full UIA tree, or another agent's complete research/thought process.

## Compress tool and test output

Prefer:

- failed count;
- relevant error;
- stack or failing location;
- affected files;
- changed behavior;
- diff summary or patch identifiers;
- acceptance evidence.

Load full raw output only when the compressed evidence is insufficient.

## Handoff rule

Pass:

`conclusions + constraints + source identifiers + blockers + acceptance criteria`

Do not pass the full research diary by default.

## Duplicate-work control

If two agents are investigating the same question, select one owner. Stop or redirect the duplicate path and use the second agent only for a bounded independent review when that adds value.

## Efficiency signals

Track only when useful:

- accepted tasks per 1M tokens;
- first-pass success rate;
- rework count;
- repeated-context ratio;
- average Task Capsule size;
- unnecessary full-test count;
- duplicate research count;
- context loaded versus context actually used.

Do not build elaborate telemetry solely to optimize these metrics.

## Composition

- `yunkai-reuse-first` reduces duplicated implementation.
- `yunkai-delivery-first` reduces over-testing and over-splitting.
- Domain skills own domain execution.
- This skill continuously constrains retrieval, prompts, evidence, and handoffs without duplicating their workflows.
