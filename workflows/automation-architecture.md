# Holocraft Automation Architecture

Automation at Holocraft handles repetitive and orchestratable tasks across the product pipeline.

Automation augments human work.

Automation does not replace human judgment or architectural decisions.

---

# Automation Principles

Every automated system must support:

- logging — every action is recorded with timestamp and context
- rollback — every automated change can be reversed
- auditability — clear record of what happened, when, and why
- approval checkpoints — human confirmation required for critical actions

Automation must never:

- deploy to production without human approval
- modify architecture or standards documents autonomously
- commit directly to main or develop
- send client-facing output without review
- make product decisions

---

# Automation Layers

## Layer 1 — GitHub Actions

Responsibility: code quality enforcement and deployment pipeline

Active workflows:
- CI pipeline: lint, type-check, build on PR and push to main/develop

Planned workflows:
- Preview deployment on feature branch push
- Production deployment on merge to main (with approval gate)
- Dependency update notifications

Location: `.github/workflows/` in each repository

---

## Layer 2 — n8n

Responsibility: workflow orchestration and AI pipeline integration

Location: `HOLOCRAFT/services/n8n/docker-compose.yml`

Planned workflows:
- Research extraction pipeline (AI-assisted source analysis)
- Client brief processing and intelligence extraction
- Asset and content synchronization
- Documentation generation and updates
- Notification and status reporting

---

## Layer 3 — AI Agents

Responsibility: intelligent task execution within approved scopes

Current capabilities:
- architecture analysis and documentation
- code generation within established constraints
- research extraction and structuring
- component scaffolding
- documentation drafting

Constraints:
- operates within the current phase scope only
- requires human approval for all architecture changes
- no direct production deployment authority
- all outputs are reviewed before committing

---

# n8n Configuration

Current state:
- image: `n8nio/n8n:latest`
- port: `5678`
- timezone: `Asia/Ho_Chi_Minh`
- storage: Docker volume (SQLite default)

Production upgrade path:

1. Pin n8n to a specific version (not `latest`)
2. Replace SQLite with PostgreSQL for scale and reliability
3. Add Redis for queue management
4. Configure `WEBHOOK_URL` environment variable for external triggers
5. Set up proper environment variable management

---

# Workflow Standards

Every n8n workflow must:

- have a descriptive, human-readable name
- include error handling and failure notifications
- log all operations with context
- have an isolated test mode
- be documented in this directory

---

# Secrets Management

All automation secrets and credentials must:

- be stored in environment variables only
- never be committed to any repository
- use `.env.example` to document required variable names without values
- be rotated immediately on suspected exposure

---

# Automation Roadmap

| Phase | Capability | Status |
|---|---|---|
| 1 | GitHub Actions CI/CD | Active |
| 2 | n8n service running | Pending |
| 3 | Research extraction pipeline | Planned |
| 4 | n8n + AI agent integration | Planned |
| 5 | Automated component scaffolding | Planned |
| 6 | Full product generation pipeline | Future |
