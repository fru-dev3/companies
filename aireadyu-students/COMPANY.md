---
name: AI Ready U: Students
description: >
  10 AI agents that manage your student life — academics, research, career,
  finance, health, social, skills, housing, and admin.
  Orchestrated by a Chief of Staff. Includes 12 tool skills.
  Agent instructions and vault available on Gumroad.
slug: aireadyu-students
schema: agentcompanies/v1
version: 2.0.0
license: MIT
authors:
  - name: fru.dev
goals:
  - Help students organize every area of their academic life so AI can actually work for them
  - Provide domain-specific AI agents with deep expertise and cross-domain coordination
  - Keep everything private, local, and vendor-neutral
---

# AI Ready U: Students

**10 AI agents. 9 student domains. 12 skills. 1 Chief of Staff. Private. On your machine.**

AI Ready U: Students is a company of AI agents that manage your entire student life. Each agent is a domain expert — academics, research, career development, finances, health, social life, skills, housing, and administration. The Chief of Staff orchestrates everything, produces weekly dashboards, and ensures nothing falls through the cracks.

## What's Free

- **10 agents** — Chief of Staff + 9 domain agents with budgets and capabilities
- **12 tool skills** — Gmail, Calendar, Drive, Storage, Port, Workflow, Contacts, Documents, Research, Writing, Booking, Analytics
- **Vault schema** — vault-structure.json showing the 9-domain architecture
- **Bootstrap tasks** — agents self-initialize on first run

## What's Paid ($49)

The agents need **instructions** and a **vault** (your documents) to do real work. Get both in the AI Ready U: Students pack:

**[Get AI Ready U: Students on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-students)**

The pack includes:
- Full agent instructions for all 10 agents (100+ lines each with domain expertise)
- 9-domain vault pre-filled with synthetic data
- 200+ ready-to-use prompts
- Context files for Claude, Gemini, and Cursor

After purchase, extract to `~/Documents/AIReadyU-Students/` and switch each agent from Managed to External in the Paperclip dashboard.

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-students --include company,agents,skills
```

## The 10 Agents

| Agent | Title | Budget |
|-------|-------|--------|
| Chief of Staff | Academic Director | $50/mo |
| Academics Agent | Academics Director | $20/mo |
| Research Agent | Research Director | $20/mo |
| Career Agent | Career Director | $20/mo |
| Finance Agent | Finance Director | $10/mo |
| Health Agent | Health Director | $10/mo |
| Social Agent | Social Director | $10/mo |
| Skills Agent | Skills Director | $10/mo |
| Housing Agent | Housing Director | $10/mo |
| Admin Agent | Admin Director | $10/mo |

## Part of AI Ready U

AI Ready U helps individuals and businesses organize their world so AI can actually work for them.

- Website: [aireadyu.dev](https://aireadyu.dev)
- YouTube: [youtube.com/@frudev](https://youtube.com/@frudev)
- Built by [fru.dev](https://fru.dev)
