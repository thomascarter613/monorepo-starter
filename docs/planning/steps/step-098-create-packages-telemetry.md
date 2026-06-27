# Step 098 — Create packages/telemetry

**Phase:** `05-shared-packages`

## Purpose

Shared OpenTelemetry setup and instrumentation helpers.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/telemetry/src

cat > packages/telemetry/package.json <<'EOF'
{
  "name": "@monorepo-starter/telemetry",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "main": "./src/index.ts",
  "types": "./src/index.ts",
  "exports": {
    ".": "./src/index.ts"
  },
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run"
  }
}
EOF

cat > packages/telemetry/tsconfig.json <<'EOF'
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "rootDir": "src"
  },
  "include": ["src/**/*.ts"]
}
EOF

cat > packages/telemetry/src/index.ts <<'EOF'
export const packageName = "@monorepo-starter/telemetry";
export const telemetryPackageName = "@monorepo-starter/telemetry";
EOF

cat > packages/telemetry/README.md <<'EOF'
# @monorepo-starter/telemetry

Shared OpenTelemetry setup and instrumentation helpers.
EOF
```

## Validate

```bash
cd packages/telemetry && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(packages): add telemetry package"
git push
```
