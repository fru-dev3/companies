
# AI Ready U: Consultants

**11 AI agents that manage your consulting business. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-consultants --include company,agents,projects,tasks
```

This creates 11 agents in Paperclip (10 domain + 1 Managing Director) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Consultants/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Consultants/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 10 consulting domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Managing Director | opus | $50/mo |
| Clients | Client Relations Director | sonnet | $20/mo |
| Proposals | Proposals Director | sonnet | $20/mo |
| Deliverables | Delivery Director | sonnet | $20/mo |
| Pipeline | Revenue Director | sonnet | $20/mo |
| SOPs | Operations Director | haiku | $10/mo |
| Knowledge | Knowledge Director | haiku | $10/mo |
| Content | Content Director | haiku | $10/mo |
| Finance | Finance Director | sonnet | $20/mo |
| Legal | Legal Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Consultants on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-consultants)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-consultants --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Consultants on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-consultants)**

### Step 3: Extract to `~/Documents/AIReadyU-Consultants/`

```
~/Documents/AIReadyU-Consultants/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 10 consulting domains with synthetic data
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
| Chief of Staff | `~/Documents/AIReadyU-Consultants/agents/chief-of-staff` |
| Clients | `~/Documents/AIReadyU-Consultants/agents/clients` |
| Proposals | `~/Documents/AIReadyU-Consultants/agents/proposals` |
| Deliverables | `~/Documents/AIReadyU-Consultants/agents/deliverables` |
| Pipeline | `~/Documents/AIReadyU-Consultants/agents/pipeline` |
| SOPs | `~/Documents/AIReadyU-Consultants/agents/sops` |
| Knowledge | `~/Documents/AIReadyU-Consultants/agents/knowledge` |
| Content | `~/Documents/AIReadyU-Consultants/agents/content` |
| Finance | `~/Documents/AIReadyU-Consultants/agents/finance` |
| Legal | `~/Documents/AIReadyU-Consultants/agents/legal` |
| Admin | `~/Documents/AIReadyU-Consultants/agents/admin` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Consultants/vault/` with your real files.

### Step 6: Enable Managing Director

It reads your goals, creates issues for all agents, and produces the first consulting dashboard.

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
