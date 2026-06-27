# Step 116 — Add the moro check command skeleton

**Phase:** `07-moro-cli`

## Purpose

Add a CLI command that will later coordinate repository validation.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > packages/moro/src/check.ts <<'EOF'
export function runCheck() {
  console.log("moro check: use `bun run check` until full orchestration is implemented");
  return 0;
}
EOF

python - <<'PY'
from pathlib import Path
p=Path('packages/moro/src/index.ts')
text=p.read_text()
text=text.replace('import { runDoctor } from "./doctor";', 'import { runDoctor } from "./doctor";\nimport { runCheck } from "./check";')
insert="\nif (command === \"check\") {\n  process.exit(runCheck());\n}\n"
text=text.replace('if (command === "doctor") {\n  process.exit(runDoctor());\n}', 'if (command === "doctor") {\n  process.exit(runDoctor());\n}'+insert)
p.write_text(text)
PY
```

## Validate

```bash
bun run moro check
```

## Commit

```bash
git add .
git commit -m "feat(cli): add check command skeleton"
git push
```
