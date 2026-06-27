# Step 128 — Add dashboard command skeleton

**Phase:** `08-dashboard-graphs`

## Purpose

Add the CLI command placeholder for the future local dashboard.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > packages/moro/src/dashboard.ts <<'EOF'
export function runDashboard() {
  console.log("moro dashboard: local dashboard is not implemented yet");
  return 0;
}
EOF

python - <<'PY'
from pathlib import Path
p=Path('packages/moro/src/index.ts')
text=p.read_text()
text=text.replace('import { runInit } from "./init";', 'import { runInit } from "./init";\nimport { runDashboard } from "./dashboard";')
text=text.replace('if (command === "init") {\n  process.exit(runInit(Bun.argv.slice(3)));\n}', 'if (command === "init") {\n  process.exit(runInit(Bun.argv.slice(3)));\n}\n\nif (command === "dashboard") {\n  process.exit(runDashboard());\n}')
p.write_text(text)
PY
```

## Validate

```bash
bun run moro dashboard
```

## Commit

```bash
git add .
git commit -m "feat(cli): add dashboard command skeleton"
git push
```
