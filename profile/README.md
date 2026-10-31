# platform-upstream

Shared code for two personal platforms built on the same base: **castillo** (Joachim) and
**niiku** (Nik). One artifact, two installations: everything here is free of platform names; each
platform supplies its own values (domain, Cloudflare Access team, registry, secret paths) from its
own config repositories (`castillo-platform/*`, `niiku-platform/*`).

## Rules

1. **No platform names in shared code** (org, domain, team, registry, secret path). Examples use
   `example.org` / `acme`. Platform values come from env, chart values or the platform profile.
2. **SemVer tags; consumers pin exact versions**, Renovate proposes bumps. A breaking change is a
   new major that both owners agree on first.
3. **Differences are feature flags with default off**, not forks.
4. Small green commits to `main`; each repo's `AGENTS.md` says how to check.

## Repositories

| Repo | What | Consumed as |
|---|---|---|
| [app-foundation](https://github.com/platform-upstream/app-foundation) | Go primitives (Access, SQLite, web/PWA, llm, push, memory, agentkit), frontend registry, app scaffold | Go module `github.com/platform-upstream/app-foundation`, vendored |

Roadmap and decisions: private repo `handbook`.
