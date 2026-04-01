
# AI Ready U: Small Business

**13 AI agents that manage your small business. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-small-business --include company,agents,projects,tasks
```

This creates 13 agents in Paperclip (12 domain + 1 Chief of Staff) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Small-Business/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Small-Business/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 12 business domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Chief Operating Officer | opus | $50/mo |
| Operations | Operations Director | haiku | $10/mo |
| Customers | Customer Success Director | sonnet | $20/mo |
| Sales | Sales Director | sonnet | $20/mo |
| Marketing | Marketing Director | sonnet | $20/mo |
| Finance | Finance Director | sonnet | $20/mo |
| HR | HR Director | haiku | $10/mo |
| Legal | Legal Director | sonnet | $10/mo |
| Vendors | Procurement Director | haiku | $10/mo |
| Products | Product Director | haiku | $10/mo |
| Knowledge | Knowledge Director | haiku | $10/mo |
| Tech | Technology Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Small Business on Gumroad → $29](https://fruverse.gumroad.com/l/aireadyu-small-business)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-small-business --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Small Business on Gumroad → $29](https://fruverse.gumroad.com/l/aireadyu-small-business)**

### Step 3: Extract to `~/Documents/AIReadyU-Small-Business/`

```
~/Documents/AIReadyU-Small-Business/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 12 business domains with synthetic data
├── PROMPTS.md
├── CLAUDE.md
├── GEMINI.md
└── .cursorrules
```

### Step 4: Connect each agent to external instructions

For each of the 13 agents in the Paperclip dashboard:

1. Click on the agent
2. Click **Advanced**
3. Switch from **Managed** to **External**
4. Paste the root folder path (shown in each agent's description)
5. Hit **Save**

| Agent | Root Folder Path |
|-------|-----------------|
| Chief of Staff | `~/Documents/AIReadyU-Small-Business/agents/chief-of-staff` |
| Operations | `~/Documents/AIReadyU-Small-Business/agents/operations-agent` |
| Customers | `~/Documents/AIReadyU-Small-Business/agents/customers-agent` |
| Sales | `~/Documents/AIReadyU-Small-Business/agents/sales-agent` |
| Marketing | `~/Documents/AIReadyU-Small-Business/agents/marketing-agent` |
| Finance | `~/Documents/AIReadyU-Small-Business/agents/finance-agent` |
| HR | `~/Documents/AIReadyU-Small-Business/agents/hr-agent` |
| Legal | `~/Documents/AIReadyU-Small-Business/agents/legal-agent` |
| Vendors | `~/Documents/AIReadyU-Small-Business/agents/vendors-agent` |
| Products | `~/Documents/AIReadyU-Small-Business/agents/products-agent` |
| Knowledge | `~/Documents/AIReadyU-Small-Business/agents/knowledge-agent` |
| Tech | `~/Documents/AIReadyU-Small-Business/agents/tech-agent` |
| Admin | `~/Documents/AIReadyU-Small-Business/agents/admin-agent` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Small-Business/vault/` with your real files.

### Step 6: Enable Chief of Staff

It reads your goals, creates issues for all agents, and produces the first business dashboard.

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
