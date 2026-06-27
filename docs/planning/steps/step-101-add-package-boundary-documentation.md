# Step 101 — Add package boundary documentation

**Phase:** `06-architecture-governance`

## Purpose

Explain how packages should depend on one another.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/package-boundaries.md <<'EOF'
# Package Boundaries

Shared packages should have clear responsibilities.

## Package Rules

- Keep packages small and focused.
- Avoid circular dependencies.
- Prefer explicit exports.
- Do not import app or service code from packages.
- Keep runtime-specific code out of generic packages.

## Boundary Validation

```bash
bun run arch
```
EOF
```

## Validate

```bash
test -f docs/architecture/package-boundaries.md
```

## Commit

```bash
git add .
git commit -m "docs(architecture): document package boundaries"
git push
```
