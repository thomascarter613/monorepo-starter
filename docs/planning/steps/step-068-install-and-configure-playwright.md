# Step 068 — Install and configure Playwright

**Phase:** `03-tooling-foundation`

## Purpose

Add the browser test baseline.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add -d @playwright/test

cat > playwright.config.ts <<'EOF'
import { defineConfig } from "@playwright/test";

export default defineConfig({
  testDir: "tests/e2e",
  reporter: "list",
  use: {
    baseURL: "http://localhost:3000",
    trace: "on-first-retry"
  }
});
EOF

bun pm pkg set scripts.test:e2e="playwright test"
```

## Validate

```bash
bunx playwright --version
```

## Commit

```bash
git add .
git commit -m "chore(test): add playwright"
git push
```
