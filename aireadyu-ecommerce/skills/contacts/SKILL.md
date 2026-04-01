---
name: contacts
description: >
  Look up, create, and manage contacts via Google People API through the Google
  Workspace CLI (gws). Use to find people by name or relationship, update
  contact details, and tag contacts for use by other agents.
---

# Contacts Skill

Contacts operations are executed through the Google Workspace CLI (`gws`)
using the People API. All commands below are real — run them directly.

## Commands

### Search for a contact

```bash
gws people people searchContacts --params '{"query": "John Smith", "readMask": "names,emailAddresses,phoneNumbers"}'
```

### List all contacts

```bash
gws people people connections list --params '{
  "resourceName": "people/me",
  "personFields": "names,emailAddresses,phoneNumbers,organizations",
  "pageSize": 50
}'
```

### Create a new contact

```bash
gws people people createContact --json '{
  "names": [{"givenName": "Jane", "familyName": "Doe"}],
  "emailAddresses": [{"value": "jane@example.com", "type": "work"}],
  "phoneNumbers": [{"value": "+15551234567", "type": "mobile"}],
  "organizations": [{"name": "Acme Corp", "title": "CPA"}]
}'
```

### Update a contact

```bash
gws people people updateContact --params '{
  "resourceName": "people/CONTACT_ID",
  "updatePersonFields": "phoneNumbers"
}' --json '{
  "phoneNumbers": [{"value": "+15559876543", "type": "mobile"}]
}'
```

### Get a specific contact

```bash
gws people people get --params '{
  "resourceName": "people/CONTACT_ID",
  "personFields": "names,emailAddresses,phoneNumbers,organizations,memberships"
}'
```

### List contact groups (labels)

```bash
gws people contactGroups list
```

## Usage Rules

- Always search for an existing contact before creating a new one to avoid duplicates
- Tag contacts consistently: use labels like `family`, `friend`, `colleague`, `vendor`, `advisor`, `client`
- When creating a contact from an email, pull name, email, company, and title from the message
- The Family and Social agents own relationship context — defer to them for categorization decisions

## Vault Integration

For key contacts (attorneys, CPAs, doctors, business partners), note the
relationship in the relevant vault domain so agents have context:

- Attorneys → `legal/00_current/`
- CPAs / financial advisors → `wealth/00_current/` or `tax/00_current/`
- Medical providers → `health/00_current/`
- Business contacts → `business/00_current/`

The contact record lives in Google Contacts; the vault note gives the agent
context about which documents relate to that person.
