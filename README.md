# ai-email-automation-n8n

AI Email Automation Assistant

An AI-powered customer support email automation workflow built with n8n, Google Sheets, Google Gemini, and Gmail.

The workflow automatically detects new customer inquiries, generates a professional AI response, sends the response by email, and records the result back in Google Sheets.

📌 Project Overview

This project demonstrates how an AI-powered workflow can automate a common customer support process from end to end.

Workflow

Customer Inquiry
       ↓
Google Sheets
       ↓
New Row Trigger
       ↓
Data Processing
       ↓
Google Gemini
       ↓
Generate AI Response
       ↓
Gmail
       ↓
Send Email
       ↓
Update Google Sheets

⚙️ How It Works

1. Google Sheets Trigger

The workflow monitors a Google Sheet for newly added customer inquiries.

Example input:

Name| Email| Message| Status
Rahul| customer@example.com| I want to know more about your service.| New

The workflow starts automatically when a new row is added.

2. Edit Fields

The incoming data is mapped into three fields:

customer_name
customer_email
customer_message

This creates a clean data structure for the AI and email steps.

3. AI Response Generation

Google Gemini receives the customer's name and message.

The AI is instructed to:

- Generate a short and professional response
- Be friendly and polite
- Avoid inventing information
- Avoid generating a subject line
- Ask the support team to follow up when required information is unavailable
- Sign the response as "Customer Support Team"

4. Gmail

The generated response is automatically sent to the customer's email address.

The email uses the subject:

Thank you for your inquiry

The AI-generated response is used as the email body.

5. Update Google Sheets

After the email is sent, the workflow updates the corresponding Google Sheets record.

The following information is stored:

Status: Sent
AI Reply: Generated response
Email: Customer email

This provides a simple record of the automation result.

---

🧩 Technologies Used

- n8n — Workflow automation and orchestration
- Google Sheets — Customer inquiry input and status tracking
- Google Gemini — AI-powered response generation
- Gmail — Automated email delivery
- OAuth 2.0 — Service authentication
- JSON — Workflow configuration

---

📁 Project Structure

ai-email-automation-n8n/
│
├── README.md
│
├── workflow/
│   └── ai-email-automation.json
│
└── screenshots/
    ├── workflow.png
    ├── google-sheet.png
    ├── ai-response.png
    └── gmail-result.png

---

📸 Screenshots

Complete Workflow

"n8n Workflow" (screenshots/workflow.png)

Google Sheets

"Google Sheets" (screenshots/google-sheet.png)

AI Generated Response

"AI Response" (screenshots/ai-response.png)

Gmail Output

"Gmail Result" (screenshots/gmail-result.png)

---

📝 Example

Customer Input

Name: Rahul

Email: customer@example.com

Message:
I would like to know more about your service.

AI Generated Response

Hi Rahul,

Thank you for reaching out and for your interest in our service.

A member of our team will follow up with you shortly with more information.

Best regards,

Customer Support Team

Final Sheet Status

Status: Sent

AI Reply:
[Generated email response]

---

🔐 Security

No API keys, passwords, access tokens, or OAuth secrets are included in this repository.

The workflow JSON uses placeholder values for credentials and the Google Sheet ID.

Before running the workflow, users must configure their own:

- Google Sheets credentials
- Google Gemini credentials
- Gmail credentials
- Google Sheet

Never commit real API keys, passwords, OAuth secrets, access tokens, or customer data to GitHub.

---

🚀 How to Use

Prerequisites

You need:

- An n8n instance
- A Google account
- A Google Sheet
- Google Gemini API access
- Gmail access

Setup

1. Download the workflow JSON from this repository.
2. Import the JSON into n8n.
3. Create/connect your Google Sheets credential.
4. Create/connect your Google Gemini credential.
5. Create/connect your Gmail credential.
6. Replace the placeholder Google Sheet ID with your own sheet.
7. Configure the required Google Sheet columns.
8. Activate the workflow.
9. Add a test customer inquiry to the Google Sheet.
10. Verify that the AI response is generated and sent by Gmail.
11. Verify that the sheet is updated with the "Sent" status and AI response.

Required Google Sheet Columns

Name
Email
Message
Status
AI Reply

---

💡 Key Concepts Demonstrated

This project demonstrates practical experience with:

- Event-driven automation
- Workflow orchestration
- AI/LLM integration
- Prompt engineering
- Google Sheets integration
- Gmail integration
- OAuth authentication
- Dynamic data mapping
- n8n expressions
- Automated email generation
- Automated email delivery
- Workflow status tracking
- JSON-based workflow configuration

---

🔄 Future Improvements

The current implementation is a working prototype. It can be extended into a more production-oriented customer support system.

Potential improvements include:

- Error handling and retry mechanisms
- Dedicated error logging
- Monitoring and alerting
- Duplicate inquiry detection
- Email validation
- Human approval before sending sensitive responses
- Conversation history
- Database integration
- CRM integration
- Webhook-based customer inquiry submission
- Automatic classification of customer requests
- Priority-based routing
- Escalation to human support
- Response-time monitoring

Possible Production Architecture

Website / Customer Form
          ↓
       Webhook
          ↓
         n8n
          ↓
   Request Classification
          ↓
      AI Processing
          ↓
    ┌─────┴─────┐
    ↓           ↓
Automated    Human Review
Response        ↓
    ↓           ↓
    └─────┬─────┘
          ↓
        Gmail
          ↓
      CRM / DB
          ↓
   Logging & Monitoring

---

📊 Project Status

Status: Completed Prototype

The current workflow successfully demonstrates the complete automation cycle:

Input → AI Processing → Email → Status Update

Future versions can extend this prototype with production-grade reliability, monitoring, error handling, and integrations.

---

👨‍💻 Author

Abhishek Kumar

This project was created to demonstrate practical experience with AI automation, n8n workflow orchestration, API integrations, and AI-powered customer support automation.