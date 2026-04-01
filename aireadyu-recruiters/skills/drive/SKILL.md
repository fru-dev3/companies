---
name: drive
description: >
  Upload, download, list, and manage files in Google Drive via the Google
  Workspace CLI (gws). Use when interacting directly with Google Drive —
  uploading files, creating docs, searching, or sharing. For vault-level
  operations (reading/writing to canonical vault paths), use the storage skill.
---

# Drive Skill

Drive operations are executed through the Google Workspace CLI (`gws`).
All commands below are real — run them directly.

This skill handles direct Google Drive interactions. It is separate from the
`storage` skill, which is the vault abstraction layer. Use `drive` when you
need to interact with Google Drive itself (uploading, downloading, sharing).
Use `storage` when you need to read/write to canonical vault paths.

## Commands

### Upload a file

```bash
gws drive +upload ./report.pdf
```

With a custom name:

```bash
gws drive +upload ./data.csv --name "Sales Data Q1 2026.csv"
```

To a specific folder:

```bash
gws drive +upload ./report.pdf --parent FOLDER_ID
```

### List files

```bash
gws drive files list --params '{"pageSize": 10}'
```

Search by name:

```bash
gws drive files list --params '{"q": "name contains '\''tax return'\''", "pageSize": 10}'
```

Search by type:

```bash
gws drive files list --params '{"q": "mimeType = '\''application/pdf'\''", "pageSize": 20}'
```

### Download a file

```bash
gws drive files get --params '{"fileId": "FILE_ID", "alt": "media"}' > output.pdf
```

### Create a Google Doc

```bash
gws drive files create --json '{
  "name": "Meeting Notes - 2026-04-01",
  "mimeType": "application/vnd.google-apps.document",
  "parents": ["FOLDER_ID"]
}'
```

### Create a folder

```bash
gws drive files create --json '{
  "name": "New Folder",
  "mimeType": "application/vnd.google-apps.folder",
  "parents": ["PARENT_FOLDER_ID"]
}'
```

### Move a file to a different folder

```bash
gws drive files update --params '{"fileId": "FILE_ID", "addParents": "NEW_FOLDER_ID", "removeParents": "OLD_FOLDER_ID"}'
```

### Share a file

```bash
gws drive permissions create --params '{"fileId": "FILE_ID"}' --json '{
  "role": "reader",
  "type": "user",
  "emailAddress": "recipient@example.com"
}'
```

### Get file metadata

```bash
gws drive files get --params '{"fileId": "FILE_ID", "fields": "id,name,mimeType,size,modifiedTime,parents"}'
```

## When to Use Drive vs Storage

| Need | Use |
|------|-----|
| Upload a file to Google Drive | `drive` |
| Download a file from Google Drive | `drive` |
| Share a file with someone | `drive` |
| Read a file from the vault | `storage` |
| Write agent output to the vault | `storage` |
| Route an incoming file to the vault | `port` |

## Usage Rules

- When uploading to the vault, always use canonical vault paths (e.g., `tax/00_current/`)
- Use vault naming convention for files: `YYYY-MM-DD_short-description.ext`
- Check for existing files before uploading to avoid duplicates
- Max file upload size: 5,120 GB
- For large batch operations, use the raw API endpoints with pagination
