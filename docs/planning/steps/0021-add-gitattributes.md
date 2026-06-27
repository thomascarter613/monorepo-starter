0021-add-gitattributes.md

## Step 21 — Add `.gitattributes`

Now add Git’s repository-level file handling rules. This should come early because the project will generate templates, scripts, lockfiles, docs, and eventually generated files through `moro`. Your charter explicitly calls for generated-code marking and repository governance, so Git attributes should be established before the repo grows much further. 

From the repo root, run:

```bash
cat > .gitattributes <<'EOF'
# Normalize text files across operating systems
* text=auto eol=lf

# Shell scripts
*.sh text eol=lf

# Markdown and documentation
*.md text eol=lf
*.mdx text eol=lf

# JavaScript / TypeScript
*.js text eol=lf
*.jsx text eol=lf
*.ts text eol=lf
*.tsx text eol=lf
*.mts text eol=lf
*.cts text eol=lf

# Data and config
*.json text eol=lf
*.jsonc text eol=lf
*.yaml text eol=lf
*.yml text eol=lf
*.toml text eol=lf
*.xml text eol=lf

# Docker / infra
Dockerfile text eol=lf
*.dockerfile text eol=lf

# Lockfiles
bun.lock text eol=lf

# Binary files
*.png binary
*.jpg binary
*.jpeg binary
*.gif binary
*.webp binary
*.ico binary
*.pdf binary
*.zip binary
*.gz binary
*.tgz binary

# Generated files
#
# Future generated files should be explicitly marked like this:
#
# path/to/generated-file linguist-generated=true
#
# Do not mark handwritten source, docs, policies, or ADRs as generated.
EOF
```

Then commit:

```bash
git add .gitattributes
git commit -m "chore(repo): add git attributes"
git push
```
