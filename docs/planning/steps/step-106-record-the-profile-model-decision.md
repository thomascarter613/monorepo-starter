# Step 106 — Record the profile model decision

**Phase:** `06-architecture-governance`

## Purpose

Record the decision to use profile-based generation.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0028-use-profile-based-generation.md <<'EOF'
# ADR-0028: Use Profile-Based Generation

## Status

Accepted

## Date

2026-06-26

## Context

Different projects need different app, package, service, infrastructure, and AI capabilities.

## Decision

Use profile-based generation so users can choose a golden path while keeping optional complexity out of minimal projects.

## Consequences

Profiles become a primary extension point for the `moro` CLI.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0028 | Use Profile-Based Generation | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0028" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): define profile-based generation"
git push
```
