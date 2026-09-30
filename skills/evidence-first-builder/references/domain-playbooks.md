# Domain Playbooks

Load only the relevant section.

## Software and code

Inspect:
- official docs and source repository;
- releases/changelog and supported runtime versions;
- issue/PR activity and maintainer responsiveness;
- tests/CI and example coverage;
- security advisories and dependency quality;
- license and redistribution terms;
- migration/rollback path.

Prefer a maintained library or platform-native mechanism over custom infrastructure when it satisfies the requirement.

## AI models, ComfyUI, plugins, and workflows

Inspect:
- official model card/repository and exact model variant;
- recent release date and required runtime versions;
- workflow JSON or reproducible graph when available;
- exact custom nodes/plugins and whether they are maintained;
- model files, quantization type, precision, and download source;
- target GPU VRAM/RAM/storage reports and tested resolution/duration/batch settings;
- fallback/offload/low-VRAM behavior;
- licenses and model-use restrictions;
- recent community runs on comparable hardware;
- known broken nodes, version pinning, and migration notes.

Do not infer 16 GB compatibility merely from parameter count or a marketing memory figure. Prefer actual runs or explicit memory calculations tied to the exact workflow.

Treat unknown custom nodes, unsigned binaries, shell installers, and executable extensions as a security review point.

## Apps and SaaS

Inspect:
- official feature support and platform availability;
- current pricing/limits and hidden usage caps when decision-relevant;
- data retention, model training/data-use terms, telemetry, account requirements;
- export, interoperability, lock-in, deletion, and self-hosting options;
- independent reliability/support reports;
- open-source/self-hosted or cheaper alternatives.

Compare total ownership cost, not sticker price alone.

## Hardware

Use official specifications for limits and independent measurements for real behavior.

Check:
- exact model/revision;
- power/thermals/noise where relevant;
- driver/firmware/runtime compatibility;
- application-specific benchmarks;
- memory capacity and bandwidth constraints;
- independent testing methodology.

Do not convert peak theoretical throughput into expected application performance.

## Automation, agents, MCP, and device control

Inspect:
- native APIs and first-party automation surfaces first;
- existing mature connectors/servers/bridges;
- permission model and credential storage;
- destructive-action boundaries and confirmation behavior;
- recovery, idempotency, retries, audit logs, and emergency stop;
- observability and live acceptance criteria;
- whether browser/UI automation is actually necessary or a stable API exists.

Prefer semantic/native control over brittle coordinate automation when available.

## High-stakes domains

For finance, legal, medical, security-sensitive, or other high-impact decisions, prioritize current authoritative evidence and domain-specific safety rules. Do not let the reuse-first heuristic override high-stakes requirements. Separate factual evidence, uncertainty, and user preference clearly.
