# AI Ready U: Life — Paperclip Installation Guide

This file is the complete installation playbook. Follow every step in order.

## Prerequisites

- Paperclip is installed and running locally (`npx paperclipai dashboard`)
- The Paperclip API is accessible at `http://127.0.0.1:3100`
- You have a gateway auth token

```bash
export PAPERCLIP_API_URL="http://127.0.0.1:3100"
export PAPERCLIP_API_KEY="<your-gateway-auth-token>"
export AIREADYU_ROOT="<absolute-path-to-aireadyu-life-folder>"
```

---

## Step 1: Create Company

```bash
curl -X POST "$PAPERCLIP_API_URL/api/companies" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "AI Ready U: Life",
    "prefix": "ARU",
    "description": "Personal AI operating system. 15 agents managing 14 life domains.",
    "icon": "crown"
  }'
```

Save the returned company ID:
```bash
export PAPERCLIP_COMPANY_ID="<returned-company-id>"
```

---

## Step 2: Create All 15 Agents

Read `paperclip/agents.json`. Create agents in this order:
1. **Chief of Staff first** (no `reportsTo`)
2. All 14 domain agents

For each agent:

```bash
curl -X POST "$PAPERCLIP_API_URL/api/companies/$PAPERCLIP_COMPANY_ID/agents" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "<agent.name>",
    "role": "general",
    "title": "<agent.title>",
    "icon": "<agent.icon>",
    "capabilities": "<agent.capabilities>",
    "adapterType": "claude_local",
    "adapterConfig": {
      "model": "<agent.adapterConfig.model>",
      "instructionsFilePath": "<AIREADYU_ROOT>/<agent.adapterConfig.instructionsFilePath>"
    },
    "runtimeConfig": {
      "heartbeat": {
        "enabled": false,
        "intervalSec": <agent.runtimeConfig.heartbeat.intervalSec>,
        "cooldownSec": 10,
        "wakeOnDemand": true,
        "maxConcurrentRuns": 1
      }
    },
    "budgetMonthlyCents": 0,
    "permissions": { "canCreateAgents": <true for chief-of-staff, false otherwise> }
  }'
```

**Save every returned agent ID mapped to its shortname.**

After all 15 are created, set `reportsTo` on each domain agent:

```bash
curl -X PATCH "$PAPERCLIP_API_URL/api/agents/<domain-agent-id>" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"reportsTo": "<chief-of-staff-id>"}'
```

### Agent hierarchy when complete

```
Chief of Staff (crown)
├── Tax (cog) — Chief Tax Officer
├── Health (sparkles) — Chief Medical Officer
├── Wealth (gem) — Chief Capital Officer
├── Career (rocket) — Chief Talent Officer
├── Legal (swords) — Chief Legal Officer
├── Insurance (shield) — Chief Risk Officer
├── Business (target) — Chief Corporate Officer
├── Estate (database) — Chief Property Officer
├── Home (wrench) — Chief Household Officer
├── Family (heart) — Chief Family Officer
├── Learning (lightbulb) — Chief Learning Officer
├── Mind (brain) — Chief Mindfulness Officer
├── Explore (star) — Chief Adventure Officer
└── Vehicles (radar) — Chief Fleet Officer
```

---

## Step 3: Import and Assign Skills

**Note:** Skills are included in the paid AI Ready U: Life pack. If you haven't purchased it yet, skip this step.

### Import all 12 skills

```bash
for skill in gmail calendar drive storage port workflow contacts documents research writing booking analytics; do
  curl -X POST "$PAPERCLIP_API_URL/api/companies/$PAPERCLIP_COMPANY_ID/skills/import" \
    -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
    -H "Content-Type: application/json" \
    -d "{\"source\": \"$AIREADYU_ROOT/skills/$skill\"}"
done
```

### Assign skills to agents

Read the `metadata.aireadyu.skills` array from each agent in `agents.json`. For each agent:

```bash
curl -X POST "$PAPERCLIP_API_URL/api/agents/<agent-id>/skills/sync" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"desiredSkills": ["<skill-key-1>", "<skill-key-2>"]}'
```

---

## Step 4: Create Project

Routines require a `projectId`. Create the project first:

```bash
curl -X POST "$PAPERCLIP_API_URL/api/companies/$PAPERCLIP_COMPANY_ID/projects" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"name": "AI Ready U: Life", "description": "Personal AI operating system — 14 life domains managed by 15 agents."}'
```

```bash
export PAPERCLIP_PROJECT_ID="<returned-project-id>"
```

---

## Step 5: Create Routines

Read `paperclip/routines.json`. For each routine:

```bash
# Create routine
curl -X POST "$PAPERCLIP_API_URL/api/companies/$PAPERCLIP_COMPANY_ID/routines" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "<routine.title>",
    "description": "<routine.description>",
    "assigneeAgentId": "<resolved-agent-uuid>",
    "projectId": "<PAPERCLIP_PROJECT_ID>",
    "priority": "<routine.priority>",
    "concurrencyPolicy": "<routine.concurrencyPolicy>",
    "catchUpPolicy": "<routine.catchUpPolicy>"
  }'

# Add schedule trigger
curl -X POST "$PAPERCLIP_API_URL/api/routines/<routine-id>/triggers" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"kind": "schedule", "cronExpression": "<trigger.cronExpression>"}'
```

---

## Step 6: Create Bootstrap Issues

Read `paperclip/issues.json`. Create parent issues then subtasks:

```bash
# Parent issue
curl -X POST "$PAPERCLIP_API_URL/api/companies/$PAPERCLIP_COMPANY_ID/issues" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "<issue.title>",
    "description": "<issue.description>",
    "assigneeAgentId": "<resolved-agent-uuid>",
    "priority": "<issue.priority>",
    "status": "todo"
  }'
```

---

## Step 7: Verify Installation

```bash
# Count agents (expect 15)
curl "$PAPERCLIP_API_URL/api/companies/$PAPERCLIP_COMPANY_ID/agents" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" | python3 -c "
import json, sys; print(f'Agents: {len(json.load(sys.stdin))}')
"
```

### Expected counts

| Component | Count |
|-----------|-------|
| Agents | 15 |
| Skills | 12 (after importing paid pack) |
| Routines | 19 |
| Goals | 7 categories |
| Bootstrap Issues | 5 parent + 14 subtasks = 19 |

---

## Step 8: Enable Agents

All agents are created with heartbeats **OFF**. To start:

```bash
# Enable one agent
curl -X PATCH "$PAPERCLIP_API_URL/api/agents/<agent-id>" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"runtimeConfig": {"heartbeat": {"enabled": true}}}'
```

**Recommended:** Enable only the Chief of Staff first. It will review all domains, create tasks, and produce the first daily brief. Watch its output before enabling other agents.

---

## Get the Skills + Vault

Without the paid pack, agents can be created but cannot operate (no skills, no vault data).

**[Get AI Ready U: Life on Gumroad → $29](https://fruverse.gumroad.com/l/aireadyu-life)**
