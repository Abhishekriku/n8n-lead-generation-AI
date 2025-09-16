# Lead Generation AI Agent (n8n + OpenAI + Google Sheets)

## Problem

Sales teams spend hours manually qualifying leads, searching for enrichment data, and updating spreadsheets or CRMs. This slows down response times and leaves gaps in the sales pipeline.

## Solution (n8n)

This AI-powered Lead Generation Agent automates the process of capturing, enriching, and storing leads using conversational AI + Google Sheets.

Workflow Steps:

- Chat Trigger → Captures incoming user messages as potential leads.
- AI Agent (OpenAI) → Extracts and structures lead details (name, email, company, intent).
- HTTP Request Node → Performs live enrichment (e.g., company/domain lookup).
- Code Node → Cleans and formats the extracted lead data.
- Google Sheets Integration → Appends each qualified lead into a sheet for sales follow-up.

## Features

- Conversational lead intake via chat
- AI-powered entity extraction (name, email, company, intent)
- External data enrichment (via HTTP API calls)
- Automatic storage in Google Sheets (CRM-ready)
- Fully extendable to HubSpot, Airtable, or Salesforce

## Stack

* n8n – workflow automation
* OpenAI – natural language understanding
* Google Sheets – lead database
* HTTP APIs – data enrichment
* (Optional) Simple Memory – keeps short context across conversations

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
