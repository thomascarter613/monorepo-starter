# Step 122 — Add generation audit log documentation

**Phase:** `07-moro-cli`

## Purpose

Document how future generated-file actions should be recorded.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/cli/generated-file-tracking.md <<'EOF'
# Generated File Tracking

`moro` should track generated files so future updates can avoid overwriting user changes.

## Metadata Location

```text
.moro/generated-manifest.json
```

## Required Metadata

- path
- owner
- hash
- generator version
- generated timestamp

## Rule

Generators must support dry-run previews before writing files.
EOF
```

## Validate

```bash
test -f docs/cli/generated-file-tracking.md
```

## Commit

```bash
git add .
git commit -m "docs(cli): document generated file tracking"
git push
```
