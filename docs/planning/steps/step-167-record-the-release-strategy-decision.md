# Step 167 — Record the release strategy decision

**Phase:** `12-release-ci`

## Purpose

Record automated releases with manual approval gates before adding Changesets.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0038-use-changesets-for-release-management.md <<'EOF'
# ADR-0038: Use Changesets for Release Management

## Status

Accepted

## Date

2026-06-26

## Context

The repository needs versioning, changelogs, and release preparation.

## Decision

Use Changesets for release management, with automated release preparation and manual approval gates.

## Consequences

Releases are documented, reviewable, and automation-ready.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0038 | Use Changesets for Release Management | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0038" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose changesets for releases"
git push
```
