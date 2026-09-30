# Agent Engineering Skills

Small, reusable workflow Skills for AI agents that should research before inventing, reuse before rebuilding, and preserve the user's actual goal when multiple workflows overlap.

## Included Skills

### Evidence First Builder

A research-first, reuse-first, verify-first workflow for recommendations, architecture, coding, setup, troubleshooting, automation, model and workflow selection, and implementation.

It emphasizes:

- inspecting the user's real environment first;
- current primary evidence plus practical reality checks;
- serious existing solutions before custom work;
- explicit security, privacy, licensing, lock-in, and commercial-bias checks;
- observable verification instead of treating command success as feature success.

### Reuse First

A lightweight decision gate:

`REUSE -> ADAPT -> COMBINE -> BUILD`

Custom building is the last option, not the default. A BUILD decision requires a short Build Justification explaining what was checked and why reuse, adaptation, or composition was insufficient.

### Task Skill Conflict Gate

A pre-execution goal and skill-composition gate. It:

- locks the requested outcome and constraints;
- considers only skills that can materially affect the task;
- composes compatible skills silently;
- asks one concise question only when a genuine user-resolvable conflict would change scope, permissions, data handling, or acceptance criteria;
- never asks the user to override mandatory platform, safety, authorization, or tool boundaries.

## Why

AI coding and automation agents can waste time and maintenance budget by immediately inventing a new subsystem, over-reading context, or letting ambient workflow instructions redirect the user's real goal.

These Skills are deliberately small control-plane instructions. They are intended to improve agent decisions without becoming a heavyweight agent framework.

## Suggested composition

```text
Task Skill Conflict Gate
        |
        v
   Reuse First
        |
        v
Evidence First Builder
        |
        v
Domain-specific execution
        |
        v
Observable verification
```

The three Skills do not need to run for every trivial task. Use the lightest workflow that materially improves the result.

## Installation

Each folder under `skills/` is a standalone Skill containing `SKILL.md` and `agents/openai.yaml` plus only the references or assets it needs.

Clone or download the repository and import the individual skill folder using the Skill workflow supported by your agent host. The instruction format is designed for ChatGPT/Codex-style Skills and can also be adapted to other agent systems.

All three skill folders were checked with the official Skill validator before publication.

## Design principles

- Goal before workflow.
- Search before build.
- Reuse before rewrite.
- Smallest sufficient change.
- Real acceptance evidence over command success.
- User authority and existing safety boundaries stay intact.
- Avoid commercial, popularity, and star-count bias.
- Keep instruction bundles concise enough to compose.

## License

MIT. See `LICENSE`.

## Status

Experimental but actively used. Compatibility and available tool surfaces vary by agent host, so treat host-specific metadata as an adapter layer rather than part of the core method.
