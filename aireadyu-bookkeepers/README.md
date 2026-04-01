
# AI Ready U: Bookkeepers

**12 AI agents that manage your bookkeeping practice. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-bookkeepers --include company,agents,projects,tasks
```

This creates 12 agents in Paperclip (11 domain + 1 Practice Operations Director) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Bookkeepers/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Bookkeepers/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 11 bookkeeping domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Practice Operations Director | opus | $50/mo |
| Clients | Client Accounts Manager | sonnet | $20/mo |
| Bookkeeping | Senior Bookkeeper | sonnet | $20/mo |
| Reconciliation | Reconciliation Specialist | sonnet | $20/mo |
| Reporting | Financial Reporting Director | sonnet | $20/mo |
| Payroll | Payroll Manager | sonnet | $15/mo |
| Tax Prep | Tax Prep Coordinator | sonnet | $15/mo |
| Billing | Practice Billing Manager | sonnet | $15/mo |
| Compliance | Compliance & Audit Director | haiku | $10/mo |
| Software | Software & Integration Director | haiku | $10/mo |
| Marketing | Practice Growth Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Bookkeepers on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-bookkeepers)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-bookkeepers --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Bookkeepers on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-bookkeepers)**

### Step 3: Extract to `~/Documents/AIReadyU-Bookkeepers/`

```
~/Documents/AIReadyU-Bookkeepers/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 11 bookkeeping domains with synthetic data
├── PROMPTS.md
├── CLAUDE.md
├── GEMINI.md
└── .cursorrules
```

### Step 4: Connect each agent to external instructions

For each of the 12 agents in the Paperclip dashboard:

1. Click on the agent
2. Click **Advanced**
3. Switch from **Managed** to **External**
4. Paste the root folder path (shown in each agent's description)
5. Hit **Save**

| Agent | Root Folder Path |
|-------|-----------------|
| Chief of Staff | `~/Documents/AIReadyU-Bookkeepers/agents/chief-of-staff` |
| Clients | `~/Documents/AIReadyU-Bookkeepers/agents/clients` |
| Bookkeeping | `~/Documents/AIReadyU-Bookkeepers/agents/bookkeeping` |
| Reconciliation | `~/Documents/AIReadyU-Bookkeepers/agents/reconciliation` |
| Reporting | `~/Documents/AIReadyU-Bookkeepers/agents/reporting` |
| Payroll | `~/Documents/AIReadyU-Bookkeepers/agents/payroll` |
| Tax Prep | `~/Documents/AIReadyU-Bookkeepers/agents/tax-prep` |
| Billing | `~/Documents/AIReadyU-Bookkeepers/agents/billing` |
| Compliance | `~/Documents/AIReadyU-Bookkeepers/agents/compliance` |
| Software | `~/Documents/AIReadyU-Bookkeepers/agents/software` |
| Marketing | `~/Documents/AIReadyU-Bookkeepers/agents/marketing` |
| Admin | `~/Documents/AIReadyU-Bookkeepers/agents/admin` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Bookkeepers/vault/` with your real files.

### Step 6: Enable Practice Operations Director

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
