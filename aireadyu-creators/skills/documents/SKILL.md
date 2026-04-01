---
name: documents
description: >
  Parse, classify, and extract structured data from incoming documents that
  have not yet been routed to the vault. Handles email attachments, downloaded
  PDFs, and files in the intake folder before port routes them.
---

# Documents Skill

Documents is your intake parsing layer. Its job is narrow: read and extract
meaning from files that have arrived but not yet been classified and routed
to the vault.

Once a document is in the vault, agents read and interpret it directly using
their domain knowledge. This skill is only for unprocessed, incoming files.

## What This Skill Handles

- Email attachments pulled from Gmail before they've been routed
- PDFs downloaded from the web or received from third parties
- Files in the `intake/` folder awaiting port's routing pass
- Any file whose domain and type are unknown

## When to Use

- Classifying what type of document a file is (so port can route it)
- Extracting key fields from an attachment before deciding where to file it
- Identifying deadlines or obligations in a newly received document
- Comparing two incoming versions of a document

## Operations

| Operation | Description |
|-----------|-------------|
| `classify` | Determine the document type and vault domain |
| `extract_fields` | Pull structured fields (dates, amounts, names, addresses) |
| `summarize` | Produce a plain-language summary |
| `find_clause` | Search for a specific clause or term |
| `detect_obligations` | Identify action items, deadlines, or required responses |
| `compare` | Diff two versions and highlight changes |

## Document Types Supported

- Tax forms (1040, 1099, W-2, K-1)
- Insurance policies and declarations pages
- Contracts and agreements
- Receipts and invoices
- Medical records and lab results
- Lease and real estate documents
- Legal filings and correspondence
- Financial statements
- Identity documents (license, passport)

## Handoff Protocol

After parsing an incoming document:
1. Return the classified domain and document type to the calling agent
2. Flag any detected deadlines or obligations with urgency level
3. Hand the file to `port` for routing to the correct vault folder
4. Port carries it to `<domain>/00_current/` or `<domain>/01_prior/YYYY/`

## Usage Rules

- Retrieve the file via `drive` first, then pass it here for parsing
- When extracting fields, return the raw value and the page/section it came from
- Do not surface sensitive data (SSN, full account numbers) in task comments
- If a file is already in the vault, the owning agent reads it directly — do not re-parse through this skill
