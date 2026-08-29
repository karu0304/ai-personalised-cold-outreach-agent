# AI-Powered Personalised Cold Outreach Agent

An AI-powered outreach automation built with n8n that researches leads, qualifies prospects, generates personalised cold emails, routes them through human approval, sends the appropriate email, and logs the outcome in Google Sheets.

## Overview

Cold outreach often requires repetitive manual work across lead research, qualification, personalization, email writing, sending, and tracking.

This workflow automates that process while keeping a human approval step before outreach is sent.

## Workflow

Lead Input
↓
Company Research
↓
AI Lead Qualification
↓
AI Cold Email Generation
↓
Human Approval Gate
↓
Approval Check
├── Approved → Send Approved Email
└── Review → Send Review Email
↓
Google Sheets Logging

## What It Does

- 🔎 Researches a company's website and analyzes the available information
- 🤖 Uses AI to qualify leads and assign a lead score and priority
- ✍️ Generates personalized cold outreach emails
- 👤 Includes a human approval gate before outreach
- 📧 Sends different emails based on approval status
- 📊 Logs lead, research, email, approval, and status information to Google Sheets
- 🔄 Handles both approved and rejected/review paths

## Tech Stack

- n8n — workflow orchestration and automation
- Google Gemini — AI-powered lead qualification and email generation
- Gmail — outbound email delivery
- Google Sheets — lead and outreach tracking
- HTTP/Web Requests — company website research
- GitHub — workflow versioning and documentation

## Workflow Architecture

Lead Input
    ↓
Company Research
    ↓
AI Lead Qualification
    ↓
AI Cold Email Generation
    ↓
Human Approval Gate
    ↓
Approval Check
   ↙           ↘
Approved      Review
   ↓            ↓
Send Approved  Send Review
Email          Email
   ↘            ↙
      Google Sheets
          Logging

## Key Features

### 🔎 Automated Company Research
Fetches company website information before the AI evaluates the lead.

### 🧠 AI Lead Qualification
Analyzes the available research and produces a lead score, priority, potential fit, and reasoning.

### ✍️ Personalized Email Generation
Uses the lead information and AI research to generate a tailored cold outreach email.

### 👤 Human-in-the-Loop Approval
AI-generated outreach passes through an approval gate before the email is sent.

### 📧 Conditional Email Delivery
Approved leads receive the generated outreach email, while rejected leads are routed through a review notification.

### 📊 Automated Outreach Logging
Both approved and rejected outcomes are recorded in Google Sheets along with lead and email information.

### 🛡️ Controlled AI Execution
The workflow avoids automatically sending AI-generated outreach without an explicit approval decision.

## Key Features

- Automated company research
- AI-powered lead qualification
- AI-generated personalised cold emails
- Human-in-the-loop approval
- Automated Gmail delivery
- Approval and review paths
- Google Sheets activity logging
- Timestamped outreach records

## Setup

### Requirements

- n8n instance
- Google Gemini credentials
- Gmail credentials
- Google Sheets credentials
- A Google Sheet for outreach logging

### Installation

1. Download the workflow JSON from the `workflow/` directory.
2. Import the JSON workflow into n8n.
3. Reconnect your Google Gemini credentials.
4. Reconnect your Gmail credentials.
5. Reconnect your Google Sheets credentials.
6. Configure the lead input fields.
7. Configure the Google Sheet used for outreach logging.
8. Test the workflow with a sample lead.
9. Verify both the approved and review paths.
10. Activate the workflow when ready.

> The workflow is provided as a sanitized portfolio example. Credentials and private account information are not included.
## Human-in-the-Loop Approval

The system does not automatically send AI-generated outreach.

After the email is generated, it passes through an approval gate.

If approved, the workflow sends the approved email.

If not approved, the workflow sends a review email instead.

Both outcomes are recorded in Google Sheets.

## Data Logged

The workflow records:

- Company
- Website
- Contact name
- Job title
- Contact email
- Research summary
- Email subject
- Email body
- Approval status
- Email status
- Timestamp

## Tech Stack

- n8n
- Google Gemini
- Gmail
- Google Sheets

## Architecture

The workflow separates research, reasoning, generation, human approval, communication, and logging into distinct automation stages.

This makes the system easier to understand, control, and extend.

## Portfolio Note

This project demonstrates practical AI automation for a sales/outreach workflow, with an emphasis on controlled AI execution and reliable business-process automation.

## Workflow File

The complete n8n workflow is included in this repository as a JSON export.

## Workflow Screenshots

### Workflow Overview
![Workflow Overview](workflow/screenshots/workflow-overview.png)

### AI Lead Qualification
![AI Lead Qualification](workflow/screenshots/ai-qualification.png)

### Approved Outreach & Sheet Logging
![Approved Outreach Result](workflow/screenshots/approved-outreach-result.png)
