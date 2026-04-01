---
name: port
description: >
  Vault porter. Picks up files from the intake folder, classifies each one,
  carries it to the correct vault location, and sets it down in the right place.
  Like a porter who takes your luggage and knows exactly which room it belongs in.
---

# Port Skill

Port is the vault porter. When files arrive — from email attachments, downloads,
exports, or manual drops — they land in the `intake/` folder unsorted. Port
picks each one up, figures out where it belongs, renames it to vault convention,
and carries it to the correct vault folder.

Port does not interpret file contents deeply. It classifies and routes. For
field extraction or content analysis, use the `documents` skill first, then
port carries the result to the vault.

Port's routing authority is `vault/vault-structure.json`. It does not invent its own
taxonomy — it routes to the vault exactly as the vault is defined.

## When to Use

- When new files have arrived in `intake/`
- When running a periodic vault triage pass
- After the `gmail` skill saves an email attachment to `intake/`
- When the user drops a batch of unsorted documents

## Operations

| Operation | Description |
|-----------|-------------|
| `scan` | List all unprocessed files in `intake/` |
| `classify` | Determine the vault domain and document type of a file |
| `carry` | Move a classified file to its correct vault folder |
| `rename` | Apply vault naming convention before placing |
| `tag` | Apply metadata tags after placing |
| `flag` | Surface files that could not be confidently classified |

## Routing Table

Derived from `vault/vault-structure.json`. All paths use the `00_current/` subfolder
for current documents or `01_prior/YYYY/` for historical ones.

| Vault Domain | Carry Here When... |
|--------------|-------------------|
| `business/` | LLC doc, contract, state filing, business plan, invoice, rental agreement |
| `career/` | Resume, offer letter, performance review, certification, employment contract |
| `civic/` | Voter registration, jury summons, community service record |
| `credit/` | Credit report, score letter, loan document, credit card application |
| `digital/` | Account credentials, password export, privacy audit, breach notification |
| `estate/` | Deed, mortgage statement, HOA doc, property tax statement, appraisal |
| `family/` | Family document, shared finance record, eldercare plan, school record |
| `health/` | Medical record, prescription, lab result, EOB, dental/vision doc |
| `home/` | Warranty, appliance manual, utility bill, maintenance invoice, security record |
| `learning/` | Diploma, transcript, course certificate, continuing education record |
| `legacy/` | Family tree document, oral history transcript, donation receipt |
| `legal/` | Will, trust, POA, insurance policy, identity doc (passport, license, SSN), court filing |
| `mind/` | Journal entry, personal notes, ideas, therapy record, goals document |
| `play/` | Trip itinerary, event ticket, hobby record, travel reward statement |
| `social/` | Membership card, gift receipt, networking contact list |
| `tax/` | Tax return, W-2, 1099, receipt, CPA letter, estimated payment |
| `time/` | OKR document, review template, checklist, schedule template |
| `transit/` | Vehicle title, registration, maintenance record, passport, booking confirmation |
| `wealth/` | Bank statement, investment statement, 401k/HSA doc, benefits enrollment |
| `intake/unclassified/` | Could not be confidently classified — needs human review |

## Year Routing

- If the document is from the current year → `<domain>/00_current/`
- If the document is from a prior year → `<domain>/01_prior/YYYY/`
- Determine the year from the document date, filename, or content

## Naming Convention

Before placing a file, rename it:
```
YYYY-MM-DD_short-description.ext
```
Examples:
- `2026-03-15_wells-fargo-statement-feb.pdf`
- `2025-04-15_federal-tax-return-2024.pdf`
- `2026-01-10_anthem-eob-jan.pdf`

## Implementation

Port uses the `drive` skill to move files within Google Drive:

Scan intake:
```bash
gws drive files list --params '{"q": "'\''INTAKE_FOLDER_ID'\'' in parents", "pageSize": 50}'
```

Move a file to its vault destination:
```bash
gws drive files update --params '{"fileId": "FILE_ID", "addParents": "DESTINATION_FOLDER_ID", "removeParents": "INTAKE_FOLDER_ID"}'
```

Rename a file:
```bash
gws drive files update --params '{"fileId": "FILE_ID"}' --json '{"name": "2026-03-15_document-name.pdf"}'
```

## Usage Rules

- Classify before carrying — never move without a confident label
- Below confidence threshold → `intake/unclassified/` and flag for human review
- After placing: tag with domain, document type, source
- Do not delete from intake — carry, don't discard
- If deeper content extraction is needed before routing, call `documents` first
