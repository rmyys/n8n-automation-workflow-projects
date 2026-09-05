# n8n Automation & Workflow Projects

A central workspace for my n8n workflows, automation experiments, and custom code snippets.

## 📁 Repository Structure
Each subfolder contains a specific project:
* **`workflow.json`** - Sanitized n8n workflow export (ready to import).
* **`scripts/`** - Custom JavaScript or Python code snippets used inside Code nodes.
* **`README.md`** - Quick overview, trigger setup, and required API credentials.

## 🚀 How to Import a Workflow
1. Navigate to any project folder and open `workflow.json`.
2. Copy the raw JSON content or download the file.
3. In your n8n instance, click **Workflows** -> **Import from File / URL** (or paste directly onto the canvas).
4. Add your own API credentials to the corresponding nodes.
