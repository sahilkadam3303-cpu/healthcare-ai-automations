# Healthcare AI Automations

Three production-style n8n workflows that automate everyday clinic work with LLMs, Gmail and Google Sheets.

| Project | What it does | Key skills |
|---|---|---|
| [Patient Inbox Assistant](patient-inbox-assistant/) | Reads patient emails, extracts details, alerts staff on urgent cases, drafts replies for approval | Structured output, IF routing, human-in-the-loop |
| [No-Show Reducer](no-show-reducer/) | Sends personalized reminders, reads YES/NO replies, updates status, sends rebook emails | Filtering, regex in Code node, sheet updates |
| [Lab Report Summarizer](lab-report-summarizer/) | Reads lab report PDFs, flags abnormal values, gets doctor approval, sends a plain-language summary | PDF extraction, Switch routing, approvals |

**Stack:** n8n, OpenRouter LLMs, Gmail, Google Sheets, JavaScript.
**Reliability:** retry on fail, a global Error Alert workflow, and Run Logs for every workflow.

All patient data is fake and for demo use only.
