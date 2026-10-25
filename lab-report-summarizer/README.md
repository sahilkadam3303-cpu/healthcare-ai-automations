# Lab Report Summarizer

## Problem
Doctors must review every lab report, and patients often don't understand medical values. Critical results need fast attention.

## Solution
1. **Gmail Trigger** downloads lab report PDFs from incoming emails.
2. **Extract from File** reads the PDF text.
3. An **LLM with a Structured Output Parser** extracts the patient, test, abnormal values, and severity (normal, borderline, or critical).
4. A **Switch** node routes each report by severity:
   - **Critical:** the doctor gets an instant 🚨 alert.
   - **Normal or borderline:** the AI writes a plain-language summary for the patient.
5. The doctor approves the summary in Gmail before the patient receives it.
6. Each report is logged to a **Lab Log** sheet.

## Tools
n8n, Gmail, Extract from File (PDF), Google Sheets, OpenRouter LLM, Switch, Send and Wait (approval).

## ROI (estimate)
50 reports a day × 4 minutes of summary writing saved comes to about **73 doctor and staff hours saved per month**, and critical results are flagged within minutes.

## Safety
The AI never diagnoses, and a doctor approves every message before it reaches a patient.

## Screenshots
![1](lab-report-summarizer%201.png)
![2](lab-report-summarizer%202.png)
![3](lab-report-summarizer%203.png)
