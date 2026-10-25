# Patient Inbox Assistant

## Problem
Clinic staff spend hours each day reading patient emails, copying details into sheets, and writing replies. Urgent cases can get buried in the inbox.

## Solution
1. **Gmail Trigger** watches for new patient emails.
2. An **LLM with a Structured Output Parser** extracts the patient's name, phone, doctor, preferred time, symptoms, and urgency (high, normal, or low).
3. Every request is saved to a **Patient Requests** sheet.
4. **High urgency:** staff get an instant 🚨 alert email.
5. **Normal or low urgency:** the AI drafts a reply, staff approve it in Gmail, and then it is sent.
6. Each run is logged to a **Run Log** (items processed, errors, and minutes saved).

## Tools
n8n, Gmail, Google Sheets, OpenRouter LLM, Structured Output Parser, Send and Wait (approval).

## ROI (estimate)
40 emails a day × 5 minutes each × 22 working days comes to about **73 staff hours saved per month** (about ₹22,000 at ₹300 an hour).

## What I learned
- Preventing feedback loops in the Gmail filter, since the alert email was retriggering the workflow.
- Making LLM output reliable with strict prompts and structured parsing.
- Human-in-the-loop approval before any patient-facing message is sent.

## Screenshots
![Workflow](patient-inbox-assistant%201.png)
![Run](patient-inbox-assistant%202.png)
