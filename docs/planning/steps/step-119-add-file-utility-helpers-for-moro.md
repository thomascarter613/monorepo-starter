# Step 119 — Add file utility helpers for moro

**Phase:** `07-moro-cli`

## Purpose

Create the first file utility module for future generators.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > packages/moro/src/files.ts <<'EOF'
import { mkdir, writeFile } from "node:fs/promises";
import { dirname } from "node:path";

export async function writeTextFile(path: string, content: string) {
  await mkdir(dirname(path), { recursive: true });
  await writeFile(path, content);
}
EOF

cat > packages/moro/src/files.test.ts <<'EOF'
import { describe, expect, it } from "vitest";
import { writeTextFile } from "./files";

describe("writeTextFile", () => {
  it("is a function", () => {
    expect(typeof writeTextFile).toBe("function");
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
git commit -m "feat(cli): add file utilities"
git push
```
