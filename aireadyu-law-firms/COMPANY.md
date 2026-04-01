---
name: AI Ready U: Law Firms
description: >
  11 AI agents that manage your legal practice — cases, documents, research,
  intake, docket, billing, clients, compliance, business development, and admin.
  Orchestrated by a Managing Partner. Includes 12 tool skills.
  Agent instructions and vault available on Gumroad.
slug: aireadyu-law-firms
schema: agentcompanies/v1
version: 1.0.0
license: MIT
authors:
  - name: fru.dev
goals:
  - Help law firms eliminate the 240 hours per year lost to administrative work
  - Provide domain-specific AI agents with deep legal practice expertise
  - Keep everything private, local, and vendor-neutral
---

# AI Ready U: Law Firms

**11 AI agents. 10 legal domains. 12 skills. 1 Managing Partner. Private. On your machine.**

AI Ready U: Law Firms is a company of AI agents that manage your entire legal practice. Each agent is a domain expert — case management, document drafting, legal research, client intake, docket tracking, billing, compliance, and more. The Managing Partner orchestrates everything, produces weekly firm dashboards, and ensures no filing deadline slips.

## What's Free

- **11 agents** — Managing Partner (Ops) + 10 domain agents with budgets and capabilities
- **12 tool skills** — Gmail, Calendar, Drive, Storage, Port, Workflow, Contacts, Documents, Research, Writing, Booking, Analytics
- **Vault schema** — vault-structure.json showing the 10-domain architecture
- **Bootstrap tasks** — agents self-initialize on first run

## What's Paid ($99)

The agents need **instructions** and a **vault** (your documents) to do real work. Get both in the AI Ready U: Law Firms pack:

**[Get AI Ready U: Law Firms on Gumroad → $99](https://fruverse.gumroad.com/l/aireadyu-law-firms)**

The pack includes:
- Full agent instructions for all 11 agents (100+ lines each with domain expertise)
- 10-domain vault pre-filled with synthetic data
- 200+ ready-to-use prompts
- Context files for Claude, Gemini, and Cursor

After purchase, extract to `~/Documents/AIReadyU-Law-Firms/` and switch each agent from Managed to External in the Paperclip dashboard.

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-law-firms --include company,agents,skills
```

## The 11 Agents

| Agent | Title | Budget |
|-------|-------|--------|
| Chief of Staff | Managing Partner (Ops) | $50/mo |
| Cases Agent | Case Management Director | $20/mo |
| Documents Agent | Document & Contract Director | $20/mo |
| Research Agent | Legal Research Director | $20/mo |
| Intake Agent | Client Intake Director | $20/mo |
| Docket Agent | Docket & Deadlines Manager | $15/mo |
| Billing Agent | Legal Billing Director | $15/mo |
| Clients Agent | Client Relations Director | $10/mo |
| Compliance Agent | Ethics & Compliance Director | $10/mo |
| Bizdev Agent | Business Development Director | $10/mo |
| Admin Agent | Admin Director | $10/mo |

## Part of AI Ready U

AI Ready U helps individuals and businesses organize their world so AI can actually work for them.

- Website: [aireadyu.dev](https://aireadyu.dev)
- YouTube: [youtube.com/@frudev](https://youtube.com/@frudev)
- Built by [fru.dev](https://fru.dev)
