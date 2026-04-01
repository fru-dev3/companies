
# AI Ready U: Freelancers

**10 AI agents that manage your freelance business. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-freelancers --include company,agents,projects,tasks
```

This creates 10 agents in Paperclip (9 domain + 1 Chief of Staff) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Freelancers/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Freelancers/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 9 business domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Chief of Staff | opus | $50/mo |
| Clients | Client Director | sonnet | $20/mo |
| Projects | Project Director | sonnet | $20/mo |
| Finance | Finance Director | sonnet | $20/mo |
| Marketing | Marketing Director | haiku | $10/mo |
| Skills | Skills Director | haiku | $10/mo |
| Legal | Legal Director | sonnet | $10/mo |
| Wellbeing | Wellbeing Director | haiku | $10/mo |
| Pipeline | Business Development Director | sonnet | $20/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Freelancers on Gumroad → $39](https://fruverse.gumroad.com/l/aireadyu-freelancers)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-freelancers --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Freelancers on Gumroad → $39](https://fruverse.gumroad.com/l/aireadyu-freelancers)**

### Step 3: Extract to `~/Documents/AIReadyU-Freelancers/`

```
~/Documents/AIReadyU-Freelancers/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 9 business domains with synthetic data
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
| Chief of Staff | `~/Documents/AIReadyU-Freelancers/agents/chief-of-staff` |
| Clients | `~/Documents/AIReadyU-Freelancers/agents/clients-agent` |
| Projects | `~/Documents/AIReadyU-Freelancers/agents/projects-agent` |
| Finance | `~/Documents/AIReadyU-Freelancers/agents/finance-agent` |
| Marketing | `~/Documents/AIReadyU-Freelancers/agents/marketing-agent` |
| Skills | `~/Documents/AIReadyU-Freelancers/agents/skills-agent` |
| Legal | `~/Documents/AIReadyU-Freelancers/agents/legal-agent` |
| Wellbeing | `~/Documents/AIReadyU-Freelancers/agents/wellbeing-agent` |
| Pipeline | `~/Documents/AIReadyU-Freelancers/agents/pipeline-agent` |
| Admin | `~/Documents/AIReadyU-Freelancers/agents/admin-agent` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Freelancers/vault/` with your real files.

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
