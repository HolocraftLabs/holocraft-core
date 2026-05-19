# Holocraft Design Principles

Holocraft designs systems, not pages.

Every visual decision must serve:

- emotional communication
- functional clarity
- architectural consistency
- brand identity
- cinematic experience

---

# Core Principles

## 1. Intention Over Decoration

Every visual element must have a reason to exist.

Remove anything that does not contribute to:

- hierarchy
- clarity
- emotion
- function

Decoration without purpose creates noise.

---

## 2. Brand-Specific Identity

No two Holocraft products should look identical.

Every product must express:

- a distinct visual language
- a unique emotional direction
- a specific design personality

Reference the Style Taxonomy to define visual direction before any implementation begins.

---

## 3. Typography as Architecture

Typography is not styling.

Typography systems must define:

- hierarchy
- rhythm
- readability
- emotional tone
- scale

Every interface requires a deliberate type scale before components are built.

---

## 4. Spacing as Rhythm

Spacing is not arbitrary margin values.

Spacing systems must create:

- visual rhythm
- breathing room
- compositional balance
- hierarchy clarity

Use a consistent spacing scale derived from the design token system.

---

## 5. Color as Communication

Color choices must communicate:

- brand identity
- emotional direction
- hierarchy
- interactive state
- environmental context

Avoid random color selections.

Define a complete token-based color system before implementation begins.

---

## 6. Motion as First-Class Layer

Motion is architectural, not cosmetic.

Motion must:

- guide attention
- communicate state changes
- create cinematic rhythm
- reinforce interaction

Reference the Motion System for primitives, timing, and rules.

---

## 7. Composition Over Complexity

Well-composed simple layouts outperform complex cluttered ones.

Composition principles:

- clear visual focal points
- deliberate whitespace
- layered depth
- guided eye movement

---

## 8. Consistency Through Systems

Individual components are never styled in isolation.

All visual decisions must reference:

- design tokens
- spacing systems
- typography scales
- motion primitives

Consistency comes from systems, not discipline alone.

---

## 9. Performance Is Part of Design

Visual quality that destroys performance is not acceptable.

Design decisions must consider:

- animation frame rates
- rendering complexity
- asset weight
- perceived performance

Fast products feel better than slow beautiful ones.

---

## 10. Accessibility Is Baseline Quality

Every interface must support:

- sufficient color contrast (WCAG AA minimum)
- keyboard navigability
- screen reader compatibility
- responsive behavior from 320px to 4K

Accessibility is not a feature added at the end.

Accessibility is the minimum bar for a production-quality product.

---

# Implementation Order

Design work at Holocraft follows this sequence:

1. Define visual direction using the Style Taxonomy
2. Establish token system (colors, spacing, typography)
3. Define motion direction
4. Design component system
5. Implement and iterate

Never implement before the system is defined.

Architecture always precedes production.
