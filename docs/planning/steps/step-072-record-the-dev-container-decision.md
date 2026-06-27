# Step 072 — Record the Dev Container decision

**Phase:** `04-environments-infra`

## Purpose

Record Dev Containers as the reproducible development environment option.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0018-support-dev-containers.md <<'EOF'
# ADR-0018: Support Dev Containers

## Status

Accepted

## Date

2026-06-26

## Context

The starter should support reproducible local development environments.

## Decision

Provide a `.devcontainer` configuration as a first-class development option.

## Consequences

Contributors can use a containerized development environment when local machine setup is inconsistent.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0018 | Support Dev Containers | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0018" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): support dev containers"
git push
```
