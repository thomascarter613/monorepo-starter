# Step 066 — Add a baseline unit test

**Phase:** `03-tooling-foundation`

## Purpose

Add the smallest test that proves the test runner is wired correctly.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p tests/unit

cat > tests/unit/baseline.test.ts <<'EOF'
import { describe, expect, it } from "vitest";

describe("baseline", () => {
  it("runs the test suite", () => {
    expect(true).toBe(true);
  });
});
EOF
```

## Validate

```bash
bun run test
```

## Commit

```bash
git add .
git commit -m "test(repo): add baseline unit test"
git push
```
