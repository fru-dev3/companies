---
name: AI Ready U: Healthcare
description: >
  11 AI agents that manage your healthcare practice — patients, scheduling,
  billing, clinical documentation, insurance, referrals, compliance, HR,
  marketing, and admin. Orchestrated by a Practice Administrator.
  Includes 12 tool skills. Agent instructions and vault available on Gumroad.
slug: aireadyu-healthcare
schema: agentcompanies/v1
version: 1.0.0
license: MIT
authors:
  - name: fru.dev
goals:
  - Eliminate administrative burden from healthcare practices so clinicians can focus on patient care
  - Provide domain-specific AI agents with deep healthcare workflow expertise
  - Keep everything private, local, and vendor-neutral
---

# AI Ready U: Healthcare

**11 AI agents. 10 healthcare domains. 12 skills. 1 Practice Administrator. Private. On your machine.**

AI Ready U: Healthcare is a company of AI agents that manage your entire healthcare practice. Each agent is a domain expert — patient relations, scheduling, medical billing, clinical documentation, insurance & prior auth, referrals, HIPAA compliance, HR, and more. The Practice Administrator orchestrates everything, produces daily practice briefings, and ensures nothing falls through the cracks.

## What's Free

- **11 agents** — Practice Administrator + 10 domain agents with budgets and capabilities
- **12 tool skills** — Gmail, Calendar, Drive, Storage, Port, Workflow, Contacts, Documents, Research, Writing, Booking, Analytics
- **Vault schema** — vault-structure.json showing the 10-domain architecture
- **Bootstrap tasks** — agents self-initialize on first run

## What's Paid ($79)

The agents need **instructions** and a **vault** (your documents) to do real work. Get both in the AI Ready U: Healthcare pack:

**[Get AI Ready U: Healthcare on Gumroad → $79](https://fruverse.gumroad.com/l/aireadyu-healthcare)**

The pack includes:
- Full agent instructions for all 11 agents (100+ lines each with domain expertise)
- 10-domain vault pre-filled with synthetic data
- 200+ ready-to-use prompts
- Context files for Claude, Gemini, and Cursor

After purchase, extract to `~/Documents/AIReadyU-Healthcare/` and switch each agent from Managed to External in the Paperclip dashboard.

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-healthcare --include company,agents,skills
```

## The 11 Agents

| Agent | Title | Budget |
|-------|-------|--------|
| Chief of Staff | Practice Administrator | $50/mo |
| Patients Agent | Patient Relations Director | $20/mo |
| Scheduling Agent | Scheduling & Access Director | $20/mo |
| Billing Agent | Medical Billing Director | $20/mo |
| Clinical Docs Agent | Clinical Documentation Director | $20/mo |
| Insurance Agent | Insurance & Prior Auth Director | $15/mo |
| Referrals Agent | Referrals & Care Coordination Director | $15/mo |
| Compliance Agent | HIPAA & Compliance Director | $10/mo |
| HR Agent | Staff & HR Director | $10/mo |
| Marketing Agent | Patient Acquisition Director | $10/mo |
| Admin Agent | Admin Director | $10/mo |

## Part of AI Ready U

AI Ready U helps individuals and businesses organize their world so AI can actually work for them.

- Website: [aireadyu.dev](https://aireadyu.dev)
- YouTube: [youtube.com/@frudev](https://youtube.com/@frudev)
- Built by [fru.dev](https://fru.dev)
