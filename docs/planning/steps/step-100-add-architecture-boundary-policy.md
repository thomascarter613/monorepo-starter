# Step 100 — Add architecture boundary policy

**Phase:** `06-architecture-governance`

## Purpose

Document allowed dependency directions before enforcing stricter rules.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p policies/architecture

cat > policies/architecture/boundaries.md <<'EOF'
# Architecture Boundaries

## Default Direction

Applications and services may depend on shared packages.

Shared packages should not depend on applications or services.

```text
apps/services -> packages -> libs/configs/contracts
```

## Rules

- `apps/*` may import `packages/*`.
- `services/*` may import `packages/*`.
- `packages/*` must not import `apps/*`.
- `packages/*` must not import `services/*`.
- Generated files must be marked and tracked.
EOF
```

## Validate

```bash
test -f policies/architecture/boundaries.md
```

## Commit

```bash
git add .
git commit -m "docs(architecture): add boundary policy"
git push
```
