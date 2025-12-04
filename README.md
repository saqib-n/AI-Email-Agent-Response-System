# 📧 AI Agentic Email Response System

![n8n](https://img.shields.io/badge/Workflow-n8n-FF6584?style=for-the-badge&logo=n8n&logoColor=white)
![Gemini](https://img.shields.io/badge/AI_Model-Google_Gemini-8E75B2?style=for-the-badge&logo=google-gemini&logoColor=white)
![Gmail](https://img.shields.io/badge/Integration-Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white)
![Slack](https://img.shields.io/badge/Alerts-Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white)

### 🚀 Overview
This repository contains an advanced **n8n workflow** designed to handle email inquiries using **Agentic AI**. 

This is not a simple "Out of Office" auto-responder. It uses a **Multi-Agent Architecture** to read the email context, draft a relevant reply, and—most importantly—**review its own work** for quality before hitting send.

---

### 🧠 System Architecture

The workflow is divided into three logical branches to ensure accuracy and safety:

#### 🟩 1. The Writer Agent (Green Zone)
*   **Role:** Context Understanding & Drafting.
*   **Logic:** Uses `Google Gemini Chat Model` with `Simple Memory`. It reads the incoming email to understand the user's question or issue and generates a professional, context-aware draft response.

#### 🟦 2. The QA Agent (Blue Zone)
*   **Role:** Quality Assurance (The Supervisor).
*   **Logic:** Before the email is sent, a second "Reviewer" agent analyzes the draft produced by the Writer Agent.
    *   It checks for: Tone, Accuracy, and Professionalism.
    *   **Action:** Only drafts that pass this strict quality check are sent via the `Reply to a message` node.

#### 🟥 3. The Sentiment Analyst (Red Zone)
*   **Role:** Risk Management & Alerts.
*   **Logic:** A parallel process analyzes the incoming email's emotional tone (Positive, Neutral, Negative).
    *   **Action:** If the email is **Negative** or urgent, it bypasses the standard flow and triggers a **Slack Alert** (`Alert WX`), notifying the human team to intervene immediately.

---

### 🛠️ Prerequisites

1.  **n8n Instance:** Self-hosted or Cloud version.
2.  **Google Cloud Console:** Enable Gemini API.
3.  **Gmail API:** Credentials for the Trigger and Reply nodes.
4.  **Slack API:** Webhook URL for team alerts.

---

### 📥 Installation

1.  Clone this repository.
2.  Open your **n8n** dashboard.
3.  Click **"Import Workflow"** and select the `.json` file from this repo.
4.  Configure your credentials (Gmail, Gemini, Slack).
5.  **Optional:** Customize the "System Prompt" in the Writer Agent node to match your company's tone of voice.

---

### 🔮 Use Cases

*   **Customer Support:** Instantly answer FAQs with high-quality, AI-generated responses.
*   **Lead Response:** Engage new leads immediately 24/7 without waiting for a human.
*   **Inbox Triage:** Automatically flag angry customers in Slack while handling routine queries automatically.

---

<div align="center">
  <p>Built with ❤️ by <a href="https://www.wolfxense.agency/">WolfXense AI</a></p>
  <p><i>Your AI Transformation Partner</i></p>
</div>
