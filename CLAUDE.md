# CLAUDE.md — holocraft-core

This repository is the **source of truth** for the entire Holocraft studio ecosystem.

## Role

`holocraft-core` governs all engineering decisions across every repo in HolocraftLabs. Before modifying any file here, understand the impact: these documents define how AI agents and human engineers behave across the entire system.

## What this repo contains

- `docs/` — Vision, philosophy, studio structure
- `standards/` — Engineering rules (frontend, AI coding, performance, design)
- `systems/` — AI hierarchy and governance
- `architecture/` — System architecture decisions (in progress)
- `prompts/` — Reusable AI prompts (in progress)
- `workflows/` — Operational workflows (in progress)
- `templates/` — Project templates (in progress)
- `branding/` — Brand identity assets (in progress)

## Critical rule

**Never modify these documents without explicit instruction from the studio owner.**

These are governance documents, not code. Changes here propagate to every project.

## Key references

- Engineering philosophy: `docs/philosophy.md`
- Studio vision: `docs/vision.md`
- AI agent roles: `systems/ai-hierarchy.md`
- Frontend stack: `standards/frontend-standards.md`
- AI coding behavior: `standards/ai-coding-rules.md`

## Git

- Branch: `main` only
- Remote: `git@github.com:HolocraftLabs/holocraft-core.git`
- All commits must have meaningful messages describing why, not what
