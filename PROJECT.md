# renovate-config

`renovate-config` is a production tooling repository for the TseFamily
Renovate relay preset. It owns the `default.json` preset that onboards
TseFamily repositories onto the Sylphx org-wide Renovate policy while keeping
TseFamily-specific overrides local to this repository.

## Lifecycle And Layer

- Lifecycle: `production`
- Layer: `tooling`

## Goals

- Provide the TseFamily Renovate relay preset for repositories that inherit the
  Sylphx org-wide dependency update policy.
- Keep TseFamily-specific Renovate overrides explicit in `default.json`.
- Preserve `SylphxAI/renovate-config` as the upstream source of truth for base
  Renovate policy.

## Non-Goals

- Own the Sylphx org-wide Renovate base policy or package-manager strategy.
- Encode one application repository's dependency exceptions as a global
  TseFamily default without a documented reason.
- Publish enterprise doctrine, org rulesets, rollout issue reconciliation, or
  shared CI policy.

## Boundaries

This repository owns only the TseFamily relay layer. Base policy changes go to
`SylphxAI/renovate-config`; repo-specific exceptions belong in the consuming
repository unless they are intentionally family-wide.

## Public Surfaces

- `default.json` is the Renovate preset consumed by TseFamily repositories.
- `README.md` documents the relay relationship and override boundary.
- `.doctrine/project.json` is the machine-readable project manifest.

## Delivery

No repository-local CI workflow is currently present. Changes should be proven
with JSON validation and, for policy changes, Renovate dry-run or affected-repo
readback. Recovery is source-revertable for preset mistakes, but consumers may
need follow-up PR cleanup if the bad policy already opened dependency updates.

The authoritative control-plane record is `.doctrine/project.json`.
