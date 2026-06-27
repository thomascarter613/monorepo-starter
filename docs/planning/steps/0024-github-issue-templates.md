0024-github-issue-templates.md

## Step 24 — Add GitHub issue templates

Now add issue templates so work can start becoming structured instead of informal. Your charter explicitly calls for GitHub integration with issue templates, task planning, labels, milestones, work packets, governance, and SDLC workflows. 

From the repo root, run:

```bash
mkdir -p .github/ISSUE_TEMPLATE
```

Create the issue template chooser config:

```bash
cat > .github/ISSUE_TEMPLATE/config.yml <<'EOF'
blank_issues_enabled: true
contact_links:
  - name: Security policy
    url: https://github.com/OWNER/REPO/security/policy
    about: Please review the security policy before reporting vulnerabilities.
EOF
```

Now replace `OWNER/REPO` automatically:

```bash
REPO_FULL_NAME="$(gh repo view --json nameWithOwner -q .nameWithOwner)"
sed -i "s|OWNER/REPO|$REPO_FULL_NAME|g" .github/ISSUE_TEMPLATE/config.yml
```

Create a task template:

````bash
cat > .github/ISSUE_TEMPLATE/task.md <<'EOF'
---
name: Task
about: A concrete implementation, documentation, tooling, governance, or maintenance task
title: "task: "
labels: ["type: task", "status: needs triage"]
assignees: ""
---

## Summary

Describe the task.

## Context

Why is this needed?

## Scope

What should be included?

## Out of Scope

What should not be included?

## Acceptance Criteria

- [ ] 
- [ ] 
- [ ] 

## Validation

Expected validation commands:

```bash
bun install --frozen-lockfile
bun run check
```

## Related Documents

Link related charter sections, ADRs, issues, plans, or work packets.

## Notes

Add implementation notes, risks, constraints, or follow-up work.
EOF

````

Create a feature template:

```bash
cat > .github/ISSUE_TEMPLATE/feature.md <<'EOF'
---
name: Feature
about: A new product, repo, CLI, automation, app, service, package, or workflow capability
title: "feat: "
labels: ["type: feature", "status: needs triage"]
assignees: ""
---

## Feature Summary

Describe the feature.

## Problem

What problem does this solve?

## Proposed Solution

Describe the intended solution.

## Alternatives Considered

List alternatives if known.

## Acceptance Criteria

- [ ] 
- [ ] 
- [ ] 

## Documentation Impact

What documentation needs to be added or updated?

## Testing / Validation

What should prove this works?

## Related Documents

Link related charter sections, ADRs, plans, or work packets.

## Notes

Add risks, constraints, open questions, or follow-up work.
EOF
````

Create a bug template:

````bash
cat > .github/ISSUE_TEMPLATE/bug.md <<'EOF'
---
name: Bug
about: Something is broken, incorrect, inconsistent, or not working as expected
title: "fix: "
labels: ["type: bug", "status: needs triage"]
assignees: ""
---

## Bug Summary

Describe the bug.

## Expected Behavior

What should happen?

## Actual Behavior

What happens instead?

## Steps to Reproduce

1. 
2. 
3. 

## Environment

- OS:
- Bun version:
- Node version, if relevant:
- Git branch:
- Commit SHA:

## Logs or Output




## Possible Cause

Optional notes about suspected cause.

## Acceptance Criteria

* [ ] The bug is reproduced or clearly understood.
* [ ] The fix is implemented.
* [ ] A regression test or validation step is added where practical.
* [ ] Documentation is updated if needed.

## Related Documents

Link related issues, ADRs, or docs.
EOF

````

Create a documentation template:

```bash
cat > .github/ISSUE_TEMPLATE/docs.md <<'EOF'
---
name: Documentation
about: Documentation that should be added, corrected, expanded, or reorganized
title: "docs: "
labels: ["type: docs", "status: needs triage"]
assignees: ""
---

## Documentation Summary

Describe the documentation change.

## Location

Which file, folder, or topic is affected?

## Reason

Why is this documentation needed?

## Proposed Change

Describe what should be added, removed, clarified, or reorganized.

## Acceptance Criteria

- [ ] The documentation is clear.
- [ ] The documentation is consistent with the project charter.
- [ ] The documentation is consistent with relevant ADRs.
- [ ] Commands and paths are accurate where included.

## Related Documents

Link related charter sections, ADRs, issues, plans, or work packets.
EOF
````

Create an ADR template issue:

```bash
cat > .github/ISSUE_TEMPLATE/adr.md <<'EOF'
---
name: Architecture Decision
about: A proposed technical, tooling, workflow, governance, or architectural decision
title: "adr: "
labels: ["type: adr", "status: needs decision"]
assignees: ""
---

## Decision Summary

What decision needs to be made?

## Context

Why is this decision needed now?

## Options

List the options being considered.

### Option 1

Description, benefits, drawbacks.

### Option 2

Description, benefits, drawbacks.

## Recommended Decision

State the recommended option if known.

## Consequences

What happens if this decision is accepted?

## Related Documents

Link related charter sections, existing ADRs, issues, plans, or work packets.

## Acceptance Criteria

- [ ] The decision is documented in an ADR.
- [ ] The ADR includes context, decision, consequences, alternatives, and follow-up work.
- [ ] Implementation work is linked separately if needed.
EOF
```

Then commit:

```bash
git add .github/ISSUE_TEMPLATE
git commit -m "docs(github): add issue templates"
git push
```
