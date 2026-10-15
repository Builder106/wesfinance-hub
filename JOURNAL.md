# JOURNAL — WesFinance Hub

> Dated log of decisions, pivots, incidents, and quotes. Add entries as
> things happen — retrospectives need this raw material to land.
> Reverse-chronological; one paragraph max per entry.

## 2026-10-13: Removed the README diagram #decision

Removed the README's three-participant, four-message Mermaid block. It only restated that the portal fetches events and network data, so one sentence now carries the same information without an image.

## 2026-08-30 — Branching and deployment policy #decision #architecture

Adopted a shared `main` production branch and persistent `staging` preview
branch for the unified WesFinance Hub portal. Feature branches remain
short-lived. Project-specific production branches will be added only if an
economics project later gets its own Vercel project, release schedule, and
owner; directory boundaries alone are not enough.

## 2026-07-17 — Project Inception #decision #milestone

Established the 30th and final showcase repo as a unified platform for Wesleyan
Business Review, Consulting Pathways, and Foss Hill Financial Group. The exact
tech stack and feature set are still being discussed, but the repository has
been scaffolded.
