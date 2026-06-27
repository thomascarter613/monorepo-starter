# Step 065 — Install and configure Vitest

**Phase:** `03-tooling-foundation`

## Purpose

Add the default unit test runner and config.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add -d vitest

cat > vitest.config.ts <<'EOF'
import { defineConfig } from "vitest/config";

export default defineConfig({
  test: {
    globals: false,
    include: ["**/*.test.ts", "**/*.spec.ts"],
    exclude: ["node_modules", "dist", "build", "coverage"]
  }
});
EOF

bun pm pkg set scripts.test="vitest run"
```

## Validate

```bash
bun run test -- --passWithNoTests
```

## Commit

```bash
git add .
git commit -m "chore(test): add vitest"
git push
```
