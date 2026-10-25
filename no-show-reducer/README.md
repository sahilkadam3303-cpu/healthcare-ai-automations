# Appointment No-Show Reducer

## Problem
Missed appointments waste doctor time and lose clinic revenue. Calling each patient to remind them is slow.

## Solution
Two n8n workflows:

**1. Send**
1. Reads pending appointments from Google Sheets.
2. Filters to tomorrow's appointments.
3. Uses an LLM to write each patient a personal reminder.
4. Emails it, asking the patient to reply YES or NO.

**2. Replies**
1. A Gmail Trigger catches each patient's reply.
2. A Code node pulls the patient ID from the subject and reads the YES or NO answer.
3. Updates the appointment status in the sheet to confirmed or cancelled.
4. Sends patients who cancel an email asking them to rebook.
5. Logs every reply to a NoShow Log.

## Tools
n8n, Gmail, Google Sheets, OpenRouter LLM, JavaScript (regex).

## ROI (estimate)
- 30 reminder calls a day × 2 minutes each comes to about **22 staff hours saved per month**.
- If no-shows drop from 15% to 8%, the clinic sees about **2 more patients a day**.

## What I learned
- Pulling structured data out of email subjects with regex.
- Handling quoted reply text and email threads correctly.
- Updating rows by matching a key column.

## Screenshots
![Send](No-Show%20Reducer%20-%20Send.png)
![Replies](No-Show%20Reducer%20-%20Replies.png)
