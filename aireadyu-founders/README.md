
# AI Ready U: Founders

**11 AI agents that manage your startup. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-founders --include company,agents,projects,tasks
```

This creates 11 agents in Paperclip (10 domain + 1 Chief of Staff) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Founders/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Founders/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 10 startup domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Chief of Staff | opus | $50/mo |
| Product | Product Director | sonnet | $20/mo |
| Fundraising | Fundraising Director | sonnet | $20/mo |
| Hiring | Hiring Director | sonnet | $20/mo |
| Legal | Legal Director | sonnet | $10/mo |
| Finance | Finance Director | sonnet | $20/mo |
| Marketing | Marketing Director | sonnet | $20/mo |
| Customers | Customer Director | sonnet | $20/mo |
| Operations | Operations Director | haiku | $10/mo |
| Tech | Tech Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Founders on Gumroad → $79](https://fruverse.gumroad.com/l/aireadyu-founders)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-founders --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Founders on Gumroad → $79](https://fruverse.gumroad.com/l/aireadyu-founders)**

### Step 3: Extract to `~/Documents/AIReadyU-Founders/`

```
~/Documents/AIReadyU-Founders/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 10 startup domains with synthetic data
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
| Chief of Staff | `~/Documents/AIReadyU-Founders/agents/chief-of-staff` |
| Product | `~/Documents/AIReadyU-Founders/agents/product-agent` |
| Fundraising | `~/Documents/AIReadyU-Founders/agents/fundraising-agent` |
| Hiring | `~/Documents/AIReadyU-Founders/agents/hiring-agent` |
| Legal | `~/Documents/AIReadyU-Founders/agents/legal-agent` |
| Finance | `~/Documents/AIReadyU-Founders/agents/finance-agent` |
| Marketing | `~/Documents/AIReadyU-Founders/agents/marketing-agent` |
| Customers | `~/Documents/AIReadyU-Founders/agents/customers-agent` |
| Operations | `~/Documents/AIReadyU-Founders/agents/operations-agent` |
| Tech | `~/Documents/AIReadyU-Founders/agents/tech-agent` |
| Admin | `~/Documents/AIReadyU-Founders/agents/admin-agent` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Founders/vault/` with your real files.

### Step 6: Enable Chief of Staff

It reads your goals, creates issues for all agents, and produces the first founder dashboard.

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
