# Step 118 — Add the moro init command skeleton

**Phase:** `07-moro-cli`

## Purpose

Add a dry-run-first project initialization command placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > packages/moro/src/init.ts <<'EOF'
export function runInit(args: string[]) {
  const target = args[0] ?? ".";
  console.log(`moro init: would initialize ${target}`);
  console.log("dry-run behavior is the default until generation is implemented");
  return 0;
}
EOF

python - <<'PY'
from pathlib import Path
p=Path('packages/moro/src/index.ts')
text=p.read_text()
text=text.replace('import { runPlan } from "./plan";', 'import { runPlan } from "./plan";\nimport { runInit } from "./init";')
text=text.replace('if (command === "plan") {\n  process.exit(runPlan());\n}', 'if (command === "plan") {\n  process.exit(runPlan());\n}\n\nif (command === "init") {\n  process.exit(runInit(Bun.argv.slice(3)));\n}')
p.write_text(text)
PY
```

## Validate

```bash
bun run moro init sample-project
```

## Commit

```bash
git add .
git commit -m "feat(cli): add init command skeleton"
git push
```
