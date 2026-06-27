# Step 129 — Record architecture graph generation decision

**Phase:** `08-dashboard-graphs`

## Purpose

Record graph generation as a first-class architecture capability.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0032-generate-architecture-graphs.md <<'EOF'
# ADR-0032: Generate Architecture Graphs

## Status

Accepted

## Date

2026-06-26

## Context

The starter should help users understand workspace, package, task, ownership, and generated-file relationships.

## Decision

Generate architecture graphs in Markdown, Mermaid, DOT, and JSON where practical.

## Consequences

The repository becomes easier to inspect and explain.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0032 | Generate Architecture Graphs | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0032" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): define architecture graph generation"
git push
```
