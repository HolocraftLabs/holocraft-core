# Holocraft Performance Rules

Performance is a first-class product value at Holocraft.

A slow product is a failed product regardless of visual quality.

Performance must be considered at architecture time, not after deployment.

---

# Core Web Vitals Targets

Every production Holocraft product must meet these minimum thresholds:

| Metric | Target |
|---|---|
| LCP (Largest Contentful Paint) | < 2.5s |
| INP (Interaction to Next Paint) | < 200ms |
| CLS (Cumulative Layout Shift) | < 0.1 |
| FCP (First Contentful Paint) | < 1.8s |
| TTFB (Time to First Byte) | < 600ms |

These are not aspirational targets.

They are minimum requirements for production deployment.

---

# Bundle Size Guidelines

JavaScript:
- Initial JS bundle: < 200KB gzipped
- Per-route JS: < 100KB gzipped
- Audit all third-party dependencies before adding

CSS:
- Total CSS: < 50KB gzipped
- Tailwind CSS purging must be enabled in production

---

# Image and Media Rules

- Always use Next.js `Image` component for automatic optimization
- Provide explicit `width` and `height` to prevent layout shift (CLS)
- Use WebP or AVIF formats
- Lazy load all images below the fold
- Use blur placeholder for large above-fold images
- Never serve unoptimized original images directly

---

# Font Loading

- Use `next/font` for all fonts (automatic optimization and self-hosting)
- Preload critical fonts used in above-fold content
- Use `font-display: swap`
- Load only the weights actually used in the design
- Never load fonts from external CDNs without subsetting

---

# Animation Performance

Motion must not degrade rendering performance.

Rules:
- only animate `transform` and `opacity` (GPU-accelerated properties)
- never animate `width`, `height`, `top`, `left`, `margin`, `padding`
- use `will-change` sparingly and remove it after animation completes
- target 60fps minimum on all devices
- target 120fps on capable displays
- reduce animation complexity when `prefers-reduced-motion` is active
- always test animations on mid-range mobile device simulation

---

# React Performance

- avoid unnecessary re-renders in all components
- use `React.memo` for expensive components that receive stable props
- use `useCallback` and `useMemo` only when measured as necessary — not preemptively
- split large component trees into smaller focused units
- use `next/dynamic` for heavy components not needed on initial load
- prefer server-side data fetching over client-side when possible

---

# Rendering Strategy

Choose the correct rendering model per route:

| Strategy | When to use |
|---|---|
| Static (SSG) | Marketing pages, landing pages, documentation |
| Dynamic (SSR) | Authenticated, personalized, or real-time content |
| Client (CSR) | Highly interactive views where SEO is not a concern |
| ISR | Content that updates periodically (blog, portfolio) |

Default to static unless there is a documented reason not to.

---

# Third-Party Scripts

- audit every external script for performance impact before adding
- load non-critical scripts with `strategy="lazyOnload"`
- never block the main thread with analytics or tracking
- use Partytown for offloading heavy third-party scripts when necessary

---

# Performance Validation

Before merging any significant UI change:

1. Run Lighthouse audit — target 90+ on all metrics
2. Check bundle analyzer for unexpected size increases
3. Test on Slow 4G network throttle
4. Test on mid-range mobile device simulation

Performance regressions must be fixed before merge to main.

No exceptions.
