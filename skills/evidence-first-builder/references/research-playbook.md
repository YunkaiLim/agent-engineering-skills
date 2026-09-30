# Research Playbook

## Goal

Find enough independent evidence to make a good decision without turning every task into a literature review.

## Search sequence

1. Resolve the exact product/project/model/plugin identity and current version.
2. Find the primary technical source.
3. Find the strongest reusable implementation(s).
4. Find one or more reality checks: issues, discussions, benchmark methodology, migration reports, real hardware runs, or reproducible examples.
5. Search specifically for failure modes, regressions, privacy/security concerns, and compatibility problems.
6. Stop when additional sources are repeating known facts rather than changing the decision.

## Search stopping rules

Stop when all are true:
- the top candidate(s) are identified;
- decisive compatibility facts are verified;
- major risks/limitations are known;
- at least one independent reality check exists when reasonably available;
- additional results are mostly duplicate claims.

Continue research when:
- primary and community evidence conflict;
- compatibility depends on a recent release;
- the decision has meaningful cost, privacy, security, or lock-in impact;
- the candidate requires obscure or untrusted dependencies;
- the source set is dominated by promotion or SEO.

## Source independence

Several pages are not several independent sources when they all repeat the same upstream claim.

Trace important claims back to their origin when possible. Treat these as one evidence chain if they share the same source:
- vendor press release -> news rewrite -> comparison blog;
- README benchmark -> influencer chart -> forum repost;
- marketplace description -> affiliate review -> SEO listicle.

Prefer disagreement that reveals real tradeoffs over artificial consensus.

## Freshness

For rapidly changing topics, note the date/version context mentally before comparing:
- software and APIs;
- AI models and quantizations;
- custom nodes/plugins/workflows;
- pricing and usage limits;
- GPU/driver/runtime compatibility.

Do not reject older evidence automatically if it tests a stable property, but do not use it to prove current compatibility without checking.
