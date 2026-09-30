---
name: task-skill-conflict-gate
description: Pre-execution goal and skill-conflict gate for non-trivial tasks where multiple skills, workflow rules, tools, or execution modes may materially change scope, permissions, data handling, output, verification depth, or success criteria. Use before substantive execution when two or more plausible skills can conflict or when a skill could redirect an explicit user goal. Normalize the task goal, inspect only plausibly relevant skills, classify material conflicts, and ask one concise clarification only for genuine user-resolvable conflicts. Proceed silently for compatible or additive skills, and never ask users to override higher-priority platform or safety constraints.
---

# Task Skill Conflict Gate

Preserve the user's actual goal while composing multiple skills. Do not turn skill selection into bureaucracy.

## 1. Lock the goal before execution

Create a compact internal Goal Capsule:

- desired outcome;
- concrete deliverable or action;
- explicit constraints and no-go rules;
- mutation authority: advise, read-only, or allowed to change state;
- important privacy, locality, cost, or time constraints;
- observable acceptance condition.

Use current user instructions and available context. Do not ask for facts that tools or existing context can resolve safely.

## 2. Shortlist only relevant skills

Consider only skills that plausibly affect the current task. Do not load or compare the entire skill catalog.

Prefer metadata first. Read full skill instructions only when the skill is a serious candidate or its constraints may matter.

## 3. Test for a material conflict

A conflict is material only when choosing one path over another would meaningfully change one or more of:

- the user's intended outcome or scope;
- whether files, accounts, devices, or external state are changed;
- permission or approval requirements;
- privacy, data exposure, or local-versus-cloud behavior;
- implementation strategy or dependency boundary;
- required verification or acceptance threshold;
- irreversible or destructive behavior;
- output format when that format is part of the requested deliverable;
- meaningful cost, latency, or resource consumption.

Typical conflict classes:

- `GOAL`: a skill redirects or broadens the requested task.
- `MODE`: read-only analysis conflicts with execution or mutation.
- `PERMISSION`: a skill expects authority the user did not grant.
- `PRIVACY`: one workflow exports data while another requires local handling.
- `SCOPE`: one skill demands a broad rewrite while another constrains work to a patch.
- `VERIFICATION`: incompatible acceptance bars would materially change work or time.
- `OWNERSHIP`: two agents or skills both require writable ownership of overlapping state.

## 4. Do not treat normal composition as conflict

Proceed without asking when:

- skills are additive or operate at different layers;
- a specific domain skill owns execution while a general skill adds research, reuse, verification, or context discipline;
- the user's current explicit instruction already resolves the difference;
- one interpretation is clearly required by a more specific task constraint;
- the difference is merely stylistic and does not affect the deliverable;
- a higher-priority platform, safety, authorization, or connector boundary already decides the issue.

Never ask the user to waive or override a non-negotiable higher-priority safety or authorization boundary.

## 5. Resolve conflicts in this order

1. Obey higher-priority platform, safety, authorization, and tool constraints.
2. Preserve the user's current explicit goal and constraints.
3. Prefer the most specific domain skill for domain behavior.
4. Compose compatible meta-workflow skills around that domain owner.
5. If two same-level choices still conflict and the user's preference is genuinely unknown, ask once before the conflicting action.

Do not let an ambient skill silently override a clear user instruction.

## 6. Ask only a decision-changing question

When clarification is necessary, keep it concise and concrete:

`Goal: <one sentence>. Conflict: <skill or workflow A> would <effect>, while <skill or workflow B> would <different effect>. Which should govern: A, B, or a bounded hybrid?`

Offer only choices that are actually feasible. Explain the consequence of each choice in a few words when useful.

Do not ask generic questions such as "How would you like to proceed?" when the real conflict can be named precisely.

## 7. Preserve capability

Apply a restrictive skill only to the scope it owns. Do not globally disable tools, connectors, other skills, or execution capability merely to avoid a local conflict.

When a skill is skipped because it conflicts with the user's goal, skip only the conflicting behavior. Reuse compatible parts when they still add value.

## 8. Silent proceed behavior

If no material conflict remains, proceed with the task. Do not expose the Goal Capsule or a skill-routing report unless it helps the user or they ask for it.

## Examples

### Compatible: no question

The task needs current research and implementation. `evidence-first-builder` supplies evidence and verification; `reuse-first` chooses reuse versus build. Compose both and continue.

### User already resolved it: no question

The user says, "Review this repository but do not modify anything." An execution-oriented skill is also available. Preserve the explicit read-only constraint and do not mutate; no clarification is needed.

### Real conflict: ask once

A security-review workflow is read-only, while an auto-remediation workflow would edit production configuration. The user asked only for "a security audit" and did not authorize changes. Ask whether they want audit-only or audit-plus-remediation before any mutation.

### Higher-priority boundary: do not negotiate

A workflow wants to bypass an existing approval gate to finish faster. The gate is mandatory. Keep the gate and continue within it; do not ask the user to override the boundary.
