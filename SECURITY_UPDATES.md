2025-10-24 — Dependency security updates

Actions performed:

- Upgraded `astro` to a patched release (>=5.14.3). Current installed: 5.15.1
- Updated `vite` transitively to a patched release (>=6.4.1)
- Upgraded `fastify` and `pino` to newer releases; transitive `fast-redact` was removed from the lockfile

How to reproduce locally:

```bash
pnpm up astro@^5.14.3 vite@^6.4.1 fastify@latest pino@latest
pnpm install
pnpm audit
pnpm run build
```

Notes:
- `fast-redact` (CVE-2025-57319) was present previously via `fastify > pino > fast-redact`. After upgrades it is no longer present in `pnpm-lock.yaml`.
- If you operate a fork, run the commands above and verify your CI passes before deploying.

If you have questions, open an issue or an advisory in the repository.
