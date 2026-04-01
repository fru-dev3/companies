
# AI Ready U: Real Estate

**11 AI agents that manage your real estate investment portfolio. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-real-estate --include company,agents,projects,tasks
```

This creates 11 agents in Paperclip (10 domain + 1 Portfolio Director) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Real-Estate/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Real-Estate/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 10 REI domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Portfolio Director | opus | $50/mo |
| Properties | Property Manager | sonnet | $20/mo |
| Acquisitions | Acquisitions Director | sonnet | $20/mo |
| Tenants | Tenant Relations Director | haiku | $10/mo |
| Maintenance | Maintenance Director | haiku | $10/mo |
| Financing | Financing Director | sonnet | $20/mo |
| Taxes | Tax Director | haiku | $10/mo |
| Insurance | Insurance Director | haiku | $10/mo |
| Legal | Legal Director | haiku | $10/mo |
| Accounting | Accounting Director | sonnet | $20/mo |
| Market | Market Research Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Real Estate on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-real-estate)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-real-estate --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Real Estate on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-real-estate)**

### Step 3: Extract to `~/Documents/AIReadyU-Real-Estate/`

```
~/Documents/AIReadyU-Real-Estate/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 10 REI domains with synthetic data
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
| Chief of Staff | `~/Documents/AIReadyU-Real-Estate/agents/chief-of-staff` |
| Properties | `~/Documents/AIReadyU-Real-Estate/agents/properties-agent` |
| Acquisitions | `~/Documents/AIReadyU-Real-Estate/agents/acquisitions-agent` |
| Tenants | `~/Documents/AIReadyU-Real-Estate/agents/tenants-agent` |
| Maintenance | `~/Documents/AIReadyU-Real-Estate/agents/maintenance-agent` |
| Financing | `~/Documents/AIReadyU-Real-Estate/agents/financing-agent` |
| Taxes | `~/Documents/AIReadyU-Real-Estate/agents/taxes-agent` |
| Insurance | `~/Documents/AIReadyU-Real-Estate/agents/insurance-agent` |
| Legal | `~/Documents/AIReadyU-Real-Estate/agents/legal-agent` |
| Accounting | `~/Documents/AIReadyU-Real-Estate/agents/accounting-agent` |
| Market | `~/Documents/AIReadyU-Real-Estate/agents/market-agent` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Real-Estate/vault/` with your real files.

### Step 6: Enable Portfolio Director

It reads your goals, creates issues for all agents, and produces the first portfolio dashboard.

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
