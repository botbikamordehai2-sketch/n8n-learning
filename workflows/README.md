# workflows

Exported n8n JSON for study. No credential blocks.

| File | What |
| --- | --- |
| `store-contact-info-and-email-response.json` | Form → Sheets appendOrUpdate → Gmail send |
| `n8n-nodes-showcase.json` | Catalog of trigger / action / core / utility / AI nodes |

Rules:

- `active` is false.
- Replace `REPLACE_WITH_YOUR_SHEET_ID` before running the contact workflow.
- Bind Gmail / Sheets OAuth in the editor. Do not commit secrets.
- Showcase node labeled Split Out is type `splitInBatches` in the export — not the same as Split Out.
