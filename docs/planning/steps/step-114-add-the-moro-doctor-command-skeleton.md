# Step 114 — Add the moro doctor command skeleton

**Phase:** `07-moro-cli`

## Purpose

Create a separate module for the future repo doctor command.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > packages/moro/src/doctor.ts <<'EOF'
export function runDoctor() {
  console.log("moro doctor: repository health checks are not fully implemented yet");
  return 0;
}
EOF

python - <<'PY'
from pathlib import Path
p=Path('packages/moro/src/index.ts')
text=p.read_text()
text=text.replace('import { commandNames } from "./commands";', 'import { commandNames } from "./commands";\nimport { runDoctor } from "./doctor";')
text=text.replace('if (command === "version" || command === "--version" || command === "-v") {\n      console.log("0.0.0");\n      process.exit(0);\n    }', 'if (command === "version" || command === "--version" || command === "-v") {\n  console.log("0.0.0");\n  process.exit(0);\n}\n\nif (command === "doctor") {\n  process.exit(runDoctor());\n}')
p.write_text(text)
PY
```

## Validate

```bash
bun run moro doctor
```

## Commit

```bash
git add .
git commit -m "feat(cli): add doctor command skeleton"
git push
```
