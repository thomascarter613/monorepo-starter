# Step 053 — Install and configure markdownlint

**Phase:** `03-tooling-foundation`

## Purpose

Add Markdown linting as a repository quality gate.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add -d markdownlint-cli2

cat > .markdownlint-cli2.jsonc <<'EOF'
{
  "config": {
    "default": true,
    "MD013": false,
    "MD033": false,
    "MD041": false
  },
  "globs": ["**/*.md", "!node_modules", "!coverage", "!dist", "!build"]
}
EOF

bun pm pkg set scripts.lint:md="markdownlint-cli2"
python - <<'PY'
import json
p=json.load(open('package.json'))
p['scripts']['check']='moon run root:check && bun run lint:md'
open('package.json','w').write(json.dumps(p, indent=2)+'\n')
PY
```

## Validate

```bash
bun run lint:md
```

## Commit

```bash
git add .
git commit -m "chore(docs): add markdownlint"
git push
```
