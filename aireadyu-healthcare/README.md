
# AI Ready U: Healthcare

**11 AI agents that manage your healthcare practice. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-healthcare --include company,agents,projects,tasks
```

This creates 11 agents in Paperclip (10 domain + 1 Practice Administrator) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Healthcare/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Healthcare/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 10 healthcare domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Practice Administrator | opus | $50/mo |
| Patients | Patient Relations Director | sonnet | $20/mo |
| Scheduling | Scheduling & Access Director | sonnet | $20/mo |
| Billing | Medical Billing Director | sonnet | $20/mo |
| Clinical Docs | Clinical Documentation Director | sonnet | $20/mo |
| Insurance | Insurance & Prior Auth Director | sonnet | $15/mo |
| Referrals | Referrals & Care Coordination Director | sonnet | $15/mo |
| Compliance | HIPAA & Compliance Director | haiku | $10/mo |
| HR | Staff & HR Director | haiku | $10/mo |
| Marketing | Patient Acquisition Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Healthcare on Gumroad → $79](https://fruverse.gumroad.com/l/aireadyu-healthcare)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-healthcare --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Healthcare on Gumroad → $79](https://fruverse.gumroad.com/l/aireadyu-healthcare)**

### Step 3: Extract to `~/Documents/AIReadyU-Healthcare/`

```
~/Documents/AIReadyU-Healthcare/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 10 healthcare domains with synthetic data
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
| Chief of Staff | `~/Documents/AIReadyU-Healthcare/agents/chief-of-staff` |
| Patients | `~/Documents/AIReadyU-Healthcare/agents/patients` |
| Scheduling | `~/Documents/AIReadyU-Healthcare/agents/scheduling` |
| Billing | `~/Documents/AIReadyU-Healthcare/agents/billing` |
| Clinical Docs | `~/Documents/AIReadyU-Healthcare/agents/clinical-docs` |
| Insurance | `~/Documents/AIReadyU-Healthcare/agents/insurance` |
| Referrals | `~/Documents/AIReadyU-Healthcare/agents/referrals` |
| Compliance | `~/Documents/AIReadyU-Healthcare/agents/compliance` |
| HR | `~/Documents/AIReadyU-Healthcare/agents/hr` |
| Marketing | `~/Documents/AIReadyU-Healthcare/agents/marketing` |
| Admin | `~/Documents/AIReadyU-Healthcare/agents/admin` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Healthcare/vault/` with your real files.

### Step 6: Enable Practice Administrator

It reads your goals, creates issues for all agents, and produces the first practice dashboard.

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
