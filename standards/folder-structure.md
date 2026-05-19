# Holocraft Folder Structure Standards

Consistent folder structure across all repositories ensures:

- predictable navigation
- AI-assisted development efficiency
- scalable organization
- team clarity

Every repository follows a defined structure.

No ad-hoc directories.

---

# Monorepo Root — holocraft-web

```
holocraft-web/
├── apps/                         Deployable applications
│   └── {app-name}/               Individual Next.js application
├── packages/                     Internal shared packages
│   ├── ui/                       Shared UI component library
│   ├── design-tokens/            Token system (color, spacing, type)
│   ├── motion/                   Motion primitives and animation presets
│   ├── typescript-config/        Shared TypeScript configuration bases
│   ├── eslint-config/            Shared ESLint rule sets
│   └── config/                   Shared tooling configurations
├── services/                     External service configurations
├── tooling/                      Internal development scripts
├── infrastructure/               Deployment and infrastructure configs
├── docs/
│   └── research/                 Design intelligence research per source
└── .github/
    └── workflows/                GitHub Actions CI/CD pipelines
```

---

# Application Structure — apps/{app-name}

```
{app-name}/
├── app/                          Next.js App Router root
│   ├── (routes)/                 Route groups
│   ├── layout.tsx                Root layout
│   ├── page.tsx                  Root page
│   └── globals.css               Global styles and token references
├── components/
│   ├── ui/                       Primitive UI components (Button, Input, etc.)
│   ├── layout/                   Layout components (Header, Footer, Nav)
│   ├── sections/                 Page section components (Hero, Features, etc.)
│   ├── motion/                   Motion and animation components
│   ├── forms/                    Form components
│   └── shared/                   Shared cross-section components
├── lib/                          Utilities, helpers, constants
├── hooks/                        Custom React hooks
├── types/                        TypeScript type definitions
├── public/                       Static assets
└── content/                      Static content (MDX, JSON)
```

---

# Package Structure — packages/{package-name}

```
{package-name}/
├── src/                          Source files
├── dist/                         Build output (gitignored)
├── package.json
├── tsconfig.json
└── README.md
```

---

# Naming Conventions

## Files

- React components: `PascalCase` — `HeroSection.tsx`
- Utilities and hooks: `camelCase` — `useScrollPosition.ts`
- Type definition files: `PascalCase` — `MotionConfig.ts`
- Configuration files: `kebab-case` — `tailwind.config.ts`
- Constants: `camelCase` or `SCREAMING_SNAKE_CASE` — `breakpoints.ts`

## Directories

All directory names use `kebab-case`.

Route directories follow URL convention (`kebab-case`).

## Components

Simple components: single file `ComponentName.tsx`

Complex components with sub-parts:

```
ComponentName/
├── index.tsx
├── ComponentName.tsx
└── ComponentName.types.ts
```

---

# Import Path Aliases

Use path aliases to avoid relative import chains.

Standard alias configuration:

```
@/*  →  root of the application
```

Examples:

```ts
import { Button } from '@/components/ui/Button'
import { tokens } from '@/lib/tokens'
import type { MotionConfig } from '@/types/motion'
```

Configure in `tsconfig.json` paths and `next.config.ts`.

---

# What to Avoid

- deeply nested component hierarchies beyond 3 levels
- placing business logic directly in page files
- generic catch-all folders with unrelated files
- mixing different concerns in a single file
- inconsistent naming within the same file type
- creating new directories without a clear long-term purpose
