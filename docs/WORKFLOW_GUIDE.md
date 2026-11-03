# Email Signature Automation - Workflow Guide

## Architecture
```
Google Sheets --> n8n Workflow --> HTML Template --> Gmail Send
  (contacts)       (trigger)      (Google Drive)    (signature)
```

## Components
| Component | Role |
|-----------|------|
| Google Sheets | Employee data source |
| Google Drive | HTML signature templates |
| n8n | Workflow orchestration |
| Gmail | Automated email delivery |

## Setup Steps
1. Import n8n workflow JSON
2. Configure Google API credentials
3. Create Sheets with employee data
4. Upload HTML templates to Drive
5. Activate workflow trigger

## Customization
| Field | Description |
|-------|-------------|
| name | Employee name |
| title | Job title |
| phone | Phone number |
| logo | Company logo URL |