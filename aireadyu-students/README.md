
# AI Ready U: Students

**10 AI agents that manage your student life. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-students --include company,agents,projects,tasks
```

This creates 10 agents in Paperclip (9 domain + 1 Chief of Staff) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Students/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Students/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 9 student domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Academic Director | opus | $50/mo |
| Academics | Academics Director | sonnet | $20/mo |
| Research | Research Director | sonnet | $20/mo |
| Career | Career Director | sonnet | $20/mo |
| Finance | Finance Director | haiku | $10/mo |
| Health | Health Director | haiku | $10/mo |
| Social | Social Director | haiku | $10/mo |
| Skills | Skills Director | haiku | $10/mo |
| Housing | Housing Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Students on Gumroad → $29](https://fruverse.gumroad.com/l/aireadyu-students)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-students --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Students on Gumroad → $29](https://fruverse.gumroad.com/l/aireadyu-students)**

### Step 3: Extract to `~/Documents/AIReadyU-Students/`

```
~/Documents/AIReadyU-Students/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 9 student domains with synthetic data
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
| Chief of Staff | `~/Documents/AIReadyU-Students/agents/chief-of-staff` |
| Academics | `~/Documents/AIReadyU-Students/agents/academics-agent` |
| Research | `~/Documents/AIReadyU-Students/agents/research-agent` |
| Career | `~/Documents/AIReadyU-Students/agents/career-agent` |
| Finance | `~/Documents/AIReadyU-Students/agents/finance-agent` |
| Health | `~/Documents/AIReadyU-Students/agents/health-agent` |
| Social | `~/Documents/AIReadyU-Students/agents/social-agent` |
| Skills | `~/Documents/AIReadyU-Students/agents/skills-agent` |
| Housing | `~/Documents/AIReadyU-Students/agents/housing-agent` |
| Admin | `~/Documents/AIReadyU-Students/agents/admin-agent` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Students/vault/` with your real files.

### Step 6: Enable Chief of Staff

It reads your goals, creates issues for all agents, and produces the first student dashboard.

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
