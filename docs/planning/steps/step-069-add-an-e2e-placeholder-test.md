# Step 069 — Add an e2e placeholder test

**Phase:** `03-tooling-foundation`

## Purpose

Add a placeholder e2e test that remains skipped until a web app exists.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p tests/e2e

cat > tests/e2e/baseline.spec.ts <<'EOF'
import { test } from "@playwright/test";

test.skip("web app smoke test placeholder", async ({ page }) => {
  await page.goto("/");
});
EOF
```

## Validate

```bash
bun run test:e2e
```

## Commit

```bash
git add .
git commit -m "test(e2e): add playwright placeholder"
git push
```
