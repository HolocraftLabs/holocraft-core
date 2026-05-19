# Holocraft Repository Architecture

Holocraft uses a multi-repository architecture organized under the HolocraftLabs GitHub organization.

Each repository has a single, non-overlapping responsibility.

Repositories do not duplicate each other's concerns.

---

# Repository Map

```
HolocraftLabs/
├── holocraft-core          Studio governance and design intelligence
├── holocraft-ui            Shared design system
├── holocraft-web           Frontend platform and applications
├── holocraft-agents        AI workflow agents (planned)
└── holocraft-assets        Brand and creative asset library (planned)
```

---

# Repository Responsibilities

## holocraft-core

Role: source of truth

Contains:
- engineering standards
- design principles
- AI governance rules
- motion system architecture
- style taxonomy
- research architecture
- product pipeline documentation
- workflow specifications
- AI prompts library

Does not contain:
- application code
- UI components
- deployment configuration

All other repositories must align with the standards defined here.

When standards conflict with implementation, standards win.

---

## holocraft-ui

Role: shared design system

Contains:
- design tokens (color, spacing, typography, shadows, radii, motion)
- base UI components
- motion primitives
- interaction patterns
- theme system (light, dark, brand variants)
- shared frontend utilities

Does not contain:
- application-specific components
- page-level layouts
- routing or data-fetching logic

Consumed by: holocraft-web and all future product repositories.

Must remain presentation-agnostic and brand-flexible.

---

## holocraft-web

Role: frontend platform and application layer

Contains:
- flagship studio website
- experimental applications
- product frontends
- research-driven UI work
- monorepo shared packages

Structure:
- `apps/` for deployable applications
- `packages/` for internal shared packages

Consumes: design tokens and components from holocraft-ui (when available)

---

## holocraft-agents (planned)

Role: AI automation and workflow orchestration

Will contain:
- n8n workflow definitions
- AI agent configurations
- automation scripts
- pipeline orchestration systems

Dependencies: none (orchestrates other systems, not consumed by them)

---

## holocraft-assets (planned)

Role: creative resource library

Will contain:
- brand logos and identity assets
- photography and video
- icon systems
- motion assets and video loops

---

# Dependency Flow

```
holocraft-core      ← read by all (governance only, no code)
holocraft-ui        → consumed by holocraft-web and product repos
holocraft-web       → consumes holocraft-ui
holocraft-agents    → orchestrates holocraft-web deployments
holocraft-assets    → consumed by all when needed
```

Invalid directions:
- holocraft-core depending on any code repository
- holocraft-ui depending on holocraft-web
- circular dependencies between any repositories

---

# Adding a New Repository

A new repository should only be created when:

1. The responsibility is clearly distinct from all existing repositories
2. The content cannot fit within an existing repository's scope
3. The repository has a defined long-term purpose

New repositories must:
- follow the standard `.gitignore` template
- include a meaningful `README.md`
- use SSH remote protocol
- have branch protection configured on `main`
- be documented in this file immediately upon creation
