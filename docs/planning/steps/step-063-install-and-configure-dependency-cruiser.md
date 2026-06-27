# Step 063 — Install and configure dependency-cruiser

**Phase:** `03-tooling-foundation`

## Purpose

Add the first architecture boundary check.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add -d dependency-cruiser

cat > dependency-cruiser.config.cjs <<'EOF'
module.exports = {
  forbidden: [
    {
      name: "no-circular",
      severity: "error",
      comment: "Do not allow circular dependencies.",
      from: {},
      to: { circular: true }
    },
    {
      name: "no-orphans-outside-known-roots",
      severity: "warn",
      from: { orphan: true, pathNot: "(^docs/|^scripts/|^templates/|^profiles/|^examples/|^policies/)" },
      to: {}
    }
  ],
  options: {
    doNotFollow: { path: "node_modules" },
    tsConfig: { fileName: "tsconfig.json" },
    reporterOptions: { dot: { collapsePattern: "node_modules/[^/]+" } }
  }
};
EOF

bun pm pkg set scripts.arch="depcruise --config dependency-cruiser.config.cjs ."
```

## Validate

```bash
bun run arch || true
```

## Commit

```bash
git add .
git commit -m "chore(architecture): add dependency boundary checks"
git push
```
