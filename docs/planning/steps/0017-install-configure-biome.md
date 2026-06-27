0017-install-configure-biome.md

## Step 17 — Install and configure Biome

Now implement the formatter/linter decision from ADR-0005. Your charter names **Biome** as the default formatting/linting tool and includes formatting and linting in the required v1 quality gates. 

From the repo root, run:

```bash
bun add -d @biomejs/biome
```

Create the root Biome config:

```bash
cat > biome.json <<'EOF'
{
  "$schema": "https://biomejs.dev/schemas/2.0.6/schema.json",
  "vcs": {
    "enabled": true,
    "clientKind": "git",
    "useIgnoreFile": true
  },
  "files": {
    "ignoreUnknown": false
  },
  "formatter": {
    "enabled": true,
    "indentStyle": "space",
    "indentWidth": 2,
    "lineWidth": 100
  },
  "organizeImports": {
    "enabled": true
  },
  "linter": {
    "enabled": true,
    "rules": {
      "recommended": true,
      "correctness": {
        "noUnusedImports": "error",
        "noUnusedVariables": "error"
      },
      "suspicious": {
        "noExplicitAny": "warn"
      }
    }
  },
  "javascript": {
    "formatter": {
      "quoteStyle": "double",
      "semicolons": "always",
      "trailingCommas": "all"
    }
  },
  "json": {
    "formatter": {
      "trailingCommas": "none"
    }
  }
}
EOF
```

Update the root scripts:

```bash
bun pm pkg set scripts.format="biome check --write ."
bun pm pkg set scripts.format:check="biome check ."
bun pm pkg set scripts.lint="biome lint ."
```

Run the checks:

```bash
bun run format
bun run lint
bun run check
```

Then commit:

```bash
git add package.json bun.lock biome.json
git commit -m "chore(format): add biome formatting and linting"
git push
```
