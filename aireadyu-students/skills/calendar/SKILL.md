---
name: calendar
description: >
  Read, create, and manage Google Calendar events via the Google Workspace CLI
  (gws). Use for scheduling, availability checks, deadline tracking, and
  recurring event management.
---

# Calendar Skill

Calendar operations are executed through the Google Workspace CLI (`gws`).
All commands below are real — run them directly.

## Commands

### View upcoming agenda

```bash
gws calendar +agenda
```

With timezone:

```bash
gws calendar +agenda --timezone America/Chicago
```

### Create an event

```bash
gws calendar +insert \
  --summary "Doctor appointment" \
  --start "2026-04-01T10:00:00" \
  --end "2026-04-01T11:00:00"
```

With location and description:

```bash
gws calendar +insert \
  --summary "Tax review with CPA" \
  --start "2026-04-10T14:00:00" \
  --end "2026-04-10T15:00:00" \
  --location "123 Main St, Suite 200" \
  --description "Bring: 2025 return, W-2s, 1099s. Vault: tax/00_current/"
```

### Quick add (natural language)

```bash
gws calendar +quickAdd "Dentist appointment Thursday at 2pm"
```

### List events in a date range

```bash
gws calendar events list --params '{
  "calendarId": "primary",
  "timeMin": "2026-04-01T00:00:00Z",
  "timeMax": "2026-04-30T23:59:59Z",
  "singleEvents": true,
  "orderBy": "startTime"
}'
```

### Update an event

```bash
gws calendar events patch --params '{"calendarId": "primary", "eventId": "EVENT_ID"}' \
  --json '{"summary": "Updated title", "location": "New location"}'
```

### Delete an event

```bash
gws calendar events delete --params '{"calendarId": "primary", "eventId": "EVENT_ID"}'
```

### Create a recurring event

```bash
gws calendar events insert --params '{"calendarId": "primary"}' --json '{
  "summary": "Weekly review",
  "start": {"dateTime": "2026-04-01T09:00:00", "timeZone": "America/Chicago"},
  "end": {"dateTime": "2026-04-01T09:30:00", "timeZone": "America/Chicago"},
  "recurrence": ["RRULE:FREQ=WEEKLY;BYDAY=MO"]
}'
```

## Usage Rules

- Always check for conflicts before creating events
- Default to the primary calendar unless the user specifies otherwise
- For deadlines (renewals, filings, expirations), create events with reminders at 30 days and 7 days
- Include the vault path in the event description when the event is tied to a vault domain
- Coordinate with agents that share the same time blocks (Health for appointments, Transit for travel)

## Vault Integration

Link calendar events to vault domains by including the vault path in the description:

- Medical appointments → `health/00_current/`
- Legal/attorney meetings → `legal/00_current/`
- CPA/financial advisor meetings → `tax/00_current/` or `wealth/00_current/`
- Travel bookings → `play/00_current/` or `transit/00_current/`

After an appointment, the owning agent should ensure any resulting documents are routed to the vault.
