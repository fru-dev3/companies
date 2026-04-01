
# AI Ready U: Creators

**12 AI agents that manage your creator business. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-creators --include company,agents,projects,tasks
```

This creates 12 agents in Paperclip (11 domain + 1 Creator Director) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Creators/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Creators/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 11 creator domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Creator Director | Creator Director | opus | $50/mo |
| Content | Content Director | sonnet | $20/mo |
| Brand | Brand Director | sonnet | $20/mo |
| Monetization | Monetization Director | sonnet | $20/mo |
| Analytics | Analytics Director | haiku | $10/mo |
| Audience | Audience Director | sonnet | $20/mo |
| Production | Production Director | haiku | $10/mo |
| Legal | Legal Director | sonnet | $10/mo |
| Finance | Finance Director | haiku | $10/mo |
| Partnerships | Partnerships Director | sonnet | $20/mo |
| Tools | Tools Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Creators on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-creators)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-creators --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Creators on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-creators)**

### Step 3: Extract to `~/Documents/AIReadyU-Creators/`

```
~/Documents/AIReadyU-Creators/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 11 creator domains with synthetic data
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
| Creator Director | `~/Documents/AIReadyU-Creators/agents/chief-of-staff` |
| Content | `~/Documents/AIReadyU-Creators/agents/content-agent` |
| Brand | `~/Documents/AIReadyU-Creators/agents/brand-agent` |
| Monetization | `~/Documents/AIReadyU-Creators/agents/monetization-agent` |
| Analytics | `~/Documents/AIReadyU-Creators/agents/analytics-agent` |
| Audience | `~/Documents/AIReadyU-Creators/agents/audience-agent` |
| Production | `~/Documents/AIReadyU-Creators/agents/production-agent` |
| Legal | `~/Documents/AIReadyU-Creators/agents/legal-agent` |
| Finance | `~/Documents/AIReadyU-Creators/agents/finance-agent` |
| Partnerships | `~/Documents/AIReadyU-Creators/agents/partnerships-agent` |
| Tools | `~/Documents/AIReadyU-Creators/agents/tools-agent` |
| Admin | `~/Documents/AIReadyU-Creators/agents/admin-agent` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Creators/vault/` with your real files.

### Step 6: Enable Creator Director

It reads your goals, creates issues for all agents, and produces the first creator dashboard.

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
