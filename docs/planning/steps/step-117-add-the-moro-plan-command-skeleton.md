# Step 117 — Add the moro plan command skeleton

**Phase:** `07-moro-cli`

## Purpose

Add a planning command that will later generate epics, work packets, and tasks.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > packages/moro/src/plan.ts <<'EOF'
export function runPlan() {
  console.log("moro plan: planning generation is not implemented yet");
  return 0;
}
EOF

python - <<'PY'
from pathlib import Path
p=Path('packages/moro/src/index.ts')
text=p.read_text()
text=text.replace('import { runCheck } from "./check";', 'import { runCheck } from "./check";\nimport { runPlan } from "./plan";')
text=text.replace('if (command === "check") {\n  process.exit(runCheck());\n}', 'if (command === "check") {\n  process.exit(runCheck());\n}\n\nif (command === "plan") {\n  process.exit(runPlan());\n}')
p.write_text(text)
PY
```

## Validate

```bash
bun run moro plan
```

## Commit

```bash
git add .
git commit -m "feat(cli): add plan command skeleton"
git push
```
