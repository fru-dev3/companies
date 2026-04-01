---
name: workflow
description: >
  Create tasks, trigger automations, chain multi-step operations, and track
  completion across agents. Coordinates work through the Paperclip task system.
  The execution engine that turns agent decisions into structured, trackable work.
---

# Workflow Skill

Workflow is the execution and coordination layer. When an agent makes a
decision that results in work — whether for itself or another agent —
workflow structures it, tracks it, and ensures it gets done.

Workflow operates through the Paperclip task system. Tasks are created as
Paperclip issues, assigned to agents, and tracked through the standard
heartbeat cycle.

## When to Use

- Breaking a complex task into trackable subtasks
- Coordinating work that spans multiple agents
- Scheduling a task to run at a future time or on a cadence
- Monitoring whether a previous task completed
- Escalating blocked or overdue work

## Implementation: Paperclip Task System

All workflow operations map to Paperclip API calls. See the `paperclip`
skill for full API reference.

### Create a task for an agent

```bash
curl -X POST "$PAPERCLIP_API_URL/api/companies/$PAPERCLIP_COMPANY_ID/issues" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Review Q1 tax documents",
    "description": "New 1099s arrived in vault. Review and flag deductions.",
    "status": "todo",
    "priority": "high",
    "assigneeAgentId": "TAX_AGENT_ID",
    "parentId": "PARENT_TASK_ID"
  }'
```

### Create subtasks for multi-agent work

```bash
# Parent task
curl -X POST "$PAPERCLIP_API_URL/api/companies/$PAPERCLIP_COMPANY_ID/issues" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -d '{"title": "Process job change", "status": "todo", "priority": "high"}'

# Subtask 1: Career agent updates records
curl -X POST "$PAPERCLIP_API_URL/api/companies/$PAPERCLIP_COMPANY_ID/issues" \
  -d '{"title": "Update career records", "parentId": "PARENT_ID", "assigneeAgentId": "CAREER_AGENT_ID"}'

# Subtask 2: Wealth agent adjusts projections
curl -X POST "$PAPERCLIP_API_URL/api/companies/$PAPERCLIP_COMPANY_ID/issues" \
  -d '{"title": "Recalculate income projections", "parentId": "PARENT_ID", "assigneeAgentId": "WEALTH_AGENT_ID"}'

# Subtask 3: Tax agent models impact
curl -X POST "$PAPERCLIP_API_URL/api/companies/$PAPERCLIP_COMPANY_ID/issues" \
  -d '{"title": "Model tax impact of job change", "parentId": "PARENT_ID", "assigneeAgentId": "TAX_AGENT_ID"}'
```

### Check task status

```bash
curl "$PAPERCLIP_API_URL/api/issues/$ISSUE_ID" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY"
```

### Escalate a blocked task

```bash
curl -X PATCH "$PAPERCLIP_API_URL/api/issues/$ISSUE_ID" \
  -H "Authorization: Bearer $PAPERCLIP_API_KEY" \
  -d '{"status": "blocked", "comment": "Blocked: need CPA input before proceeding. Escalating to user."}'
```

## Common Coordination Patterns

### Intake pipeline
1. Workflow creates a task for `port` to process `intake/`
2. Port classifies and routes files
3. Workflow creates subtasks for each agent whose vault domain received new files

### Life event cascade
A single life event (job change, move, new baby) triggers tasks across agents:
1. Create a parent task for the event
2. Create subtasks assigned to each affected agent
3. Each agent processes its subtask independently
4. Workflow monitors completion of all subtasks

### Recurring maintenance
Schedule recurring tasks for periodic operations:
- Monthly: vault triage (port), budget review (wealth > budget)
- Quarterly: analytics reports, tax estimate review
- Annually: insurance renewal check, estate plan review

## Usage Rules

- Always set a clear owner (assigneeAgentId) and priority
- For multi-agent work, use subtasks with a shared parent
- Include vault paths in task descriptions so agents know where to read/write
- Do not create tasks without an assignee — unowned tasks become invisible
- When escalating, include what is blocked and who needs to act
