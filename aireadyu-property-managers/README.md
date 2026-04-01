
# AI Ready U: Property Managers

**11 AI agents that manage your property portfolio. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-property-managers --include company,agents,projects,tasks
```

This creates 11 agents in Paperclip (10 domain + 1 Chief of Staff) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Property-Managers/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Property-Managers/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 10 property domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Chief Operating Officer | opus | $50/mo |
| Properties | Property Director | sonnet | $20/mo |
| Tenants | Tenant Director | sonnet | $20/mo |
| Maintenance | Maintenance Director | haiku | $10/mo |
| Leasing | Leasing Director | sonnet | $20/mo |
| Finance | Finance Director | sonnet | $20/mo |
| Legal | Legal Director | sonnet | $10/mo |
| Vendors | Vendor Director | haiku | $10/mo |
| Insurance | Insurance Director | haiku | $10/mo |
| Compliance | Compliance Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Property Managers on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-property-managers)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-property-managers --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Property Managers on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-property-managers)**

### Step 3: Extract to `~/Documents/AIReadyU-Property-Managers/`

```
~/Documents/AIReadyU-Property-Managers/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 10 property domains with synthetic data
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
| Chief of Staff | `~/Documents/AIReadyU-Property-Managers/agents/chief-of-staff` |
| Properties | `~/Documents/AIReadyU-Property-Managers/agents/properties-agent` |
| Tenants | `~/Documents/AIReadyU-Property-Managers/agents/tenants-agent` |
| Maintenance | `~/Documents/AIReadyU-Property-Managers/agents/maintenance-agent` |
| Leasing | `~/Documents/AIReadyU-Property-Managers/agents/leasing-agent` |
| Finance | `~/Documents/AIReadyU-Property-Managers/agents/finance-agent` |
| Legal | `~/Documents/AIReadyU-Property-Managers/agents/legal-agent` |
| Vendors | `~/Documents/AIReadyU-Property-Managers/agents/vendors-agent` |
| Insurance | `~/Documents/AIReadyU-Property-Managers/agents/insurance-agent` |
| Compliance | `~/Documents/AIReadyU-Property-Managers/agents/compliance-agent` |
| Admin | `~/Documents/AIReadyU-Property-Managers/agents/admin-agent` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Property-Managers/vault/` with your real files.

### Step 6: Enable Chief of Staff

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
