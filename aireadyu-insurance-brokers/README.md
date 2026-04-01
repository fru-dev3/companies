
# AI Ready U: Insurance Brokers

**10 AI agents that manage your insurance brokerage. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-insurance-brokers --include company,agents,projects,tasks
```

This creates 10 agents in Paperclip (9 domain + 1 Brokerage Operations Director) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Insurance-Brokers/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Insurance-Brokers/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 9 brokerage domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Brokerage Operations Director | opus | $50/mo |
| Clients | Client Relations Director | sonnet | $20/mo |
| Renewals | Renewals & Retention Director | sonnet | $20/mo |
| Intake | New Client Intake Director | sonnet | $20/mo |
| Quotes | Quoting & Proposal Director | sonnet | $15/mo |
| Claims | Claims Support Director | sonnet | $15/mo |
| Compliance | Compliance & Licensing Director | haiku | $10/mo |
| Carrier | Carrier Relations Director | haiku | $10/mo |
| Marketing | Growth & Marketing Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Insurance Brokers on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-insurance-brokers)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-insurance-brokers --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Insurance Brokers on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-insurance-brokers)**

### Step 3: Extract to `~/Documents/AIReadyU-Insurance-Brokers/`

```
~/Documents/AIReadyU-Insurance-Brokers/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 9 brokerage domains with synthetic data
├── PROMPTS.md
├── CLAUDE.md
├── GEMINI.md
└── .cursorrules
```

### Step 4: Connect each agent to external instructions

For each of the 10 agents in the Paperclip dashboard:

1. Click on the agent
2. Click **Advanced**
3. Switch from **Managed** to **External**
4. Paste the root folder path (shown in each agent's description)
5. Hit **Save**

| Agent | Root Folder Path |
|-------|-----------------|
| Chief of Staff | `~/Documents/AIReadyU-Insurance-Brokers/agents/chief-of-staff` |
| Clients | `~/Documents/AIReadyU-Insurance-Brokers/agents/clients` |
| Renewals | `~/Documents/AIReadyU-Insurance-Brokers/agents/renewals` |
| Intake | `~/Documents/AIReadyU-Insurance-Brokers/agents/intake` |
| Quotes | `~/Documents/AIReadyU-Insurance-Brokers/agents/quotes` |
| Claims | `~/Documents/AIReadyU-Insurance-Brokers/agents/claims` |
| Compliance | `~/Documents/AIReadyU-Insurance-Brokers/agents/compliance` |
| Carrier | `~/Documents/AIReadyU-Insurance-Brokers/agents/carrier` |
| Marketing | `~/Documents/AIReadyU-Insurance-Brokers/agents/marketing` |
| Admin | `~/Documents/AIReadyU-Insurance-Brokers/agents/admin` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Insurance-Brokers/vault/` with your real files.

### Step 6: Enable Brokerage Operations Director

It reads your goals, creates issues for all agents, and produces the first brokerage dashboard.

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
