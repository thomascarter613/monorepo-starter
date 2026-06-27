# Step 102 — Tighten dependency-cruiser boundary rules

**Phase:** `06-architecture-governance`

## Purpose

Add explicit app/service/package dependency restrictions.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > dependency-cruiser.config.cjs <<'EOF'
module.exports = {
  forbidden: [
    {
      name: "no-circular",
      severity: "error",
      from: {},
      to: { circular: true }
    },
    {
      name: "packages-must-not-import-apps",
      severity: "error",
      from: { path: "^packages/" },
      to: { path: "^apps/" }
    },
    {
      name: "packages-must-not-import-services",
      severity: "error",
      from: { path: "^packages/" },
      to: { path: "^services/" }
    }
  ],
  options: {
    doNotFollow: { path: "node_modules" },
    tsConfig: { fileName: "tsconfig.json" }
  }
};
EOF
```

## Validate

```bash
bun run arch || true
```

## Commit

```bash
git add .
git commit -m "chore(architecture): tighten dependency boundary rules"
git push
```
