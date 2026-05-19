# Holocraft Motion System

Motion is a first-class architectural layer at Holocraft.

Motion is not decoration.

Motion communicates:

- state changes
- narrative progression
- emotional direction
- spatial relationships
- interaction feedback
- hierarchy and attention

---

# Motion Philosophy

Every animation must answer: why does this element move?

Acceptable reasons:
- guiding attention toward important content
- communicating a state or context transition
- reinforcing spatial hierarchy
- creating cinematic narrative pacing
- improving perceived performance

Unacceptable reasons:
- "it looks interesting"
- filling visual emptiness
- imitating another website

If there is no clear reason, remove the animation.

---

# Motion Primitives

## Cinematic Reveal

A section or element entering the viewport with cinematic weight.

Characteristics:
- duration: 0.8–1.4s
- easing: deceleration curve
- properties: opacity (0→1) + translateY (40px→0) or scale (0.96→1)
- stagger between child elements: 0.1–0.15s

Use for: hero sections, large feature reveals, above-fold imagery

---

## Stagger Text

Multiple text elements entering in choreographed sequence.

Characteristics:
- per-element duration: 0.5–0.8s
- stagger delay: 0.06–0.1s per element
- easing: deceleration curve
- properties: opacity + translateY

Use for: headlines, list reveals, navigation items, feature bullets

---

## Parallax Depth

Elements moving at different rates relative to scroll velocity.

Characteristics:
- depth layers: background (0.1×), midground (0.3×), foreground (0.5×)
- smooth interpolation via Lenis scroll driver
- no jarring jumps or discontinuities
- movement bounded by parent container

Use for: hero backgrounds, decorative elements, depth scenes

---

## Magnetic Hover

Interactive elements that attract toward the cursor position.

Characteristics:
- magnetic strength: 0.3–0.5 (percentage of maximum displacement)
- smooth spring physics follow
- restore to origin on mouse leave
- bounded magnetic field radius

Use for: primary CTAs, navigation items, interactive cards

---

## Ambient Float

Idle loop animation that gives life to static decorative elements.

Characteristics:
- duration: 3–8s loop
- easing: sine in-out
- amplitude: 8–20px vertical or combined axes
- phase offset between multiple simultaneous elements

Use for: decorative shapes, background elements, feature icons, particles

---

## Page Transition

Full-page choreography when navigating between routes.

Characteristics:
- exit: 0.3–0.4s (fast and intentional)
- enter: 0.5–0.8s (deliberate reveal)
- consistent directional logic throughout the application
- implemented with Framer Motion AnimatePresence

Use for: all route changes in Next.js applications

---

## Scroll Choreography

Multiple elements animated in response to scroll progress.

Characteristics:
- driven by scroll progress (0–1)
- smooth interpolation between keyframes
- section-scoped timelines
- GPU-safe properties only

Use for: storytelling sections, feature walkthroughs, data visualization reveals

---

## Smooth Interpolation

Continuous smooth follow between current and target states.

Characteristics:
- Lenis for global scroll smoothing
- spring physics for interactive state following
- lerp factor: 0.08–0.12 for slow follow, 0.2–0.3 for responsive follow

Use for: cursor followers, scroll progress indicators, position tracking

---

# Timing System

## Duration Scale

```
instant     0ms        No animation — immediate state flip
fast        150ms      Micro-interactions, button states, tooltips
base        300ms      Standard transitions, dropdowns, modals
moderate    500ms      Panel transitions, expanding sections
slow        800ms      Cinematic reveals, section entrances
cinematic   1200ms+    Hero sequences, storytelling moments
```

## Easing Presets

```
ease-out-smooth     cubic-bezier(0.16, 1, 0.3, 1)      Natural deceleration
ease-in-out-smooth  cubic-bezier(0.87, 0, 0.13, 1)     Symmetric, elegant
ease-out-spring     Framer Motion spring physics         Organic response
ease-sharp          cubic-bezier(0.4, 0, 1, 1)          Fast aggressive start
```

---

# Implementation Stack

| Tool | Purpose |
|---|---|
| Framer Motion | React integration, layout animations, gestures, AnimatePresence |
| Lenis | Smooth scroll interpolation and scroll event normalization |
| GSAP | Complex timelines, scroll-triggered sequences (heavy use cases) |
| Three.js / R3F | 3D environments and depth simulations when required |

Default to Framer Motion.

Use GSAP only when Framer Motion is insufficient for the required complexity.

Use Lenis on all productions apps for consistent scroll behavior.

---

# Performance Rules

Only animate GPU-accelerated properties:
- `transform` (translate, scale, rotate)
- `opacity`

Never animate layout-triggering properties:
- `width`, `height`
- `top`, `left`, `bottom`, `right`
- `margin`, `padding`
- `background-color` (use opacity layers instead)

Rules:
- use `will-change` sparingly and remove it after animation completes
- always test on mid-range mobile device simulation
- always test with CPU throttling enabled in dev tools
- respect `prefers-reduced-motion` media query

---

# Accessibility

All motion must respect user preference.

When `prefers-reduced-motion: reduce` is active:

- disable parallax
- reduce duration to near-instant (not zero)
- remove ambient floating loops
- preserve state-change feedback (do not eliminate all motion)

Motion must never:
- cause seizure risk (avoid flashing at frequencies above 3Hz)
- obstruct content access
- prevent keyboard navigation
- auto-play without user initiation for extended sequences
