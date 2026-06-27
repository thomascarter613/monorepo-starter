# Step 042 — Add the command reference

**Phase:** `02-documentation-foundation`

## Purpose

Create the first command reference so common commands are discoverable.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/development/commands.md <<'EOF'
# Commands

## Install

```bash
bun install
```

## Validation

```bash
bun run check
```

## Formatting

```bash
bun run format
bun run format:check
```

## Linting

```bash
bun run lint
```

## Typechecking

```bash
bun run typecheck
```

## Testing

```bash
bun run test
```

## Build

```bash
bun run build
```

## Moon

```bash
moon run root:check
moon run root:typecheck
```
EOF
```

## Validate

```bash
test -f docs/development/commands.md
```

## Commit

```bash
git add .
git commit -m "docs(development): add command reference"
git push
```
