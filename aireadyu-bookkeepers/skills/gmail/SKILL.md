---
name: gmail
description: >
  Read, send, search, and manage email via the Google Workspace CLI (gws).
  Use for all email communication, inbox triage, replying, forwarding, and
  attachment handling. All outbound emails must include the agent signature.
---

# Gmail Skill

Gmail operations are executed through the Google Workspace CLI (`gws`).
All commands below are real — run them directly.

## Agent Signature (Required)

Every email sent by an agent MUST include a signature block that clearly
identifies it as agent-generated. This is non-negotiable — recipients must
know they are communicating with an AI agent, not the user directly.

Append this to the end of every outbound email body:

```
---
Sent by [Agent Name] on behalf of [User Name]
This message was composed by an AI agent using Omega Life OS.
For direct communication, please reply to this email.
```

Example for the Health agent:
```
---
Sent by Health Agent on behalf of Alex Rivera
This message was composed by an AI agent using Omega Life OS.
For direct communication, please reply to this email.
```

**Rules:**
- The signature goes on every send, reply, and forward that includes agent-written content
- Never impersonate the user — always disclose agent involvement
- If the user provides their own signature block, append the agent disclosure below it
- The user's name in the signature should match their configured identity

## Commands

### Send an email

```bash
gws gmail +send --to recipient@example.com --subject "Subject" --body "Message body"
```

With CC, BCC, and HTML:

```bash
gws gmail +send \
  --to recipient@example.com \
  --cc someone@example.com \
  --bcc another@example.com \
  --subject "Subject" \
  --body "<b>HTML content</b>" \
  --html
```

With attachments:

```bash
gws gmail +send \
  --to recipient@example.com \
  --subject "Documents attached" \
  --body "Please see attached." \
  -a /path/to/file1.pdf \
  -a /path/to/file2.csv
```

Send from a specific alias:

```bash
gws gmail +send \
  --to recipient@example.com \
  --subject "Subject" \
  --body "Message" \
  --from alias@example.com
```

### Reply to a message

```bash
gws gmail +reply --message-id MESSAGE_ID --body "Reply body with agent signature."
```

### Forward a message

```bash
gws gmail +forward --message-id MESSAGE_ID --to recipient@example.com
```

### Search emails

```bash
gws gmail messages list --params '{"q": "from:someone@example.com subject:invoice"}'
```

### Read a specific message

```bash
gws gmail messages get --params '{"id": "MESSAGE_ID", "userId": "me"}'
```

### List labels

```bash
gws gmail labels list
```

### Apply a label

```bash
gws gmail messages modify --params '{"id": "MESSAGE_ID", "userId": "me"}' \
  --json '{"addLabelIds": ["LABEL_ID"]}'
```

## Tone and Formatting

- Write in a professional, clear, and concise tone
- Match the formality of the conversation (formal for doctors, attorneys, CPAs; casual for family, friends)
- Use the user's first name in the greeting when writing to people they know
- Keep emails short — get to the point in the first sentence
- For scheduling or action requests, include specific dates, times, and next steps
- For follow-ups, reference the previous conversation or document by name

## Usage Rules

- Never send email without explicit user instruction or an approved routine task
- Always confirm the recipient before sending
- Read the full thread before replying to ensure context
- When summarizing for another agent: include sender, date, subject, and action items
- Use labels to mark threads as processed by a specific agent
- If authentication fails, surface the error — do not retry silently
- Never include sensitive data (SSN, full account numbers, passwords) in email body

## Vault Integration

- **Attachments** — save to `intake/` and let `port` route them to the correct vault domain
- **Important correspondence** — save to the relevant vault folder via the `storage` skill:
  - Tax notices → `tax/00_current/`
  - Insurance documents → `legal/00_current/`
  - Business contracts → `business/00_current/`
  - Medical correspondence → `health/00_current/`
