---
name: reuse-first
description: Reuse-first decision gate for non-trivial software, AI, automation, infrastructure, tooling, and game-development work. Use before designing or implementing a new component when an existing project implementation, official feature, SDK, starter, mature open-source project, Skill, Plugin, MCP server, connector, package, library, framework, or community-proven workflow might already solve the need. Force the decision order REUSE, then ADAPT, then COMBINE, then BUILD; evaluate licensing, maintenance, version compatibility, privacy and security, cloud-upload requirements, integration cost, fork burden, and adapter boundaries; and require a brief Build Justification before custom implementation.
---

# Reuse First

Prevent unnecessary reinvention. Apply this decision order:

`REUSE -> ADAPT -> COMBINE -> BUILD`

## Search order

Check only as deeply as the task warrants:

1. Existing implementation in the current project.
2. Official feature, SDK, starter, or supported extension point.
3. Mature open-source project.
4. Existing Skill, Plugin, MCP server, connector, or equivalent integration.
5. Mature package, library, or framework.
6. Community-validated workflow or template.

## Candidate gate

Before adoption, check the material factors:

- license and whether the intended use is allowed;
- maintenance status and current-version compatibility;
- security and privacy implications;
- whether data must be uploaded to a cloud service;
- integration complexity and operational burden;
- expected long-term fork or patch maintenance;
- whether an Adapter, Provider, or Bridge can isolate the dependency.

Do not adopt merely because a project has many stars. Do not copy code beyond license permissions. Do not replace a stable existing module solely because a newer alternative exists.

## Decision rules

- Prefer `REUSE` when an existing solution fits without meaningful behavior change.
- Prefer `ADAPT` when a thin compatibility layer is enough.
- Prefer `COMBINE` when a few proven components cover distinct requirements with less custom logic than a new subsystem.
- Choose `BUILD` only when the prior options fail the real requirements or would be more complex than a bounded custom implementation.
- Treat sunk cost as irrelevant to the decision.

If choosing `BUILD`, produce a short Build Justification containing:

- what was checked;
- why REUSE, ADAPT, and COMBINE were insufficient;
- why the proposed build is the smallest and simplest viable option.

## Reuse Packet

Pass downstream agents only a compact packet:

- chosen solution;
- source;
- version;
- license;
- `REUSE | ADAPT | COMBINE | BUILD` decision;
- integration boundary;
- acceptance criteria.

Do not forward the full research diary unless specifically needed.

## Composition

If a task or skill-conflict gate is active, resolve the user's goal and any material workflow conflict first. Then run this decision gate before design or implementation.

Let domain-specific skills own domain execution. Let delivery or scope-control skills govern execution budget, and let context or token-efficiency skills constrain handoffs. Do not duplicate their work.
