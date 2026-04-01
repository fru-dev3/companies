
# AI Ready U: E-Commerce

**12 AI agents that manage your e-commerce store. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-ecommerce --include company,agents,projects,tasks
```

This creates 12 agents in Paperclip (11 domain + 1 Chief of Staff) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Ecommerce/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Ecommerce/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 11 store domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Chief Operating Officer | opus | $50/mo |
| Inventory | Inventory Director | haiku | $10/mo |
| Listings | Listings Director | sonnet | $20/mo |
| Customers | Customer Success Director | sonnet | $20/mo |
| Orders | Operations Director | haiku | $10/mo |
| Marketing | Marketing Director | sonnet | $20/mo |
| Finance | Finance Director | sonnet | $20/mo |
| Vendors | Procurement Director | haiku | $10/mo |
| Shipping | Logistics Director | haiku | $10/mo |
| Analytics | Analytics Director | haiku | $10/mo |
| Tech | Tech Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: E-Commerce on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-ecommerce)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-ecommerce --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: E-Commerce on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-ecommerce)**

### Step 3: Extract to `~/Documents/AIReadyU-Ecommerce/`

```
~/Documents/AIReadyU-Ecommerce/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 11 store domains with synthetic data
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
| Chief of Staff | `~/Documents/AIReadyU-Ecommerce/agents/chief-of-staff` |
| Inventory | `~/Documents/AIReadyU-Ecommerce/agents/inventory-agent` |
| Listings | `~/Documents/AIReadyU-Ecommerce/agents/listings-agent` |
| Customers | `~/Documents/AIReadyU-Ecommerce/agents/customers-agent` |
| Orders | `~/Documents/AIReadyU-Ecommerce/agents/orders-agent` |
| Marketing | `~/Documents/AIReadyU-Ecommerce/agents/marketing-agent` |
| Finance | `~/Documents/AIReadyU-Ecommerce/agents/finance-agent` |
| Vendors | `~/Documents/AIReadyU-Ecommerce/agents/vendors-agent` |
| Shipping | `~/Documents/AIReadyU-Ecommerce/agents/shipping-agent` |
| Analytics | `~/Documents/AIReadyU-Ecommerce/agents/analytics-agent` |
| Tech | `~/Documents/AIReadyU-Ecommerce/agents/tech-agent` |
| Admin | `~/Documents/AIReadyU-Ecommerce/agents/admin-agent` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Ecommerce/vault/` with your real files.

### Step 6: Enable Chief of Staff

It reads your goals, creates issues for all agents, and produces the first store dashboard.

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
