# Maintenance Policy

This policy defines how `monorepo-starter` should be maintained over time.

## Dependency Updates

Dependencies should be updated through documented automation where practical. Updates that affect runtime behavior, generated code, security posture, or developer workflow require review.

## Security Updates

Security patches should be prioritized ahead of normal feature work when risk is material.

## Deprecations

Deprecated commands, profiles, templates, or packages should have:

- a documented replacement
- a migration note
- a removal target when possible

## Support Windows

Formal support windows will be defined before a stable public release.

## Maintenance Rule

Maintenance work should preserve the golden path, avoid unnecessary churn, and keep the starter usable by a solo developer.
