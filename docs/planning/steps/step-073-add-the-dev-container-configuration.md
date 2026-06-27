# Step 073 — Add the Dev Container configuration

**Phase:** `04-environments-infra`

## Purpose

Create the initial Dev Container setup.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > .devcontainer/devcontainer.json <<'EOF'
{
  "name": "monorepo-starter",
  "image": "mcr.microsoft.com/devcontainers/base:ubuntu",
  "features": {
    "ghcr.io/devcontainers/features/git:1": {},
    "ghcr.io/devcontainers/features/docker-in-docker:2": {}
  },
  "customizations": {
    "vscode": {
      "extensions": [
        "biomejs.biome",
        "EditorConfig.EditorConfig",
        "GitHub.vscode-github-actions"
      ]
    }
  },
  "postCreateCommand": "curl https://mise.run | sh && echo 'Run mise install && bun install after container creation.'"
}
EOF
```

## Validate

```bash
test -f .devcontainer/devcontainer.json
```

## Commit

```bash
git add .
git commit -m "chore(devcontainer): add dev container config"
git push
```
