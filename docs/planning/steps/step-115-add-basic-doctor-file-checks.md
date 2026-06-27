# Step 115 — Add basic doctor file checks

**Phase:** `07-moro-cli`

## Purpose

Teach `moro doctor` to check for essential files.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > packages/moro/src/doctor.ts <<'EOF'
import { existsSync } from "node:fs";

const requiredFiles = [
  "project-charter.md",
  "README.md",
  "package.json",
  "bun.lock",
  "mise.toml",
  "tsconfig.json",
  "biome.json",
  "moon.yml",
  "AGENTS.md"
];

export function runDoctor() {
  let failures = 0;

  for (const file of requiredFiles) {
    if (existsSync(file)) {
      console.log(`ok   ${file}`);
    } else {
      console.error(`miss ${file}`);
      failures += 1;
    }
  }

  return failures === 0 ? 0 : 1;
}
EOF
```

## Validate

```bash
bun run moro doctor
```

## Commit

```bash
git add .
git commit -m "feat(cli): add basic doctor file checks"
git push
```
