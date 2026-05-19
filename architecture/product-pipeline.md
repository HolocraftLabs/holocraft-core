# Holocraft Product Pipeline

Every Holocraft product follows a structured six-phase delivery pipeline.

No phase is skipped.

Each phase produces defined outputs before the next phase begins.

Human approval is required at every phase gate.

AI agents assist within phases but do not approve transitions.

---

# Phase 1 — Idea

Objective: define what is being built and for whom.

Inputs:
- client brief or internal product concept

Outputs:
- product direction document
- target audience definition
- primary goals (1–3 clear objectives)
- emotional direction selected from the Style Taxonomy
- success criteria

Gate: human reviews and approves direction before research begins.

---

# Phase 2 — Research

Objective: build design intelligence specific to this product.

Inputs:
- style direction from Phase 1
- target industry
- research system in holocraft-core

Outputs:
- curated reference set (3–5 sources from the research system)
- visual DNA extraction for this product
- typography direction
- motion direction
- color palette direction
- competitive and reference landscape notes

Gate: human reviews and approves research outputs before architecture begins.

---

# Phase 3 — Architecture

Objective: define the complete technical and design system blueprint.

Inputs:
- research outputs from Phase 2
- product goals from Phase 1

Outputs:
- system blueprint (page structure, section map, component inventory)
- design token specification
- component strategy (complete list of required components)
- motion plan (which primitives, which sequences)
- technical stack confirmation
- folder structure plan
- automation flow definition (if applicable)

This phase produces the master reference document.

All subsequent implementation decisions reference this document.

Gate: human reviews and approves the full blueprint before foundation work begins.

---

# Phase 4 — Foundation

Objective: build reusable infrastructure before any production UI.

Inputs:
- architecture outputs from Phase 3

Outputs:
- design tokens implemented and tested
- typography system configured
- color system configured
- spacing system configured
- motion primitives configured
- base component library for this product
- shared utilities and hooks

Phase 5 does not begin until foundation is complete and working.

No shortcuts.

---

# Phase 5 — Prototype

Objective: validate the experience through interactive prototyping.

Inputs:
- foundation from Phase 4
- architecture plan from Phase 3

Outputs:
- interactive cinematic prototype
- motion system demonstrated in context
- key interaction patterns validated
- responsive behavior confirmed across breakpoints
- performance baseline established

Gate: human reviews and approves prototype before production build begins.

---

# Phase 6 — Production

Objective: build, optimize, and deploy the production product.

Inputs:
- approved prototype from Phase 5
- full architecture blueprint from Phase 3

Outputs:
- optimized production application
- CI/CD pipeline configured
- Core Web Vitals targets met
- deployment completed
- monitoring configured
- product documentation updated

Gate: human approval required before production deployment.

---

# Pipeline Rules

Phases are sequential.

No parallel phase execution without explicit approval.

The only permitted overlap: design token work (Phase 4) may begin concurrent with late-stage research (Phase 2) if the token specification is already defined from Phase 3.

Each phase transition requires documented outputs and human sign-off.

AI agents do not approve phase transitions.

---

# AI Responsibilities by Phase

| Phase | AI Role |
|---|---|
| 1 — Idea | Brief analysis, goal extraction, style taxonomy matching |
| 2 — Research | Research extraction, design intelligence synthesis |
| 3 — Architecture | System blueprint drafting, component mapping, token specification |
| 4 — Foundation | Token implementation, component scaffolding, utility generation |
| 5 — Prototype | Prototype assembly, motion implementation, interaction development |
| 6 — Production | Build optimization, CI/CD configuration, deployment scripts |

---

# Note

This document supersedes the workflow section in `docs/studio-structure.md`, which describes an earlier version of the pipeline.

This six-phase model is the current authoritative product delivery process.
