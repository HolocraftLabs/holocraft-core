# Holocraft Git Workflow

Holocraft uses a structured branching model designed for:

- AI-assisted parallel development
- stable production deployments
- clean auditable history
- isolated experimentation

---

# Branch Model

## main

Production-stable branch.

Rules:
- no direct commits
- no force pushes
- only receives changes via PR from develop (or hotfix/* for critical fixes)
- CI must pass before merge
- protected

## develop

Integration branch.

Rules:
- all feature work merges here first
- CI must pass before merge
- no force pushes
- protected

## feature/{name}

Isolated feature development.

Rules:
- branch from develop
- merge back into develop via PR
- delete after merge

Examples:
```
feature/hero-section
feature/design-tokens
feature/motion-primitives
```

## fix/{name}

Bug fixes.

Rules:
- branch from develop
- for critical production bugs: branch from main, merge to both main and develop

Examples:
```
fix/font-loading
fix/ci-pipeline
fix/token-resolution
```

## experimental/{name}

Research and prototype work.

Rules:
- not guaranteed to merge into develop
- used for R&D, 3D experiments, motion concepts
- never merges directly to main

Examples:
```
experimental/3d-hero
experimental/gsap-scroll-system
experimental/motion-language
```

---

# Commit Message Format

Holocraft uses Conventional Commits.

Format:
```
{type}: {short description}
```

Types:

| Type | When to use |
|---|---|
| `feat` | New feature or capability |
| `fix` | Bug fix |
| `docs` | Documentation changes only |
| `style` | Formatting, no logic change |
| `refactor` | Code restructure, no feature or fix |
| `perf` | Performance improvement |
| `chore` | Build, tooling, dependency updates |
| `ci` | CI/CD configuration changes |
| `revert` | Reverting a previous commit |

Rules:
- subject line under 72 characters
- lowercase
- no period at end
- present tense (`add` not `added`)
- imperative mood (`fix` not `fixes`)

Examples:
```
feat: add hero section with cinematic reveal
fix: correct geist font variable in root layout
chore: update turborepo to v2.9
ci: remove duplicate pnpm version declaration
docs: add motion system architecture document
refactor: extract animation config into motion package
```

---

# Pull Request Rules

Every PR must:
- have a clear title following commit message format
- target the correct branch (feature/* and fix/* → develop)
- pass all CI checks (lint, type-check, build)
- include a brief description of what changed and why

PRs must not:
- mix unrelated changes
- contain incomplete or broken work
- bypass CI

---

# Merge Strategy

Holocraft enforces linear history on protected branches.

Use squash merge or rebase merge when merging PRs.

Do not create merge commits on main or develop.

This keeps git log readable and bisectable.

---

# What to Never Do

- commit directly to main or develop
- force push to any protected branch
- commit secrets, credentials, or .env files
- use vague commit messages (`fix stuff`, `update`, `wip`)
- mix formatting changes with logic changes in the same commit
- leave branches open after they are merged
