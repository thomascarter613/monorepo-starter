# Step 131 — Document architecture graphs

**Phase:** `08-dashboard-graphs`

## Purpose

Add documentation for generated architecture graph outputs.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/diagrams/README.md <<'EOF'
# Architecture Diagrams

This directory contains generated and hand-maintained architecture diagrams.

## Root Structure Graph

Generate it with:

```bash
scripts/architecture/generate-root-graph.sh
```

Output:

```text
docs/architecture/diagrams/root-structure.mmd
```
EOF
```

## Validate

```bash
test -f docs/architecture/diagrams/README.md
```

## Commit

```bash
git add .
git commit -m "docs(architecture): document diagram generation"
git push
```
