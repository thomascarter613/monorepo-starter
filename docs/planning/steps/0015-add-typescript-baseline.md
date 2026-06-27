0015-add-typescript-baseline.md

## Step 15 — Add the root TypeScript baseline

Now add TypeScript itself and the root TypeScript configuration. The charter makes this a Bun-first, TypeScript-first monorepo, so the repo should have a real typechecking foundation before apps, packages, services, or the `moro` CLI are added. 

From the repo root, run:

```bash id="18cv1e"
bun add -d typescript
```

Create the shared base config:

```bash id="z6d18k"
cat > tsconfig.base.json <<'EOF'
{
  "$schema": "https://json.schemastore.org/tsconfig",
  "compilerOptions": {
    "target": "ES2023",
    "lib": ["ES2023", "DOM", "DOM.Iterable"],
    "module": "ESNext",
    "moduleResolution": "Bundler",
    "moduleDetection": "force",
    "allowImportingTsExtensions": true,
    "resolveJsonModule": true,
    "isolatedModules": true,
    "verbatimModuleSyntax": true,
    "strict": true,
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true,
    "noImplicitOverride": true,
    "noFallthroughCasesInSwitch": true,
    "noEmit": true,
    "skipLibCheck": true
  }
}
EOF
```

Create the root project config:

```bash id="m1kshq"
cat > tsconfig.json <<'EOF'
{
  "$schema": "https://json.schemastore.org/tsconfig",
  "extends": "./tsconfig.base.json",
  "files": [],
  "references": []
}
EOF
```

Update the `typecheck` script:

```bash id="7re9ph"
bun pm pkg set scripts.typecheck="tsc -b tsconfig.json --pretty false"
```

Verify:

```bash id="88if1f"
bun run typecheck
```

Then commit:

```bash id="pwf16y"
git add package.json bun.lock tsconfig.json tsconfig.base.json
git commit -m "chore(ts): add root typescript baseline"
git push
```
