# Step 120 — Add moro config loader skeleton

**Phase:** `07-moro-cli`

## Purpose

Add initial support for detecting config files.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > packages/moro/src/config.ts <<'EOF'
import { existsSync } from "node:fs";

export const configCandidates = ["moro.config.ts", "moro.config.json", "moro.config.yaml", "moro.config.yml"];

export function findConfigFile(cwd = process.cwd()) {
  return configCandidates.find((candidate) => existsSync(`${cwd}/${candidate}`));
}
EOF

cat > moro.config.ts <<'EOF'
export default {
  name: "monorepo-starter",
  packageManager: "bun",
  profile: "starter-dev"
};
EOF
```

## Validate

```bash
bun run typecheck
```

## Commit

```bash
git add .
git commit -m "feat(cli): add moro config loader skeleton"
git push
```
