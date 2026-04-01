
# AI Ready U: Law Firms

**11 AI agents that manage your legal practice. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-law-firms --include company,agents,projects,tasks
```

This creates 11 agents in Paperclip (10 domain + 1 Managing Partner) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Law-Firms/`.

## Architecture

```
GitHub (free):
  agents/          <- agent shells (name, title, budget, capabilities)
  .paperclip.yaml  <- adapter config, models, heartbeats
  tasks/           <- bootstrap issues
  vault/           <- vault schema (vault-structure.json)

~/Documents/AIReadyU-Law-Firms/ (paid pack):
  agents/          <- full agent instructions (AGENTS.md)
  skills/          <- 12 tool skills (gmail, calendar, drive, etc.)
  vault/           <- 10 legal domains with synthetic data
  PROMPTS.md       <- 200+ ready-to-use prompts
  CLAUDE.md        <- context file for Claude
  GEMINI.md        <- context file for Gemini
  .cursorrules     <- context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Managing Partner (Ops) | opus | $50/mo |
| Cases | Case Management Director | sonnet | $20/mo |
| Documents | Document & Contract Director | sonnet | $20/mo |
| Research | Legal Research Director | sonnet | $20/mo |
| Intake | Client Intake Director | sonnet | $20/mo |
| Docket | Docket & Deadlines Manager | sonnet | $15/mo |
| Billing | Legal Billing Director | sonnet | $15/mo |
| Clients | Client Relations Director | haiku | $10/mo |
| Compliance | Ethics & Compliance Director | haiku | $10/mo |
| Bizdev | Business Development Director | haiku | $10/mo |
| Admin | Admin Director | haiku | $10/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Law Firms on Gumroad → $99](https://fruverse.gumroad.com/l/aireadyu-law-firms)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-law-firms --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Law Firms on Gumroad → $99](https://fruverse.gumroad.com/l/aireadyu-law-firms)**

### Step 3: Extract to `~/Documents/AIReadyU-Law-Firms/`

```
~/Documents/AIReadyU-Law-Firms/
├── agents/          <- full instructions for each agent
├── skills/          <- gmail, calendar, drive, storage, port, etc.
├── vault/           <- 10 legal domains with synthetic data
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
| Chief of Staff | `~/Documents/AIReadyU-Law-Firms/agents/chief-of-staff` |
| Cases | `~/Documents/AIReadyU-Law-Firms/agents/cases` |
| Documents | `~/Documents/AIReadyU-Law-Firms/agents/documents` |
| Research | `~/Documents/AIReadyU-Law-Firms/agents/research` |
| Intake | `~/Documents/AIReadyU-Law-Firms/agents/intake` |
| Docket | `~/Documents/AIReadyU-Law-Firms/agents/docket` |
| Billing | `~/Documents/AIReadyU-Law-Firms/agents/billing` |
| Clients | `~/Documents/AIReadyU-Law-Firms/agents/clients` |
| Compliance | `~/Documents/AIReadyU-Law-Firms/agents/compliance` |
| Bizdev | `~/Documents/AIReadyU-Law-Firms/agents/bizdev` |
| Admin | `~/Documents/AIReadyU-Law-Firms/agents/admin` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Law-Firms/vault/` with your real files.

### Step 6: Enable Managing Partner

It reads your goals, creates issues for all agents, and produces the first firm dashboard.

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
