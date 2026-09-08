# 📥 Automated Lead Tracker & Slack Alert Pipeline

An event-driven automation workflow built in n8n that captures incoming webhooks, logs contact submissions into Google Sheets, and sends formatted notifications to a team Slack channel.

## ⚡ Workflow Features
* **Instant Lead Capture:** Listens for `POST` requests containing lead data (`name`, `email`, `service`).
* **Automated Data Logging:** Appends new lead entries directly into Google Sheets along with an automated ISO timestamp (`$now`).
* **Real-time Notifications:** Sends custom markdown-formatted alert messages directly to Slack via Webhook.

## 📊 Expected Payload Structure
Send a `POST` request to the webhook endpoint with the following JSON structure:

```
{
  "name": "Jane Doe",
  "email": "jane@example.com",
  "service": "Workflow Automation"
}

```
