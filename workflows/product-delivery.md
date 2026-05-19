# Holocraft Product Delivery Workflow

This document describes the operational process for delivering a Holocraft product from concept to deployment.

Reference `architecture/product-pipeline.md` for the six-phase pipeline structure.

---

# Starting a New Product

1. Create a product workspace directory: `HOLOCRAFT/workspace/{product-name}/`
2. Create `brief.md` — initial product direction
3. Begin Phase 1 of the Product Pipeline
4. Document all decisions and outputs in the product workspace

---

# Workspace Structure per Product

```
HOLOCRAFT/workspace/{product-name}/
├── brief.md                    Phase 1: product direction and goals
├── research/                   Phase 2: extracted design intelligence
│   ├── visual-dna.md
│   ├── typography.md
│   ├── motion.md
│   └── references.md
├── architecture.md             Phase 3: system blueprint
└── progress.md                 Phase tracking and status
```

---

# Phase Transition Checklist

Use this checklist at each phase gate before proceeding.

## Phase 1 → Phase 2

- [ ] Product direction document written
- [ ] Target audience defined
- [ ] 1–3 primary goals documented
- [ ] Emotional direction selected from Style Taxonomy
- [ ] Success criteria defined
- [ ] Human approval obtained

## Phase 2 → Phase 3

- [ ] Research extraction complete (3–5 sources referenced)
- [ ] Visual DNA documented
- [ ] Typography direction chosen
- [ ] Motion direction chosen
- [ ] Color palette direction defined
- [ ] Human approval obtained

## Phase 3 → Phase 4

- [ ] System blueprint complete
- [ ] All required components listed
- [ ] Design token specification written
- [ ] Motion plan documented
- [ ] Technical stack confirmed
- [ ] Folder structure planned
- [ ] Human approval obtained

## Phase 4 → Phase 5

- [ ] All tokens implemented and working
- [ ] Base components built and tested
- [ ] Motion primitives configured
- [ ] No unresolved architecture questions
- [ ] No open technical blockers

## Phase 5 → Phase 6

- [ ] Prototype reviewed by human
- [ ] Motion sequences validated
- [ ] Responsive behavior confirmed
- [ ] Performance baseline documented
- [ ] Human approval obtained

## Phase 6 → Deploy

- [ ] CI/CD pipeline passing
- [ ] Lighthouse score 90+ across all metrics
- [ ] Core Web Vitals targets met
- [ ] No console errors or warnings in production build
- [ ] Human approval for production deployment

---

# Branch Naming for Product Work

```
feature/{product-name}-p{phase}-{component}
```

Examples:
```
feature/flagship-p4-design-tokens
feature/flagship-p4-typography-system
feature/flagship-p5-hero-section
feature/flagship-p5-motion-reveal
```

---

# AI Agent Instructions

When an AI agent begins product work:

1. Read `brief.md` in the product workspace
2. Read the current phase's required outputs from `architecture/product-pipeline.md`
3. Read all relevant standards from `holocraft-core/standards/`
4. Execute only within the current phase scope
5. Document all outputs in the product workspace
6. Request human review before phase transition

AI agents must not:
- skip phases
- make architecture decisions without documentation
- deploy to production without human approval
- modify foundation systems without explicit instruction
- proceed to the next phase without the checklist being completed
