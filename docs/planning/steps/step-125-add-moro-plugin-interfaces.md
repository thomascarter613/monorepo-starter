# Step 125 — Add moro plugin interfaces

**Phase:** `07-moro-cli`

## Purpose

Create initial TypeScript interfaces for future plugins.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > packages/moro/src/plugins.ts <<'EOF'
export type MoroPluginCapability = "command" | "generator" | "validator" | "profile" | "template";

export interface MoroPlugin {
  name: string;
  version: string;
  capabilities: MoroPluginCapability[];
}
EOF
```

## Validate

```bash
bun run typecheck
```

## Commit

```bash
git add .
git commit -m "feat(cli): add plugin interfaces"
git push
```
