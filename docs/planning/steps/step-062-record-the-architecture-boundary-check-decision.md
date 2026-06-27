# Step 062 — Record the architecture boundary check decision

**Phase:** `03-tooling-foundation`

## Purpose

Record the decision to use dependency-cruiser for TypeScript boundary checks.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0014-use-dependency-cruiser-for-architecture-boundaries.md <<'EOF'
# ADR-0014: Use dependency-cruiser for Architecture Boundaries

## Status

Accepted

## Date

2026-06-26

## Context

The repository needs enforceable import and dependency boundary checks.

## Decision

Use dependency-cruiser as the first architecture fitness check for TypeScript package boundaries.

## Consequences

Boundary rules can be enforced locally and in CI.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0014 | Use dependency-cruiser for Architecture Boundaries | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0014" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose dependency-cruiser for boundaries"
git push
```
