# Vault

This directory contains the **vault schema** — the blueprint for the 10-domain folder structure.

The full vault — with pre-built folders, synthetic data, and ready-to-use structure — is included in the **AI Ready U: Healthcare pack**.

**[Get the full vault + skills → $79](https://fruverse.gumroad.com/l/aireadyu-healthcare)**

After purchase, extract to `~/Documents/AIReadyU-Healthcare/`. The agents already know to look there.

```
~/Documents/AIReadyU-Healthcare/
├── skills/              <- 12 tool skills (gmail, calendar, drive, etc.)
└── vault/               <- 10 healthcare domains with synthetic data
    ├── patients/
    │   ├── 00_current/
    │   └── 01_prior/YYYY/
    ├── scheduling/
    ├── billing/
    └── ...
```

## 10 Healthcare Domains

| Domain | Folder | What Goes Here |
|--------|--------|---------------|
| Patients | `patients/` | Patient communications, appointment reminders, satisfaction surveys, retention records |
| Scheduling | `scheduling/` | Appointment logs, wait list records, no-show tracking, provider availability templates |
| Billing | `billing/` | Claims submissions, denial logs, ERA/EOB records, AR aging reports, revenue cycle dashboards |
| Clinical Docs | `clinical-docs/` | SOAP note templates, documentation standards, chart audit checklists, CDI improvement plans |
| Insurance | `insurance/` | Prior auth requests, eligibility verification records, payer follow-up logs, insurance docs |
| Referrals | `referrals/` | Specialist referral records, care coordination notes, transitions of care documentation |
| Compliance | `compliance/` | HIPAA checklists, staff training records, incident logs, policy documentation, regulatory updates |
| HR | `hr/` | Provider credentialing files, staff onboarding docs, license renewal trackers, HR records |
| Marketing | `marketing/` | Google Business profile notes, review management, referral network contacts, patient education content |
| Admin | `admin/` | Front desk workflows, form templates, fax/mail logs, vendor contracts, administrative notes |
