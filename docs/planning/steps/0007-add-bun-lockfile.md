0007-add-bun-lockfile.md

## Step 7 — Generate the canonical Bun lockfile

Now that `package.json` and `mise.toml` exist, generate the first canonical Bun lockfile. Your charter says Bun is the default package manager and `bun.lock` is the canonical default lockfile, so this should be created before adding dependencies or tools. 

From the repo root, run:

```bash id="k6tx3h"
bun install
```

Verify that Bun created the lockfile:

```bash id="vyi6g2"
ls -la bun.lock
```

Then verify a clean reproducible install works:

```bash id="r0eer3"
bun install --frozen-lockfile
```

Commit it:

```bash id="4vgtv3"
git add bun.lock
git commit -m "chore(repo): add bun lockfile"
git push
```

This establishes the first reproducible dependency baseline, even before the repo has real dependencies.
