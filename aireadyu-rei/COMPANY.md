---
name: AI Ready U: Real Estate
description: >
  11 AI agents that manage your real estate investment portfolio — properties,
  acquisitions, tenants, maintenance, financing, taxes, insurance, legal,
  accounting, and market research. Orchestrated by a Portfolio Director.
  Includes 12 tool skills. Agent instructions and vault available on Gumroad.
slug: aireadyu-rei
schema: agentcompanies/v1
version: 2.0.0
license: MIT
authors:
  - name: fru.dev
goals:
  - Help real estate investors organize every property and process so AI can actually work for them
  - Provide domain-specific AI agents with deep expertise and cross-domain coordination
  - Keep everything private, local, and vendor-neutral
---

# AI Ready U: Real Estate

**11 AI agents. 10 REI domains. 12 skills. 1 Portfolio Director. Private. On your machine.**

AI Ready U: Real Estate is a company of AI agents that manage your entire real estate investment portfolio. Each agent is a domain expert — property management, tenant relations, maintenance coordination, financing strategy, and more. The Portfolio Director orchestrates everything, produces portfolio dashboards, and ensures nothing falls through the cracks.

## What's Free

- **11 agents** — Portfolio Director + 10 domain agents with budgets and capabilities
- **12 tool skills** — Gmail, Calendar, Drive, Storage, Port, Workflow, Contacts, Documents, Research, Writing, Booking, Analytics
- **Vault schema** — vault-structure.json showing the 10-domain architecture
- **Bootstrap tasks** — agents self-initialize on first run

## What's Paid ($29)

The agents need **instructions** and a **vault** (your documents) to do real work. Get both in the AI Ready U: Real Estate pack:

**[Get AI Ready U: Real Estate on Gumroad → $29](https://fruverse.gumroad.com/l/aireadyu-rei)**

The pack includes:
- Full agent instructions for all 11 agents (100+ lines each with domain expertise)
- 10-domain vault pre-filled with synthetic data
- 200+ ready-to-use prompts
- Context files for Claude, Gemini, and Cursor

After purchase, extract to `~/Documents/AIReadyU-REI/` and switch each agent from Managed to External in the Paperclip dashboard.

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-rei --include company,agents,skills
```

## The 11 Agents

| Agent | Title | Budget |
|-------|-------|--------|
| Chief of Staff | Portfolio Director | $50/mo |
| Properties Agent | Property Manager | $20/mo |
| Acquisitions Agent | Acquisitions Director | $20/mo |
| Tenants Agent | Tenant Relations Director | $10/mo |
| Maintenance Agent | Maintenance Director | $10/mo |
| Financing Agent | Financing Director | $20/mo |
| Taxes Agent | Tax Director | $10/mo |
| Insurance Agent | Insurance Director | $10/mo |
| Legal Agent | Legal Director | $10/mo |
| Accounting Agent | Accounting Director | $20/mo |
| Market Agent | Market Research Director | $10/mo |

## Part of AI Ready U

AI Ready U helps individuals and businesses organize their world so AI can actually work for them.

- Website: [aireadyu.dev](https://aireadyu.dev)
- YouTube: [youtube.com/@frudev](https://youtube.com/@frudev)
- Built by [fru.dev](https://fru.dev)
