# Planning Artifact Model

`monorepo-starter` uses structured planning artifacts so work can move from intent to execution without losing context.

## Hierarchy

``text
Vision
└── Roadmap
    └── Milestone
        └── Epic
            └── Feature
                └── Work Packet
                    └── Task
                        └── Subtask
``

## Artifact Definitions

- **Vision**: the long-term reason the project exists.
- **Roadmap**: staged path from current state to target state.
- **Milestone**: a release-oriented package of outcomes.
- **Epic**: a major body of work.
- **Feature**: a user-visible or operator-visible capability.
- **Work Packet**: a bounded implementation unit with acceptance criteria.
- **Task**: a concrete action a developer can complete.
- **Subtask**: the smallest useful execution item.

## Rule

Every non-trivial implementation change should be traceable to a planning artifact, issue, ADR, or roadmap item.
