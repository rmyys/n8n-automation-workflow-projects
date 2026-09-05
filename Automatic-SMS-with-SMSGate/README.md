# 📲 Automated AI SMS Sender via SMSGate & n8n

An automated batch SMS dispatch pipeline built in n8n. It reads pending contacts from a Google Sheet, generates a personalized message using an AI model node, dispatches the SMS via a local Android gateway (SMSGate), updates the row status in Google Sheets, and applies rate-limit delays to prevent SIM flagging.

## 🛠 Prerequisites & Hardware
* **n8n Instance:** Self-hosted or Cloud.
* **Android Device:** Running [SMSGate](https://sms-gate.app/) on the same local network as your n8n server.
* **Google Sheets API:** Configured credentials with read/write access.
* **LLM Provider:** OpenAI, Anthropic, or local LLM credentials attached in n8n.

## 🔄 Workflow Logic
1. **Manual Trigger:** Initiates the execution batch.
2. **Google Sheets (Read):** Queries rows marked with `Status = Pending` (or in my case in which status was just blank).
3. **Loop Over Items:** Processes contacts individually (Batch Size: 1).
4. **Message a Model:** Generates custom SMS copy based on recipient row data.
5. **HTTP Request (SMSGate):** Sends a `POST` request to `http://<ANDROID_IP>:8080/message`.
6. **Google Sheets (Update):** Sets status to `Sent` for the processed row ID.
7. **Wait Node:** Applies a randomized delay before looping to the next item.

## 🚀 How to Import
1. Download `workflow.json`.
2. Open n8n -> **Workflows** -> **Import from File**.
3. Re-link your Google Sheets, LLM model credentials, and local SMSGate IP address.
