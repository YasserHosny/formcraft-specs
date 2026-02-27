# FormCraft – Universal Form Designer & Print Studio

Enterprise-grade web application for designing printable form templates with multilingual support (Arabic-first), pixel-perfect PDF export, and AI-powered smart control suggestions.

**Domain**: [formcraft.iron-sys.com](https://formcraft.iron-sys.com)

## Architecture

```
┌─────────────────────┐     ┌─────────────────────┐     ┌──────────────┐
│  formcraft-frontend │────▶│  formcraft-backend   │────▶│   Supabase   │
│  Angular + Material │     │  Python FastAPI      │     │   Cloud      │
│  Konva.js Canvas    │     │  WeasyPrint PDF      │     │   Auth + DB  │
│  Bunny Container    │     │  AWS Bedrock AI      │     │   Storage    │
└─────────────────────┘     │  Bunny Container     │     └──────────────┘
                            └─────────────────────┘
```

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Angular (LTS) + Angular Material + Pure Konva.js |
| Backend | Python 3.12 + FastAPI |
| Database | Supabase Cloud (PostgreSQL + Auth + Storage) |
| PDF | WeasyPrint (server-side HTML→PDF) |
| AI | AWS Bedrock (abstracted via LLMProvider interface) |
| Hosting | Bunny Magic Containers |
| CI/CD | Bunny built-in CI |

## Repository Structure

This is a **polyrepo** project with three repositories:

| Repo | Purpose |
|------|---------|
| **formcraft-specs** (this repo) | Specifications, plans, task breakdowns, constitution |
| **formcraft-frontend** | Angular application |
| **formcraft-backend** | Python FastAPI application |

## Specifications

| # | Feature | Priority | Spec | Plan | Tasks |
|---|---------|----------|------|------|-------|
| 01 | Auth & Users | P1 | [spec](specs/01-auth-users/spec.md) | [plan](specs/01-auth-users/plan.md) | [tasks](specs/01-auth-users/tasks.md) |
| 02 | i18n & RTL | P1 | [spec](specs/02-i18n-rtl/spec.md) | [plan](specs/02-i18n-rtl/plan.md) | [tasks](specs/02-i18n-rtl/tasks.md) |
| 03 | Template Model | P1 | [spec](specs/03-template-model/spec.md) | [plan](specs/03-template-model/plan.md) | [tasks](specs/03-template-model/tasks.md) |
| 04 | Design Studio | P1 | [spec](specs/04-design-studio/spec.md) | [plan](specs/04-design-studio/plan.md) | [tasks](specs/04-design-studio/tasks.md) |
| 05 | AI Suggestion | P2 | [spec](specs/05-ai-suggestion/spec.md) | [plan](specs/05-ai-suggestion/plan.md) | [tasks](specs/05-ai-suggestion/tasks.md) |
| 06 | PDF Engine | P2 | [spec](specs/06-pdf-engine/spec.md) | [plan](specs/06-pdf-engine/plan.md) | [tasks](specs/06-pdf-engine/tasks.md) |
| 07 | Arabic Validators | P2 | [spec](specs/07-arabic-validators/spec.md) | [plan](specs/07-arabic-validators/plan.md) | [tasks](specs/07-arabic-validators/tasks.md) |
| 08 | Security & Audit | P3 | [spec](specs/08-security-audit/spec.md) | [plan](specs/08-security-audit/plan.md) | [tasks](specs/08-security-audit/tasks.md) |
| 09 | Perf & Hardening | P3 | [spec](specs/09-perf-hardening/spec.md) | [plan](specs/09-perf-hardening/plan.md) | [tasks](specs/09-perf-hardening/tasks.md) |

## Key Principles

See [CONSTITUTION.md](CONSTITUTION.md) for the full set. Highlights:

1. **Arabic-First, RTL-Native** – Default direction is RTL
2. **Pixel-Perfect Print** – Absolute mm positioning, no auto-scaling
3. **AI Suggest, Never Auto-Apply** – User always confirms
4. **Deterministic Over Probabilistic** – Hard-coded validators override AI
5. **Test-First** – TDD mandatory

## Getting Started

1. Review the [Constitution](CONSTITUTION.md)
2. Read the specs in priority order (01 → 04 first)
3. Set up the frontend and backend repos
4. Follow the task breakdowns in each spec's `tasks.md`

## Timeline

| Weeks | Phase |
|-------|-------|
| 1 | Project bootstrap (scaffolds, Supabase, Docker) |
| 2–3 | Auth, i18n/RTL, Template model |
| 4–6 | Design Studio (Konva canvas) |
| 7 | AI Smart Suggestion |
| 8–9 | PDF engine + Arabic validators |
| 10 | Security & audit |
| 11 | Testing + performance |
| 12 | Production hardening & deployment |
