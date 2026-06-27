# Step 147 — Update TypeScript references for apps and services

**Phase:** `09-workspace-skeleton`

## Purpose

Add app and service tsconfig references to the root TypeScript config.

## Commands

Run from the repository root unless stated otherwise.

```bash
python - <<'PY'
import json
from pathlib import Path
roots = []
for parent in ['packages', 'apps', 'services']:
  roots.extend(sorted([p for p in Path(parent).iterdir() if (p / 'tsconfig.json').exists()]))
config = json.loads(Path('tsconfig.json').read_text())
config['references'] = [{'path': str(p)} for p in roots]
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
git commit -m "chore(ts): add app and service references"
git push
```
