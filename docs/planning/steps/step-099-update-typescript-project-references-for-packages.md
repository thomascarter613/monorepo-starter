# Step 099 — Update TypeScript project references for packages

**Phase:** `05-shared-packages`

## Purpose

Add package references to the root TypeScript config.

## Commands

Run from the repository root unless stated otherwise.

```bash
python - <<'PY'
import json
from pathlib import Path
packages = sorted([p for p in Path('packages').iterdir() if (p / 'tsconfig.json').exists()])
config = json.loads(Path('tsconfig.json').read_text())
config['references'] = [{'path': str(p)} for p in packages]
Path('tsconfig.json').write_text(json.dumps(config, indent=2) + '\n')
PY
```

## Validate

```bash
bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(ts): add package project references"
git push
```
