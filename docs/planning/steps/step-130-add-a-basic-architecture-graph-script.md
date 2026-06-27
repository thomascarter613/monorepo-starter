# Step 130 — Add a basic architecture graph script

**Phase:** `08-dashboard-graphs`

## Purpose

Create a first script that emits a simple Mermaid graph of top-level areas.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p docs/architecture/diagrams scripts/architecture

cat > scripts/architecture/generate-root-graph.sh <<'EOF'
#!/usr/bin/env bash
set -euo pipefail

cat > docs/architecture/diagrams/root-structure.mmd <<'GRAPH'
flowchart TD
  repo[monorepo-starter]
  repo --> apps
  repo --> services
  repo --> packages
  repo --> libs
  repo --> tools
  repo --> configs
  repo --> contracts
  repo --> infra
  repo --> policies
  repo --> docs
  repo --> tests
  repo --> examples
  repo --> templates
  repo --> profiles
  repo --> scripts
  repo --> github[.github]
  repo --> devcontainer[.devcontainer]
  repo --> moro[.moro]
GRAPH
EOF

chmod +x scripts/architecture/generate-root-graph.sh
scripts/architecture/generate-root-graph.sh
```

## Validate

```bash
test -f docs/architecture/diagrams/root-structure.mmd
```

## Commit

```bash
git add .
git commit -m "docs(architecture): add root graph generator"
git push
```
