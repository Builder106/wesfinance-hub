# CONTRIBUTING — WesFinance Hub

Welcome! This repository serves as the central hub for Wesleyan's Econ &
Finance community.

## Dev Setup

(To be added upon tech stack finalization)

## Branches and deployments

Use short-lived `feature/*` branches for changes. Merge tested work into
`staging` for shared preview and acceptance testing, then promote `staging` to
`main` for production. Vercel automatic deployments are limited to those two
branches; CI still checks pull requests from feature branches.

WesFinance Hub is a unified portal at this stage. Do not create a persistent
branch for each economics project unless that project later receives its own
Vercel project, release schedule, and production owner. See
[`docs/deployment-and-branching.md`](docs/deployment-and-branching.md) before
changing this policy.

## Guardrails

- **Performance**: We target < 1s LCP.
- **Commit Messages**: Standard conventional commits. No AI-generated
  co-author trailers.

## Out of Scope

- Direct trading or money handling; this is purely educational/networking software.
