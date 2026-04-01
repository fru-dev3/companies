
# AI Ready U: Life

**15 AI agents that manage your personal life. Private. On your machine.**

## Install

```bash
npx companies.sh add fru-dev3/companies/aireadyu-life --include company,agents,projects,tasks
```

This creates 15 agents in Paperclip (14 domain + 1 Chief of Staff) with bootstrap tasks and sample goals. Agent instructions are loaded externally from `~/Documents/AIReadyU-Life/`.

## Architecture

```
GitHub (free):
  agents/          ← agent shells (name, title, budget, capabilities)
  .paperclip.yaml  ← adapter config, models, heartbeats
  tasks/           ← bootstrap issues
  vault/           ← vault schema (vault-structure.json)

~/Documents/AIReadyU-Life/ (paid pack):
  agents/          ← full agent instructions (AGENTS.md)
  skills/          ← 12 tool skills (gmail, calendar, drive, etc.)
  vault/           ← 14 life domains with synthetic data
  PROMPTS.md       ← 200+ ready-to-use prompts
  CLAUDE.md        ← context file for Claude
  GEMINI.md        ← context file for Gemini
  .cursorrules     ← context file for Cursor
```

## Agents

| Agent | Title | Model | Budget |
|-------|-------|-------|--------|
| Chief of Staff | Life Operations Director | opus | $50/mo |
| Tax | Chief Tax Officer | sonnet | $20/mo |
| Health | Chief Medical Officer | sonnet | $20/mo |
| Wealth | Chief Capital Officer | sonnet | $20/mo |
| Career | Chief Talent Officer | sonnet | $20/mo |
| Legal | Chief Legal Officer | sonnet | $15/mo |
| Business | Chief Corporate Officer | sonnet | $20/mo |
| Insurance | Chief Risk Officer | haiku | $10/mo |
| Estate | Chief Property Officer | haiku | $10/mo |
| Home | Chief Household Officer | haiku | $5/mo |
| Family | Chief Family Officer | haiku | $10/mo |
| Learning | Chief Learning Officer | haiku | $5/mo |
| Mind | Chief Mindfulness Officer | haiku | $5/mo |
| Explore | Chief Adventure Officer | haiku | $5/mo |
| Vehicles | Chief Fleet Officer | haiku | $5/mo |

## Get the Pack

The agents are free. The instructions, skills, and vault make them operational.

**[Get AI Ready U: Life on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-life)**

## How It Works

### Step 1: Install agents (free)

```bash
npx companies.sh add fru-dev3/companies/aireadyu-life --include company,agents,projects,tasks
```

### Step 2: Buy the pack

**[Get AI Ready U: Life on Gumroad → $49](https://fruverse.gumroad.com/l/aireadyu-life)**

### Step 3: Extract to `~/Documents/AIReadyU-Life/`

```
~/Documents/AIReadyU-Life/
├── agents/          ← full instructions for each agent
├── skills/          ← gmail, calendar, drive, storage, port, etc.
├── vault/           ← 14 life domains with synthetic data
├── PROMPTS.md
├── CLAUDE.md
├── GEMINI.md
└── .cursorrules
```

### Step 4: Connect each agent to external instructions

For each of the 15 agents in the Paperclip dashboard:

1. Click on the agent
2. Click **Advanced**
3. Switch from **Managed** to **External**
4. Paste the root folder path (shown in each agent's description)
5. Hit **Save**

| Agent | Root Folder Path |
|-------|-----------------|
| Chief of Staff | `~/Documents/AIReadyU-Life/agents/chief-of-staff` |
| Tax | `~/Documents/AIReadyU-Life/agents/tax` |
| Health | `~/Documents/AIReadyU-Life/agents/health` |
| Wealth | `~/Documents/AIReadyU-Life/agents/wealth` |
| Career | `~/Documents/AIReadyU-Life/agents/career` |
| Legal | `~/Documents/AIReadyU-Life/agents/legal` |
| Insurance | `~/Documents/AIReadyU-Life/agents/insurance` |
| Business | `~/Documents/AIReadyU-Life/agents/business` |
| Estate | `~/Documents/AIReadyU-Life/agents/estate` |
| Home | `~/Documents/AIReadyU-Life/agents/home` |
| Family | `~/Documents/AIReadyU-Life/agents/family` |
| Learning | `~/Documents/AIReadyU-Life/agents/learning` |
| Mind | `~/Documents/AIReadyU-Life/agents/mind` |
| Explore | `~/Documents/AIReadyU-Life/agents/explore` |
| Vehicles | `~/Documents/AIReadyU-Life/agents/vehicles` |

### Step 5: Drop your documents

Replace the synthetic data in `~/Documents/AIReadyU-Life/vault/` with your real files.

### Step 6: Enable Chief of Staff

It reads your goals, creates issues for all agents, and produces the first life dashboard.

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
