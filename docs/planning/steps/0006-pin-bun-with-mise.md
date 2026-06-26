0006-pin-bun-with-mise.md

## Step 6 — Pin Bun with `mise`

Now add the tool-version manager config before installing dependencies. Your charter makes **mise** the default tool version manager and **Bun** the default runtime/package manager, so the repo should declare its expected Bun version explicitly. 

From the repo root, run:

```bash
BUN_VERSION="$(bun --version)"

cat > mise.toml <<EOF
[tools]
bun = "$BUN_VERSION"
EOF
```

Verify it:

```bash
cat mise.toml
```

You should see something like:

```toml
[tools]
bun = "1.2.17"
```

Then commit:

```bash
git add mise.toml
git commit -m "chore(repo): pin bun with mise"
git push
```
