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
``

## Naming

- Packages use kebab-case.
- Source files use kebab-case unless framework conventions require otherwise.
- Exported types use PascalCase.
- Functions and variables use camelCase.

## Documentation

Update docs when commands, structure, setup, architecture, policies, or workflows change.
