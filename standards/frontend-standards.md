# Holocraft Frontend Standards

## Philosophy

Frontend at Holocraft is not decoration.

It is:
- interaction design
- motion storytelling
- visual engineering
- emotional communication
- system architecture

Every interface must feel:
- intelligent
- immersive
- cinematic
- responsive
- scalable

---

# Core Stack

Mandatory technologies:

- Next.js
- TypeScript
- Tailwind CSS
- Framer Motion
- shadcn/ui

Optional:
- GSAP
- Three.js
- Motion One

---

# Design Language

Holocraft interfaces should feel:

- futuristic
- minimal
- cinematic
- premium
- layered
- fluid

Avoid:
- generic SaaS layouts
- template-like interfaces
- overused gradients
- random animations
- excessive glassmorphism

---

# Component Architecture

Rules:

- reusable first
- isolated logic
- scalable composition
- low coupling
- high readability

Structure example:

components/
├── ui/
├── layout/
├── sections/
├── motion/
├── forms/
└── shared/

---

# Motion Rules

Animation is functional.

Motion should:
- guide attention
- improve hierarchy
- create immersion
- enhance transitions

Avoid:
- random motion
- excessive bounce
- distracting effects

Preferred:
- smooth easing
- layered transitions
- opacity + transform
- cinematic timing

---

# Responsive System

Mandatory breakpoints:

- mobile
- tablet
- desktop
- ultrawide

Interfaces must work smoothly from:
320px → 4K displays.

---

# Performance Rules

Priority:
1. performance
2. responsiveness
3. visual quality

Avoid:
- unnecessary re-renders
- massive dependencies
- heavy animations
- blocking rendering

---

# Accessibility

Every interface must support:
- keyboard navigation
- semantic HTML
- screen readers
- proper contrast

---

# Code Quality

Mandatory:
- strict TypeScript
- clean naming
- modular architecture
- readable logic

Avoid:
- giant components
- duplicated logic
- inline chaos
- deeply nested structures

---

# AI Collaboration

AI must:
- follow existing architecture
- avoid rewriting stable systems
- preserve naming consistency
- prioritize maintainability

Human remains final decision maker.