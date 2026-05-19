# Holocraft Research Architecture

The research system is the design intelligence layer of the studio.

Research is not inspiration collection.

Research is structured intelligence extracted from reference sources and formatted for AI consumption and reuse.

---

# Purpose

The research system enables:

- AI-readable visual language extraction
- style-specific design decision support
- evidence-based component and token generation
- consistent design intelligence across all products

Without a populated research system, AI-assisted design generation has no foundation.

---

# Research Source Structure

Each research source lives in:

```
docs/research/{source-name}/
```

Each source directory contains exactly six files:

```
overview.md        General approach, design philosophy, emotional direction
visual-dna.md      Core visual characteristics, grid, density, composition
typography.md      Type system, scale, weights, font choices, spacing
motion.md          Animation patterns, timing, interaction choreography
interactions.md    User interaction patterns, hover states, micro-interactions
prompts.md         AI generation prompts derived from this source
```

All six files must be present and complete before a source is considered ready for use.

---

# File Content Format

## overview.md

Answer these questions:

- What is this source and what does it represent?
- What design philosophy does it embody?
- What industries or brands does it serve?
- What is the emotional direction?
- What does it do exceptionally well that Holocraft can learn from?
- What are the limitations or overused patterns to avoid?

---

## visual-dna.md

Extract and document:

- Color palette: primary, secondary, accent, background, surface colors (hex if identifiable)
- Grid system: column count, gutter sizing, max-width, margin behavior
- Content density: sparse / balanced / dense
- Spacing rhythm: apparent base unit and scale pattern
- Imagery style: photography treatment, illustration style, or absence
- Surface aesthetic: flat, elevated, glass, textured, material-referencing

---

## typography.md

Extract and document:

- Display typeface: name, weight used, size range, tracking behavior
- Body typeface: name, weight, line-height, optimal reading width
- Supporting typefaces: monospace, accent, or secondary family if present
- Heading scale: approximate size ratios across h1–h4
- Hierarchy approach: how size, weight, color, and spacing distinguish levels

---

## motion.md

Extract and document:

- Overall motion personality: fast or slow, aggressive or gentle, cinematic or functional
- Entrance animation style: how content appears on load and scroll
- Scroll behavior: smooth, snap, scroll-linked animation presence
- Hover response style and intensity
- Page transition approach
- Signature motion moment: the single most memorable animation pattern
- Timing character: snappy or weighted
- Easing character: bouncy, smooth, sharp, or elastic

---

## interactions.md

Extract and document:

- Navigation behavior: menu type, open/close mechanism
- Scroll interaction: native, smooth, snap, or custom
- Button states: hover, active, focus behavior
- Card interactions: hover treatment, image response, overlay behavior
- Cursor behavior: default or custom cursor presence
- Micro-interactions: form feedback, loading states, state change animations

---

## prompts.md

AI-ready prompts generated from the extracted intelligence.

Format for each component prompt:

```
### {Component Name}

Style: {source name}
Visual: {bullet list of visual characteristics}
Motion: {bullet list of motion characteristics}
Typography: {relevant type spec}
Color context: {relevant color spec}
Instruction: Generate a [component description] in this visual language.
```

Include prompts for: Hero, Navigation, Feature Section, Card, Footer, and any signature components observed in the source.

---

# Current Sources

| Source | Status |
|---|---|
| awwwards | Empty — pending extraction |
| behance | Empty — pending extraction |
| bootstrapmade | Empty — pending extraction |
| designprompts | Empty — pending extraction |
| google-labs | Empty — pending extraction |
| mdx | Empty — pending extraction |
| mobbin | Empty — pending extraction |
| pageflows | Empty — pending extraction |

---

# Planned Sources

| Source | Priority | Style Direction |
|---|---|---|
| stripe | High | Product-Focused, Minimal |
| apple | High | Luxury, Cinematic |
| framer | High | Motion-Heavy, Futuristic |
| linear | Medium | Minimal, Product-Focused |

---

# How to Add a New Research Source

1. Create directory: `docs/research/{source-name}/`
2. Create all six standard files
3. Complete each file following the format above
4. Update the Current Sources table in this document
5. Commit with: `docs: add research extraction for {source-name}`

---

# Quality Standards

Each research entry must be:

- specific and measurable, not vague
- based on observable patterns, not subjective impressions
- structured for AI consumption (consistent, parseable)
- actionable — leads directly to design or token decisions

Avoid:
- vague adjectives without specifics (`beautiful`, `clean`, `modern`)
- marketing descriptions copied from the source's own website
- incomplete entries with placeholder text
- personal opinions presented as design analysis
