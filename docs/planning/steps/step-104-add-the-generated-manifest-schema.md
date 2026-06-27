# Step 104 — Add the generated manifest schema

**Phase:** `06-architecture-governance`

## Purpose

Create the first schema for `.moro` generated-file metadata.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p .moro/schemas

cat > .moro/schemas/generated-manifest.schema.json <<'EOF'
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "title": "moro generated manifest",
  "type": "object",
  "required": ["version", "files"],
  "properties": {
    "version": { "type": "string" },
    "files": {
      "type": "array",
      "items": {
        "type": "object",
        "required": ["path", "owner", "hash"],
        "properties": {
          "path": { "type": "string" },
          "owner": { "type": "string" },
          "hash": { "type": "string" },
          "generatedAt": { "type": "string" }
        }
      }
    }
  }
}
EOF
```

## Validate

```bash
test -f .moro/schemas/generated-manifest.schema.json
```

## Commit

```bash
git add .
git commit -m "chore(moro): add generated manifest schema"
git push
```
