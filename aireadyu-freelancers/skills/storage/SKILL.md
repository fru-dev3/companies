---
name: storage
description: >
  The vault access layer. The vault is the structured, canonical record of the
  user's life. All vault operations go through this skill. Use for reading,
  writing, searching, and organizing files in the vault. For raw Google Drive
  operations (upload, share, download), use the drive skill instead.
---

# Storage Skill

The vault is the source of truth. It lives in Google Drive, organized into
domain folders that map 1:1 to agents. Every agent reads from and writes to
the vault through this skill using canonical vault paths.

This skill is the vault abstraction layer. For raw Google Drive operations
(uploading files, sharing, downloading), use the `drive` skill. For routing
incoming files to the correct vault location, use the `port` skill.

## Vault Structure

Every domain folder contains exactly two subfolders:

- `00_current/` — all active, current documents
- `01_prior/` — historical documents, subdivided by year (`01_prior/2024/`, `01_prior/2025/`)

The 19 vault domains (one per agent):

| Domain | Agent | What Goes Here |
|--------|-------|---------------|
| `business/` | business | LLC docs, contracts, filings, invoices, rental properties |
| `career/` | career | Resumes, certifications, reviews, offer letters, contracts |
| `civic/` | civic | Voter registration, jury duty, community service |
| `credit/` | credit | Credit reports, scores, disputes, loan documents |
| `digital/` | digital | Credentials, account maps, privacy records |
| `estate/` | estate | Property records, deeds, mortgages, HOA docs, appraisals |
| `family/` | family | Family documents, shared finances, eldercare, children's records |
| `health/` | health | Medical records, prescriptions, lab results, dental, vision |
| `home/` | home | Warranties, appliance manuals, utility data, maintenance |
| `learning/` | learning | Degrees, transcripts, courses, certificates |
| `legacy/` | legacy | Family tree, oral histories, philanthropic records |
| `legal/` | legal | Wills, trusts, POA, insurance policies, identity docs, contracts |
| `mind/` | mind | Journal, ideas, notes, therapy logs, goals, reference material |
| `play/` | play | Travel itineraries, event tickets, hobbies, trip logs |
| `social/` | social | Memberships, gift history, contact interactions |
| `tax/` | tax | Tax returns, W-2s, 1099s, receipts, CPA correspondence |
| `time/` | time | OKRs, daily/weekly reviews, checklists |
| `transit/` | transit | Vehicle titles, registration, maintenance, travel docs |
| `wealth/` | wealth | Bank statements, investment statements, retirement, benefits |

There is also an `intake/` folder for unprocessed files awaiting routing by
the `port` skill.

## Vault Path Rules

- All paths are relative to the vault root: `<domain>/00_current/` or `<domain>/01_prior/YYYY/`
- File naming convention: `YYYY-MM-DD_short-description.ext`
- Current year documents go in `00_current/`
- Prior year documents go in `01_prior/YYYY/`
- When unsure which domain, drop in `intake/` and let `port` route it
- The vault structure is defined in `vault/vault-structure.json` — treat it as the authoritative schema

## Examples

Save a current tax document:
```
vault path: tax/00_current/2026-W2-acme-corp.pdf
```

Save a prior year health record:
```
vault path: health/01_prior/2025/2025-03-15_annual-physical.pdf
```

Save a current legal document:
```
vault path: legal/00_current/2026-03-01_auto-policy-renewal.pdf
```

## Implementation

All vault operations use the Google Workspace CLI (`gws`) against Google Drive.
The vault root is a top-level Drive folder. Each domain is a subfolder.

List a vault domain:
```bash
gws drive files list --params '{"q": "name = '\''00_current'\'' and '\''DOMAIN_FOLDER_ID'\'' in parents"}'
```

Upload to vault:
```bash
gws drive +upload ./document.pdf --parent VAULT_DOMAIN_FOLDER_ID --name "2026-03-28_document-name.pdf"
```

Search vault:
```bash
gws drive files list --params '{"q": "fullText contains '\''tax return'\'' and '\''VAULT_ROOT_ID'\'' in parents", "pageSize": 20}'
```

## Cross-Agent Access

Agents have a primary vault domain but can read from others:

| Agent | Primary | Also Reads |
|-------|---------|------------|
| tax | tax | wealth, business, estate, career |
| legal | legal | health, family, digital, estate |
| wealth | wealth | tax, business, career |
| health | health | legal, wealth |
| estate | estate | home, legal, tax, wealth |
| business | business | tax, legal, wealth |
| family | family | health, legal, wealth |
| time | time | all domains (coordination) |
