0019-install-moon.md

## Step 19 — Install moon and initialize its workspace config

Now implement ADR-0006 by adding moon as a pinned dev dependency and creating the initial `.moon/` workspace configuration. The charter names moon as the default monorepo task runner, and the official moon docs support installing it through the `@moonrepo/cli` npm package with Bun. Bun requires packages with lifecycle scripts to be trusted explicitly.  ([Moonrepo][1]) ([Bun][2])

From the repo root, run:

```bash
bun -e 'const p = await Bun.file("package.json").json(); p.trustedDependencies = Array.from(new Set([...(p.trustedDependencies ?? []), "@moonrepo/cli"])); await Bun.write("package.json", `${JSON.stringify(p, null, 2)}\n`);'
```

Install moon:

```bash
bun add -d @moonrepo/cli
```

Verify it:

```bash
bun run moon --version
```

Initialize moon minimally:

```bash
bun run moon init --minimal
```

The moon docs say `moon init` creates the `.moon` folder with workspace configuration and integrates the repo with moon’s workspace model. ([Moonrepo][3])

Then commit:

```bash
git add package.json bun.lock .moon .gitignore
git commit -m "chore(tasks): initialize moon workspace"
git push
```

[1]: https://moonrepo.dev/docs/install "Install moon | moonrepo"
[2]: https://bun.com/docs/guides/install/trusted?utm_source=chatgpt.com "Add a trusted dependency"
[3]: https://moonrepo.dev/docs/setup-workspace "Setup workspace | moonrepo"
