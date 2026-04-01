
# AI Ready U: Educators

**11 AI agents that manage your teaching practice. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-educators --include company,agents,projects,tasks
```

This creates 11 agents in Paperclip (10 domain + 1 Chief of Staff) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Educators/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Educators/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 10 educator domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Chief of Staff | opus | $50/mo |
| Curriculum | Curriculum Director | sonnet | $20/mo |
| Students | Student Success Director | sonnet | $20/mo |
| Assessment | Assessment Director | haiku | $10/mo |
| Professional Dev | Professional Development Director | haiku | $10/mo |
| Research | Research Director | haiku | $10/mo |
| Finance | Finance Director | haiku | $10/mo |
| Tech | Tech Director | haiku | $10/mo |
| Wellbeing | Wellbeing Director | haiku | $10/mo |
| Community | Community Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Educators on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-educators)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-educators --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Educators on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-educators)**

### Step 3: Extract to `~/Documents/AIReadyU-Educators/`

```
~/Documents/AIReadyU-Educators/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 10 educator domains with synthetic data
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
| Chief of Staff | `~/Documents/AIReadyU-Educators/agents/chief-of-staff` |
| Curriculum | `~/Documents/AIReadyU-Educators/agents/curriculum-agent` |
| Students | `~/Documents/AIReadyU-Educators/agents/students-agent` |
| Assessment | `~/Documents/AIReadyU-Educators/agents/assessment-agent` |
| Professional Dev | `~/Documents/AIReadyU-Educators/agents/professional-dev-agent` |
| Research | `~/Documents/AIReadyU-Educators/agents/research-agent` |
| Finance | `~/Documents/AIReadyU-Educators/agents/finance-agent` |
| Tech | `~/Documents/AIReadyU-Educators/agents/tech-agent` |
| Wellbeing | `~/Documents/AIReadyU-Educators/agents/wellbeing-agent` |
| Community | `~/Documents/AIReadyU-Educators/agents/community-agent` |
| Admin | `~/Documents/AIReadyU-Educators/agents/admin-agent` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Educators/vault/` with your real files.

### Step 6: Enable Chief of Staff

It reads your goals, creates issues for all agents, and produces the first educator dashboard.

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
