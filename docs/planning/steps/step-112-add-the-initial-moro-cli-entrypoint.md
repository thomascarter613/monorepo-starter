# Step 112 — Add the initial moro CLI entrypoint

**Phase:** `07-moro-cli`

## Purpose

Create the first working `moro` command with help output.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > packages/moro/src/index.ts <<'EOF'
#!/usr/bin/env bun

const commands = [
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
];

function printHelp() {
  console.log(`moro\n\nUsage:\n  moro <command> [options]\n\nCommands:\n${commands.map((command) => `  ${command}`).join("\n")}`);
}

const command = Bun.argv[2] ?? "help";

if (command === "help" || command === "--help" || command === "-h") {
  printHelp();
  process.exit(0);
}

if (command === "version" || command === "--version" || command === "-v") {
  console.log("0.0.0");
  process.exit(0);
}

console.error(`Unknown or unimplemented command: ${command}`);
printHelp();
process.exit(1);
EOF

chmod +x packages/moro/src/index.ts
bun pm pkg set scripts.moro="bun packages/moro/src/index.ts"
```

## Validate

```bash
bun run moro --help
```

## Commit

```bash
git add .
git commit -m "feat(cli): add initial moro entrypoint"
git push
```
