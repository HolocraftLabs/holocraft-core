# Architecture Assistant Prompts

These prompts guide AI-assisted architecture work for Holocraft projects.

Use these when beginning a new product architecture phase or reviewing existing systems.

---

# System Context Prompt

```
You are an architecture assistant for Holocraft, an AI-native creative engineering studio.

Before beginning any work, read:
- holocraft-core/docs/philosophy.md
- holocraft-core/architecture/product-pipeline.md
- holocraft-core/architecture/repository-structure.md
- holocraft-core/standards/frontend-standards.md

You operate in Phase 3 — Architecture.

Your outputs must be precise, structured, and directly actionable.

You document decisions and trade-offs clearly.

You do not implement — you design the system that will be implemented.

Human approval is required before any architecture document is finalized.
```

---

# Prompt: System Blueprint Generation

```
For the product described in [brief.md], generate a system blueprint.

Include:

Page structure:
- List all pages/routes with purpose and content sections

Section inventory:
- For each page, list all sections (e.g. Hero, Features, Testimonials, CTA, Footer)
- For each section, describe its purpose and content type

Component inventory:
- List all UI components required across all pages
- Categorize as: ui / layout / sections / motion / forms / shared

Design token requirements:
- What color tokens are needed?
- What spacing scale is needed?
- What typography tokens are needed?
- What motion tokens (durations, easings) are needed?

Motion plan:
- Which sections require animation?
- Which motion primitives from the Motion System apply?
- What is the scroll narrative?

Technical notes:
- Rendering strategy per route (static / dynamic / ISR)
- Any third-party integrations required
- Performance considerations

Output as a structured markdown document suitable for `architecture.md` in the product workspace.
```

---

# Prompt: Component Strategy Review

```
Review the component inventory for [product name]:

[paste component list]

For each component, evaluate:
- Is this component reusable across multiple products?
- Does an equivalent component already exist in holocraft-ui?
- Should it be built in packages/ui/ or as a product-specific component?
- What are the props and variant requirements?

Output a categorized component plan:
1. Build in packages/ui/ (reusable)
2. Build as product-specific component
3. Use from existing library (shadcn/ui, etc.)

For each component in category 1 and 2, define:
- Component name
- Props interface (TypeScript)
- Variants required
- Motion behavior (if any)
```

---

# Prompt: Design Token Specification

```
Based on the visual DNA extracted for [product name]:

[paste visual-dna.md content]

Generate a complete design token specification.

Format:

Color Tokens:
- --color-background: [value]
- --color-foreground: [value]
- --color-primary: [value]
- --color-accent: [value]
- [continue for all required colors]

Spacing Tokens (base unit and scale):
- --space-1: [value]
- --space-2: [value]
- [continue scale]

Typography Tokens:
- --font-display: [font stack]
- --font-body: [font stack]
- --font-mono: [font stack]
- --text-xs through --text-7xl: [size scale]

Motion Tokens:
- --duration-fast: [value]
- --duration-base: [value]
- --duration-slow: [value]
- --ease-out-smooth: [cubic-bezier]
- --ease-in-out-smooth: [cubic-bezier]

Output as CSS custom properties compatible with Tailwind CSS v4.
```
