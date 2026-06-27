# Step 110 — Record the moro CLI architecture decision

**Phase:** `07-moro-cli`

## Purpose

Record the CLI location, runtime, and core command model before implementation.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0029-build-moro-cli-in-typescript-on-bun.md <<'EOF'
# ADR-0029: Build `moro` CLI in TypeScript on Bun

## Status

Accepted

## Date

2026-06-26

## Context

The project charter defines `moro` as the built-in CLI for init, generation, checks, planning, GitHub integration, dashboard, release, and evolution.

## Decision

Build `moro` in TypeScript, run it on Bun, and place it in `packages/moro`.

## Consequences

The CLI shares the same runtime and language as the starter foundation.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0029 | Build `moro` CLI in TypeScript on Bun | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0029" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): define moro cli architecture"
git push
```
