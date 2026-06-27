# Step 105 — Add initial moro state files

**Phase:** `06-architecture-governance`

## Purpose

Create empty state files used by future `moro` commands.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > .moro/state.json <<'EOF'
{
  "starterVersion": "0.0.0",
  "profile": "starter-dev",
  "generatedManifest": ".moro/generated-manifest.json"
}
EOF

cat > .moro/generated-manifest.json <<'EOF'
{
  "version": "0.0.0",
  "files": []
}
EOF
```

## Validate

```bash
test -f .moro/state.json && test -f .moro/generated-manifest.json
```

## Commit

```bash
git add .
git commit -m "chore(moro): add initial metadata state"
git push
```
