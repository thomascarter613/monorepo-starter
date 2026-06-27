0020-add-root-moon.md

## Step 20 — Add the root moon project and wire root scripts through moon

Now make the repository root an explicit moon project. Moon supports this by mapping a root-level project to `"."`, and moon tasks are run as project targets such as `root:check`. ([moonrepo.dev][1])

Your charter makes moon the canonical monorepo task orchestrator, so `package.json` should become a convenience wrapper while moon owns task orchestration. 

From the repo root, run:

```bash
cat > .moon/workspace.yml <<'EOF'
$schema: "https://moonrepo.dev/schemas/workspace.json"

projects:
  root: "."
EOF
```

Create the root moon project tasks:

```bash
cat > moon.yml <<'EOF'
$schema: "https://moonrepo.dev/schemas/project.json"

language: "typescript"

tasks:
  format:
    command: "biome check --write ."

  format-check:
    command: "biome check ."

  lint:
    command: "biome lint ."

  typecheck:
    command: "tsc -b tsconfig.json --pretty false"

  test:
    command: "echo 'tests not configured yet'"

  build:
    command: "echo 'build not configured yet'"

  doctor:
    command: "echo 'moro doctor not implemented yet'"

  check:
    deps:
      - "format-check"
      - "lint"
      - "typecheck"
      - "test"
EOF
```

Update the root scripts to call moon:

```bash
bun pm pkg set scripts.format="moon run root:format"
bun pm pkg set scripts.format:check="moon run root:format-check"
bun pm pkg set scripts.lint="moon run root:lint"
bun pm pkg set scripts.typecheck="moon run root:typecheck"
bun pm pkg set scripts.test="moon run root:test"
bun pm pkg set scripts.build="moon run root:build"
bun pm pkg set scripts.doctor="moon run root:doctor"
bun pm pkg set scripts.check="moon run root:check"
```

Verify:

```bash
bun run check
```

Then commit:

```bash
git add .moon/workspace.yml moon.yml package.json bun.lock
git commit -m "chore(tasks): route root scripts through moon"
git push
```

[1]: https://moonrepo.dev/docs/guides/root-project?utm_source=chatgpt.com "Root-level project"
