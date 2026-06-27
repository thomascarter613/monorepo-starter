# Step 037 — Add the code of conduct

**Phase:** `01-github-governance`

## Purpose

Add a basic contributor conduct document for open-source readiness.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > CODE_OF_CONDUCT.md <<'EOF'
# Code of Conduct

`monorepo-starter` is intended to be a respectful, constructive, and professional project.

## Expected Behavior

- Be respectful and direct.
- Discuss ideas on their merits.
- Give actionable feedback.
- Assume good intent where reasonable.
- Keep collaboration focused on the project.

## Unacceptable Behavior

- Harassment or abuse
- Personal attacks
- Discriminatory language
- Deliberate disruption
- Publishing private information

## Enforcement

The maintainer may remove comments, close issues, block participants, or take other reasonable action to protect the project.

A fuller community policy may be adopted before public release.
EOF
```

## Validate

```bash
test -f CODE_OF_CONDUCT.md
```

## Commit

```bash
git add .
git commit -m "docs(repo): add code of conduct"
git push
```
