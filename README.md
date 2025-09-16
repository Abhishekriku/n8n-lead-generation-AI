# Lead Generation AI Agent (Enrich + Score + Push to CRM)

## Problem
Leads arrive unstructured and get slow follow‑ups.

## Solution (n8n)
- Webhook/CSV Import (lead intake)
- HTTP Request (company/person enrich via API or search)
- OpenAI (score intent & priority)
- CRM (HubSpot/Airtable) create/update
- Slack summary notification

## Result
- Faster response times and fewer manual steps.
- Replace with real or demo metrics (e.g., first response < 2 min, 70% auto‑resolved).

## Stack
n8n, OpenAI, HubSpot/Airtable, Slack

## How to Run (Demo)
1. Import `workflow.json` into n8n (this export is sanitized; set your own credentials).
2. Create the required credentials in n8n (WhatsApp/Telegram/OpenAI/etc.).
3. Create a Google Sheet / Notion DB / Airtable base as needed.
4. Update node IDs/URLs in the workflow to match your resources.
5. Trigger the entry node (Cron/Webhook/Gmail) with sample data from `/sample-data`.

## Repo Structure
```
/
├─ README.md
├─ workflow.json            # sanitized; no secrets
├─ /screenshots             # add 2–4 PNGs (flow overview & success logs)
├─ /sample-data             # example payloads (JSON/CSV)
└─ LICENSE                  # MIT license
```

## Screenshots
![flow](screenshots/flow-overview.png)

## Notes on Credentials & Safety
- This repo does **not** include secrets. Configure credentials inside n8n.
- Replace any test tokens/IDs with your own before running.
