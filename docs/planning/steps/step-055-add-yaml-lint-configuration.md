# Step 055 — Add YAML lint configuration

**Phase:** `03-tooling-foundation`

## Purpose

Configure YAML linting for GitHub workflows and repository YAML files.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > .yamllint.yml <<'EOF'
extends: default

rules:
  line-length: disable
  truthy:
    allowed-values: ["true", "false", "on", "off"]
  comments:
    min-spaces-from-content: 1
EOF

bun pm pkg set scripts.lint:yaml="yamllint ."
```

## Validate

```bash
test -f .yamllint.yml
```

## Commit

```bash
git add .
git commit -m "chore(yaml): add yamllint config"
git push
```

## Notes

Install yamllint on your machine through your OS package manager, pipx, or mise before running the script.
