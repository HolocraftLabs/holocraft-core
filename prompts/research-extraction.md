# Research Extraction Prompts

These prompts guide AI-assisted extraction of design intelligence from reference sources.

Use these prompts when populating `docs/research/{source}/` files in holocraft-web.

---

# System Context Prompt

Use this as the base system instruction when beginning any research extraction session.

```
You are a design intelligence analyst for Holocraft, an AI-native creative engineering studio.

Your task is to analyze a reference website or design source and extract structured design intelligence.

You extract observable patterns only.
You do not write vague impressions or marketing language.
You do not copy descriptions from the source itself.
You write specific, measurable, actionable information.

Output format must follow the Holocraft research architecture defined in:
holocraft-core/systems/research-architecture.md

Each output section corresponds to one of the six research files:
overview, visual-dna, typography, motion, interactions, prompts.
```

---

# Prompt: Overview Extraction

```
Analyze [source name] and document:

1. What this source represents and its position in the design world
2. The core design philosophy it embodies
3. The industries and brand types it serves
4. The emotional direction and intended audience experience
5. What Holocraft can specifically learn from it
6. Any patterns that are overused or should be avoided

Be specific. Avoid vague praise.
```

---

# Prompt: Visual DNA Extraction

```
Analyze the visual design of [source] and extract:

Color system:
- Primary background color (hex if identifiable)
- Primary foreground/text color
- Accent colors and their usage contexts
- Surface and card colors

Grid and layout:
- Column count on desktop
- Maximum content width
- Gutter size (approximate)
- Margin behavior at breakpoints

Density and spacing:
- Content density level: sparse / balanced / dense
- Apparent base spacing unit
- Spacing between major sections

Imagery:
- Photography treatment and style
- Illustration approach (if present)
- Absence of imagery as a design choice

Surface aesthetic:
- Flat / elevated / glass / textured / material-referencing

Output as structured data suitable for design token generation.
```

---

# Prompt: Typography System Extraction

```
Analyze the typography in [source] and extract:

Display typeface:
- Name or classification (geometric sans, humanist serif, etc.)
- Weights used for headlines
- Approximate size range (largest headline to smallest display text)
- Letter-spacing behavior

Body typeface:
- Name or classification
- Weight used for body text
- Line-height (normal / tight / loose)
- Optimal reading column width

Supporting typefaces:
- Monospace usage (code, labels, data)
- Any accent or secondary typeface

Scale:
- Approximate ratio between headline levels
- Body size (16px equivalent?)
- Label and caption sizing

Hierarchy strategy:
- What elements differentiate heading levels (size, weight, color, spacing)

Output in a format suitable for typography token definition.
```

---

# Prompt: Motion Analysis

```
Analyze the motion and animation present in [source] and extract:

Overall motion personality:
- Describe in 3–5 adjectives (e.g. slow, weighted, cinematic)

Entrance animations:
- How do elements appear on page load?
- How do elements appear on scroll into view?

Scroll behavior:
- Is scroll smooth or native?
- Are there scroll-linked animations?
- Is there parallax or depth behavior?

Hover responses:
- How do interactive elements respond to hover?
- Is the response subtle or dramatic?

Page transitions:
- Does the site use page transitions?
- What is the style and duration?

Signature motion:
- What is the single most distinctive animation moment?

Timing character:
- Are transitions fast and snappy or slow and weighted?

Easing character:
- Bouncy / smooth / sharp / elastic?

Output as motion system specifications referencing Holocraft motion primitives where applicable.
```

---

# Prompt: Interaction Pattern Extraction

```
Analyze the interaction patterns in [source] and extract:

Navigation:
- Navigation structure and visual approach
- Menu open/close behavior and animation

Scroll:
- Scroll behavior: native / smooth / snap / custom

Button interactions:
- Hover state visual response
- Active/pressed state
- Focus state visibility

Card interactions:
- Hover behavior (elevation, image, overlay, scale)
- Click/tap response

Cursor:
- Default browser cursor or custom cursor?
- Cursor behavior changes on interactive elements?

Micro-interactions:
- Form field feedback
- Loading state approach
- State change confirmations

Document as specific patterns, not general descriptions.
```

---

# Prompt: Component Prompt Generation

```
Based on the extracted design intelligence from [source], generate AI component prompts.

For each of the following components observed in the source:
Hero, Navigation, Feature Section, Card, CTA Section, Footer

Generate a prompt in this exact format:

### {Component Name}

Style Reference: [source name]
Visual: 
- [specific visual characteristic 1]
- [specific visual characteristic 2]
- [specific visual characteristic 3]
Motion:
- [specific motion behavior 1]
- [specific motion behavior 2]
Typography:
- [relevant typeface and size spec]
Color Context:
- [relevant color usage]
Instruction: Generate a [component description] that captures the visual language of [source] using Next.js, TypeScript, Tailwind CSS v4, and Framer Motion.

Generate prompts for all major components.
Be specific enough that a developer or AI agent can implement without ambiguity.
```
