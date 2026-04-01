---
name: AI Ready U: Life
description: >
  15 AI agents that manage your personal life — tax, health, wealth, career,
  legal, insurance, business, estate, home, family, learning, mind, explore,
  and vehicles. Orchestrated by a Chief of Staff. Includes 12 tool skills.
  Agent instructions and vault available on Gumroad.
slug: aireadyu-life
schema: agentcompanies/v1
version: 2.0.0
license: MIT
authors:
  - name: fru.dev
goals:
  - Help individuals organize every area of their life so AI can actually work for them
  - Provide domain-specific AI agents with deep expertise and cross-domain coordination
  - Keep everything private, local, and vendor-neutral
---

# AI Ready U: Life

**15 AI agents. 14 life domains. 12 skills. 1 Chief of Staff. Private. On your machine.**

AI Ready U: Life is a company of AI agents that manage your entire personal life. Each agent is a domain expert — tax strategy, wealth management, health monitoring, career growth, and more. The Chief of Staff orchestrates everything, produces daily briefs, and ensures nothing falls through the cracks.

## What's Free

- **15 agents** — Chief of Staff + 14 domain agents with budgets and capabilities
- **12 tool skills** — Gmail, Calendar, Drive, Storage, Port, Workflow, Contacts, Documents, Research, Writing, Booking, Analytics
- **Vault schema** — vault-structure.json showing the 14-domain architecture
- **Bootstrap tasks** — agents self-initialize on first run

## What's Paid ($29)

The agents need **instructions** and a **vault** (your documents) to do real work. Get both in the AI Ready U: Life pack:

**[Get AI Ready U: Life on Gumroad → $29](https://fruverse.gumroad.com/l/aireadyu-life)**

The pack includes:
- Full agent instructions for all 15 agents (100+ lines each with domain expertise)
- 14-domain vault pre-filled with synthetic data
- 200+ ready-to-use prompts
- Context files for Claude, Gemini, and Cursor

After purchase, extract to `~/Documents/AIReadyU-Life/` and switch each agent from Managed to External in the Paperclip dashboard.

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-life --include company,agents,skills
```

## The 15 Agents

| Agent | Title | Budget |
|-------|-------|--------|
| Chief of Staff | Life Operations Director | $50/mo |
| Tax Agent | Chief Tax Officer | $20/mo |
| Health Agent | Chief Medical Officer | $20/mo |
| Wealth Agent | Chief Capital Officer | $20/mo |
| Career Agent | Chief Talent Officer | $20/mo |
| Legal Agent | Chief Legal Officer | $15/mo |
| Business Agent | Chief Corporate Officer | $20/mo |
| Insurance Agent | Chief Risk Officer | $10/mo |
| Estate Agent | Chief Property Officer | $10/mo |
| Home Agent | Chief Household Officer | $5/mo |
| Family Agent | Chief Family Officer | $10/mo |
| Learning Agent | Chief Learning Officer | $5/mo |
| Mind Agent | Chief Mindfulness Officer | $5/mo |
| Explore Agent | Chief Adventure Officer | $5/mo |
| Vehicles Agent | Chief Fleet Officer | $5/mo |

## Part of AI Ready U

AI Ready U helps individuals and businesses organize their world so AI can actually work for them.

- Website: [aireadyu.dev](https://aireadyu.dev)
- YouTube: [youtube.com/@frudev](https://youtube.com/@frudev)
- Built by [fru.dev](https://fru.dev)
