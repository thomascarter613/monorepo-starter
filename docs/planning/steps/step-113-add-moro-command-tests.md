# Step 113 — Add moro command tests

**Phase:** `07-moro-cli`

## Purpose

Add a small test around the command list contract.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > packages/moro/src/commands.ts <<'EOF'
export const commandNames = [
  "init",
  "add",
  "doctor",
  "fix",
  "check",
  "plan",
  "evolve",
  "github",
  "dashboard",
  "release",
  "version",
  "help"
] as const;
EOF

python - <<'PY'
from pathlib import Path
p=Path('packages/moro/src/index.ts')
text=p.read_text()
text=text.replace('const commands = [\n      "init",\n      "add",\n      "doctor",\n      "fix",\n      "check",\n      "plan",\n      "evolve",\n      "github",\n      "dashboard",\n      "release",\n      "version",\n      "help"\n    ];', 'import { commandNames } from "./commands";\n\nconst commands = commandNames;')
p.write_text(text)
PY

cat > packages/moro/src/commands.test.ts <<'EOF'
import { describe, expect, it } from "vitest";
import { commandNames } from "./commands";

describe("moro commands", () => {
  it("includes the baseline lifecycle commands", () => {
    expect(commandNames).toContain("doctor");
    expect(commandNames).toContain("plan");
    expect(commandNames).toContain("evolve");
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
git commit -m "test(cli): add moro command tests"
git push
```
