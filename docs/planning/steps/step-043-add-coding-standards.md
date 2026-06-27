# Step 043 — Add coding standards

**Phase:** `02-documentation-foundation`

## Purpose

Define basic style, naming, TypeScript, and documentation standards before source code expands.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/development/coding-standards.md <<'EOF'
# Coding Standards

## TypeScript

- Use strict TypeScript.
- Prefer explicit domain types over `any`.
- Avoid hidden global state.
- Prefer small modules with clear boundaries.

## Formatting

Biome is the default formatter and linter.

```bash
bun run format
bun run lint
```

## Naming

- Packages use kebab-case.
- Source files use kebab-case unless framework conventions require otherwise.
- Exported types use PascalCase.
- Functions and variables use camelCase.

## Documentation

Update docs when commands, structure, setup, architecture, policies, or workflows change.
EOF
```

## Validate

```bash
test -f docs/development/coding-standards.md
```

## Commit

```bash
git add .
git commit -m "docs(development): add coding standards"
git push
```
