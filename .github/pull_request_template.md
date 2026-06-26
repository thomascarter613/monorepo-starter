# Pull Request

## Summary

Describe what changed and why.

## Type of Change

Check all that apply:

- [ ] Feature
- [ ] Fix
- [ ] Documentation
- [ ] Refactor
- [ ] Test
- [ ] Build/tooling
- [ ] CI/CD
- [ ] Security
- [ ] Governance/policy
- [ ] Release
- [ ] Other

## Related Work

Link related issues, ADRs, plans, or work packets.

## Checklist

- [ ] I read the relevant project charter sections.
- [ ] I checked existing ADRs before making this change.
- [ ] I added or updated an ADR if this introduces a major decision.
- [ ] I updated documentation if behavior, workflow, structure, or commands changed.
- [ ] I kept the change focused and reviewable.
- [ ] I avoided committing secrets or local-only files.
- [ ] I used Bun as the default package manager.
- [ ] I did not add conflicting lockfiles.
- [ ] I considered security and supply-chain impact.
- [ ] I considered whether AI-agent instructions need to be updated.

## Validation

Commands run:

```bash
bun install --frozen-lockfile
bun run check
```

If any command was not run, explain why.

## Screenshots or Output

Add screenshots, terminal output, generated reports, or other evidence if useful.

## Risk Notes

Describe risks, migration concerns, compatibility issues, or follow-up work.

## Reviewer Notes

Anything specific reviewers should focus on?
