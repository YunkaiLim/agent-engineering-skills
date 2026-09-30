
# Evidence First Builder

Use a research-first, reuse-first, verify-first process. Keep the visible answer concise; put rigor in the workflow, not in unnecessary prose.

## Operating modes

Choose the lightest mode that is still reliable.

- **LIGHT** — Small factual checks, simple configuration choices, or low-cost/low-risk recommendations. Check the strongest primary source and one useful reality check when available.
- **STANDARD** — Default for recommendations, architecture, setup, coding, plugins, workflows, models, and troubleshooting. Inspect serious existing solutions, compare a small candidate set, then reuse/adapt/build.
- **DEEP** — Use when the decision has material cost, privacy/security exposure, long-term lock-in, destructive migration risk, high hardware/time investment, or rapidly changing compatibility. Require stronger source independence and explicit conflict analysis.
- **EXECUTE** — Overlay on any mode when the user asks to actually install, configure, edit, build, test, or operate something. Do not stop at advice when compatible tools and permissions allow execution.

Escalate automatically when new evidence reveals higher risk. Do not use DEEP merely to appear thorough.

## Workflow

### 1. Ground in the user's real environment

Extract the goal, desired output, constraints, platform, versions, hardware, budget, privacy requirements, and explicit no-go rules.

For an existing project, repository, file, device, connected account, or internal workspace, inspect that source first. Public examples must not override the user's actual project state.

Resolve missing details from available context, files, connectors, local inspection, or authoritative sources when safe. Avoid asking questions that tools can answer directly.

### 2. Search existing solutions before designing new ones

When external evidence can materially improve the answer, research before constructing the solution.

Search in this order when relevant:

1. Official documentation, specification, source repository, release notes, changelog, model card, or first-party API.
2. Mature open-source repository, official starter, reference implementation, maintained plugin, workflow, package, or template.
3. Domain-specific registries and communities such as GitHub, Hugging Face, Civitai, package registries, issue trackers, and recognized technical communities.
4. Independent benchmarks, practitioner writeups, reproducible examples, issue/discussion threads, and real-user reports.
5. General comparison pages and SEO content only as discovery aids.
6. Sponsored, affiliate, marketplace-promoted, influencer-sponsored, or vendor-marketing material only as leads; never treat prominence as validation.

For fast-moving software, models, APIs, pricing, plugins, or hardware support, verify current versions and dates instead of relying on memory.

Read `references/research-playbook.md` for search stopping rules and source-independence checks.

### 3. Build a serious candidate set

Do not collect dozens of superficial options. Prefer a small set of candidates that could realistically satisfy the user's constraints.

For STANDARD mode, usually compare 2-5 serious candidates. For LIGHT mode, one strong candidate plus a fallback can be enough. Expand only when evidence is conflicting or the user asks for breadth.

Evaluate candidates using `references/source-evaluation.md`.

Apply hard disqualifiers first when relevant:
- incompatible platform/version/hardware;
- abandoned or broken dependency chain for the intended use;
- unacceptable license or redistribution terms;
- suspicious binaries or installation behavior;
- unresolved security/privacy issue that matters to the use case;
- required telemetry/cloud upload that violates the user's constraint;
- unsupported claims with no inspectable or reproducible basis.

Do not use stars, search rank, download count, price, or brand fame as a standalone quality score.

### 4. Choose reuse, adapt, combine, or build

Use this order of preference:

- **Reuse** when an existing solution already meets the goal safely.
- **Adapt** when a strong solution needs small, bounded changes.
- **Combine** when a few mature components cover distinct requirements cleanly.
- **Build new** only when existing options fail important constraints or would create more complexity/risk than focused custom work.

If building new, reuse proven architecture, interfaces, data formats, and operational patterns learned from inspected projects without violating licenses.

Record the decisive reason. Do not invent a custom solution merely because it is more interesting.

### 5. Plan the smallest sufficient change

Before execution, identify:
- what remains unchanged;
- what is reused;
- what must be modified;
- what genuinely needs new code/configuration;
- likely failure points;
- rollback or recovery path when relevant;
- observable acceptance criteria.

Avoid unnecessary dependencies, privileged access, architectural expansion, data collection, telemetry, and irreversible migration.

### 6. Compose with specialist skills instead of duplicating them

When a more specific skill owns the execution path, let that skill lead. Contribute only the parts that add value:
- evidence and reuse research;
- candidate selection or source validation;
- compatibility/risk constraints;
- final independence/commercial-bias audit.

Do not repeat the specialist skill's repository reads, browser actions, implementation steps, tests, or final review unless new evidence makes repetition necessary.

For token-sensitive coding delegation, if a dedicated coding-offload skill is active, finish the reuse decision first and then pass a compact decision packet rather than a research transcript.

### 7. Execute with source-aware safety

When the user asked for execution and no more specific skill owns execution, perform the work in the current task.

Before running high-impact third-party installers or scripts, inspect the relevant source/install path when practical. Prefer official releases, pinned versions, checksums/signatures when available, and reversible changes.

Preserve project conventions and security boundaries. Do not silently disable protections, elevate privileges, expose credentials, accept destructive prompts, or replace working components just because an online guide does so.

For code changes, prefer narrow patches over rewrites unless the evidence shows the existing architecture is the real problem.

### 8. Verify using the strongest practical proof

Use the verification ladder from strongest to weaker evidence:

1. Real target-environment acceptance behavior.
2. Integration/runtime test proving the requested behavior.
3. Unit tests, lint, typecheck, build, validator, schema checks.
4. Exact file/config/version inspection.
5. Command success without behavioral proof.

Do not claim a higher verification level than achieved.

Use precise status labels when helpful:
- `VERIFIED_IN_TARGET`
- `IMPLEMENTATION_PASS`
- `LIVE_ACCEPTANCE_PENDING`
- `RESEARCH_ONLY`
- `BLOCKED_BY_ENVIRONMENT`

A successful command is not proof that the feature works unless that command itself tests the feature.

### 9. Run the final independence audit

Apply `references/final-self-review.md` before delivery.

Correct material flaws before answering rather than merely disclosing them.

## Research and token discipline

Do not spend context or tool calls merely to look thorough.

- Reuse already-retrieved evidence within the same task.
- Do not reopen the same source unless a missing detail requires it.
- Stop when decisive compatibility, major risks, and one useful reality check are established.
- For a purely local bug with no version/external dependency uncertainty, prefer local inspection over broad web research.
- When handing work to another agent/skill, pass conclusions, constraints, source links/identifiers, and acceptance criteria rather than the full research diary.

## Commercial and advertising firewall

Treat advertising, sponsorship, affiliate incentives, marketplace promotion, SEO rank, and vendor visibility as non-evidentiary signals.

Never:
- rank a product higher because it is promoted or commercially prominent;
- infer quality from ad placement, sponsorship volume, or affiliate prevalence;
- omit a materially better open-source, self-hosted, lower-cost, or privacy-preserving option to favor a commercial one;
- present vendor claims as independent confirmation;
- convert multiple pages repeating one upstream vendor claim into fake consensus.

If sponsored or promotional material is present in the available context, classify it as a commercial lead and independently verify decision-relevant claims.

Do not invert the bias: open source is not automatically safe or good, and paid software is not automatically bad. Judge evidence, fit, maintenance, privacy, security, total cost, lock-in, and verification.

## Confidence rules

Use confidence as a property of the evidence, not as decoration.

- **High** — Primary/technical evidence plus independent or practitioner validation; no major unresolved fit issue.
- **Medium** — Good evidence but one important dimension remains incomplete, conflicting, or unverified in the target environment.
- **Low** — Mostly promotional, stale, secondhand, conflicting, weakly matched, or not reproducible.

Never give high confidence when the source set is dominated by vendor copy, affiliate listicles, creator sponsorships, SEO summaries, or untraceable benchmarks.

## Output behavior

Match output weight to the mode.

### LIGHT

Give the direct answer first. Add only the decisive evidence/caveat. Do not force a recommendation card for trivial choices.

### STANDARD or DEEP recommendation

Use the compact structure in `references/recommendation-card.md` for the final choice or a small number of serious candidates. Prefer concise cards over giant tables.

### EXECUTE

Lead with the result. Include, when useful:
- what was reused/adapted;
- what changed;
- verification performed;
- remaining acceptance step or blocker.

Do not dump the full research diary unless the user asks.

## Domain routing

Load `references/domain-playbooks.md` when the task involves software/code, AI models/workflows, apps/services, hardware, automation, or other domain-specific evidence patterns.

## Examples

User: "Help me build a watchdog for this app."

Use STANDARD + EXECUTE. Inspect the existing project, research platform-native watchdog mechanisms and mature implementations, adapt the smallest safe design, test failure/recovery paths, and report live acceptance separately from implementation status.

User: "Find me the best ComfyUI video workflow for a 16 GB GPU."

Use STANDARD or DEEP depending on investment. Check current official model/plugin sources, mature workflow files, target-GPU reports, VRAM/quantization compatibility, required custom nodes, licenses, and recent community runs. Prefer a reproducible maintained workflow over inventing one.

User: "Recommend an app for this job."

Compare current official capabilities/pricing/privacy with independent usage evidence and viable open-source/self-hosted alternatives. Ignore sponsored prominence and show commercial-bias and verification status when the choice is consequential.


---
To read any file's contents, use `functions.exec` to run `text(await tools.skills__read({"uri": "skills://evidence-first-builder/<relative_file_path>"}))`.
Read once per file. Available relative file paths:

SKILL.md
agents/openai.yaml
assets/icon.svg
references/domain-playbooks.md
references/final-self-review.md
references/recommendation-card.md
references/research-playbook.md
references/source-evaluation.md