# 📧 Onebox Email Aggregator (ReachInbox Backend Task)

A **full-stack email aggregator system** built using **TypeScript (Node.js)** and **ReactJS**, inspired by **ReachInbox**.  
This project syncs multiple IMAP email accounts in real-time, makes them searchable using **Elasticsearch**, and integrates **AI-based email categorization** and **Slack/Webhook notifications**.  
The ultimate goal is to create a seamless, intelligent, and searchable email management platform.

---

## 🚀 Features Implemented

### 1. Real-Time Email Synchronization
- Supports syncing **multiple IMAP accounts** (minimum 2).
- Fetches the **last 30 days** of emails.
- Uses **persistent IMAP IDLE connections** for real-time updates — *no cron jobs used*.
- Handles multiple folders (Inbox, Sent, Spam, etc.) per account.

---

### 2. Searchable Storage using Elasticsearch
- Stores emails in a **locally hosted Elasticsearch instance (via Docker)**.
- Each email is **indexed and searchable** by:
  - Subject
  - Sender
  - Body content
  - Folder
  - Account
- Supports **filtering** and **full-text search** queries.

---

### 3. AI-Based Email Categorization
- Emails are automatically categorized into the following classes:
  - ✅ **Interested**
  - 📅 **Meeting Booked**
  - ❌ **Not Interested**
  - 🚫 **Spam**
  - 💤 **Out of Office**
- AI model (LLM / OpenAI API) analyzes the email subject and body for classification.

---

### 4. Slack & Webhook Integrations
- **Slack Notification:** Sends a real-time Slack message when a new “Interested” email is received.
- **Webhook Trigger:** Sends an external POST request to [webhook.site](https://webhook.site) when an email is marked as “Interested” for automation workflows.

---

### 5. Frontend Interface (ReactJS)
- Built using **ReactJS + Axios + TailwindCSS**.
- Displays emails with:
  - Folder & Account filters
  - AI-based categorization labels
  - Search powered by Elasticsearch
- Simple, clean, and responsive interface.

---

### 6. AI-Powered Suggested Replies (Bonus)
> 💎 Completing this feature qualifies for a **direct final interview invitation**.

- Stores **outreach agenda & product details** in a **vector database**.
- Implements **RAG (Retrieval-Augmented Generation)** using an LLM (e.g., OpenAI GPT model).
- Generates **smart auto-replies** based on email context.

#### Example:
**Training Data:**  
> “I am applying for a job position. If the lead is interested, share the meeting booking link: [https://cal.com/example](https://cal.com/example)”

**Incoming Email:**  
> “Hi, your resume has been shortlisted. When will be a good time for you to attend the technical interview?”

**AI Suggested Reply:**  
> “Thank you for shortlisting my profile! I’m available for a technical interview. You can book a slot here: [https://cal.com/example](https://cal.com/example)”

---

## 🧩 Tech Stack

### **Backend**
- TypeScript (Node.js)
- Express.js
- IMAP (email fetching)
- Mailparser
- Elasticsearch (for search)
- Docker
- Slack API
- Webhooks
- OpenAI API (for AI classification)

### **Frontend**
- ReactJS
- Axios (for backend API calls)
- FontAwesome (for icons)
- TailwindCSS (for UI styling)

---
