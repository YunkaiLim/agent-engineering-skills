---
name: yunkai-delivery-first
description: Delivery-first execution control for software, AI, automation, tooling, infrastructure, and game-development work. Use when a task risks over-testing, over-splitting, over-refactoring, scope creep, repeated acceptance loops, or architecture cleanup that delays a usable result. Prefer one bounded work packet that can implement, integrate, minimally verify, and make the feature directly usable. Apply tiered verification budgets, keep one primary writable owner per overlapping scope, record non-blocking discoveries as follow-ups, favor patch/adapter/bounded refactor over broad rewrites, and protect existing human gates, permissions, kill switches, and safe modes. The success metric is usable functionality and workbench progress, not code, test, or refactor volume.
---

# Yunkai Delivery First

Optimize for the fastest path to a directly usable result without weakening existing safety boundaries.

## Work packet

When one capable agent can reliably finish the work end-to-end, prefer one bounded packet covering:

`implement -> integrate -> minimum verification -> usable result`

Every packet must state:

- Goal
- Writable scope
- Do now
- Do not expand
- Verification budget
- Acceptance condition

Keep one primary writable owner for overlapping scope.

## Scope control

- If a newly discovered issue does not block the current goal, record `FOLLOW_UP` and continue.
- If it truly blocks the current goal, include only the minimum necessary fix.
- Prefer patch, adapter, or bounded refactor when the existing structure is stable.
- Do not refactor adjacent systems merely for cleanliness.
- Do not split a task into many phases when a single agent can safely finish it in one pass.

## Verification budget

Use the lowest level that can establish acceptance:

- **L1 - Direct**: verify only the modified behavior.
- **L2 - Targeted integration**: use when the change crosses a component boundary.
- **L3 - Full regression**: use only for shared foundations, major schema/protocol/public-interface changes, release gates, explicit regression evidence, or explicit user request.

After acceptance evidence is sufficient, stop. Do not rerun large suites merely for reassurance.

## Context budget

Prefer the relevant files, failing stack, diff, targeted logs, and compact Task Capsule. Do not re-read the full repository, all historical handoffs, or full logs unless they are actually required.

## Safety floor

Optional new hardening/audit/policy work may be deferred when it would block core delivery, but never:

- disable, bypass, or weaken an existing Human Gate;
- cross an existing permission boundary;
- disable an existing Kill Switch or Safe Mode;
- broaden permissions merely to make a test pass.

## Completion rule

Measure success by how quickly the core feature becomes directly usable with enough evidence to trust the change. Treat extra tests, code volume, and refactoring as costs unless they materially improve that outcome.

## Composition

Let `yunkai-reuse-first` decide whether to reuse/adapt/combine/build. Let domain-specific skills own domain execution. Let `yunkai-token-efficiency` reduce context and handoff waste throughout.
