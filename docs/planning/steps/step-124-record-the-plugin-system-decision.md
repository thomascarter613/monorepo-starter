# Step 124 — Record the plugin system decision

**Phase:** `07-moro-cli`

## Purpose

Record the long-term `moro` plugin architecture decision.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0030-support-local-and-official-moro-plugins.md <<'EOF'
# ADR-0030: Support Local and Official `moro` Plugins

## Status

Accepted

## Date

2026-06-26

## Context

`moro` needs extension points for profiles, generators, validators, commands, and lifecycle hooks.

## Decision

Support official plugins and local repository plugins first. Design for community plugins later.

## Consequences

The CLI can grow without forcing every extension into core.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0030 | Support Local and Official `moro` Plugins | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0030" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): define moro plugin model"
git push
```
