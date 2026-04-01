
# AI Ready U: Recruiters

**11 AI agents that power your full recruitment cycle. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-recruiters --include company,agents,projects,tasks
```

This creates 11 agents in Paperclip (10 domain + 1 Recruiting Operations Director) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Recruiters/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Recruiters/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 10 recruiting domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Recruiting Operations Director | opus | $50/mo |
| Sourcing | Talent Sourcing Director | sonnet | $20/mo |
| Outreach | Candidate Outreach Director | sonnet | $20/mo |
| Screening | Candidate Screening Director | sonnet | $20/mo |
| Pipeline | Pipeline & Tracking Director | sonnet | $20/mo |
| Clients | Client Relations Director | sonnet | $15/mo |
| JD | Job Description Director | haiku | $10/mo |
| Offers | Offer Management Director | haiku | $10/mo |
| Onboarding | Candidate Onboarding Director | haiku | $10/mo |
| Bizdev | Business Development Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Recruiters on Gumroad → $59](https://fruverse.gumroad.com/l/aireadyu-recruiters)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-recruiters --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Recruiters on Gumroad → $59](https://fruverse.gumroad.com/l/aireadyu-recruiters)**

### Step 3: Extract to `~/Documents/AIReadyU-Recruiters/`

```
~/Documents/AIReadyU-Recruiters/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 10 recruiting domains with synthetic data
├── PROMPTS.md
├── CLAUDE.md
├── GEMINI.md
└── .cursorrules
```

### Step 4: Connect each agent to external instructions

For each of the 11 agents in the Paperclip dashboard:

1. Click on the agent
2. Click **Advanced**
3. Switch from **Managed** to **External**
4. Paste the root folder path (shown in each agent's description)
5. Hit **Save**

| Agent | Root Folder Path |
|-------|-----------------|
| Chief of Staff | `~/Documents/AIReadyU-Recruiters/agents/chief-of-staff` |
| Sourcing | `~/Documents/AIReadyU-Recruiters/agents/sourcing` |
| Outreach | `~/Documents/AIReadyU-Recruiters/agents/outreach` |
| Screening | `~/Documents/AIReadyU-Recruiters/agents/screening` |
| Pipeline | `~/Documents/AIReadyU-Recruiters/agents/pipeline` |
| Clients | `~/Documents/AIReadyU-Recruiters/agents/clients` |
| JD | `~/Documents/AIReadyU-Recruiters/agents/jd` |
| Offers | `~/Documents/AIReadyU-Recruiters/agents/offers` |
| Onboarding | `~/Documents/AIReadyU-Recruiters/agents/onboarding` |
| Bizdev | `~/Documents/AIReadyU-Recruiters/agents/bizdev` |
| Admin | `~/Documents/AIReadyU-Recruiters/agents/admin` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Recruiters/vault/` with your real files.

### Step 6: Enable Recruiting Operations Director

It reads your goals, creates issues for all agents, and produces the first recruiting dashboard.

## Privacy

Everything runs locally. No cloud. No accounts. No telemetry. Your documents never leave your machine.

## Part of AI Ready U

| Resource | Link |
|----------|------|
| Website | [aireadyu.dev](https://aireadyu.dev) |
| YouTube | [youtube.com/@frudev](https://youtube.com/@frudev) |
| Strategy Call | [Book a call](https://cal.com/fru-dev3/vault-strategy) |
| Built by | [fru.dev](https://fru.dev) |

## License

MIT
