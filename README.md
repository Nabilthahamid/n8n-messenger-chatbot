# 🤖 AI-Powered Facebook Messenger Chatbot with n8n

An intelligent Facebook Messenger chatbot built using **n8n**, **Google Gemini AI**, **Google Sheets**, and **Google Docs** integration.

This workflow receives messages from Facebook Messenger, processes them using Google's Gemini AI model, maintains conversation memory, accesses Google Docs and Google Sheets as knowledge sources, and sends AI-generated responses back to users.

---

## 🚀 Features

- ✅ Facebook Messenger Webhook Integration
- ✅ Facebook Webhook Verification
- ✅ Google Gemini AI Agent
- ✅ Conversation Memory Support
- ✅ Google Docs Knowledge Retrieval
- ✅ Google Sheets Data Retrieval
- ✅ Automatic AI Response Generation
- ✅ Real-time Message Processing
- ✅ No-Code/Low-Code Automation using n8n

---

## 🏗️ Workflow Architecture

```text
Facebook Messenger
        │
        ▼
    Webhook
        │
        ▼
Webhook Verification
        │
        ▼
     AI Agent
        │
 ┌──────┼─────────┐
 │      │         │
 ▼      ▼         ▼
Gemini  Memory  Google Tools
Model           (Docs/Sheets)
 │
 ▼
AI Response
 │
 ▼
Facebook Graph API
 │
 ▼
Messenger User
```

---

## 📋 Workflow Components

### 1. Webhook Node
Receives incoming Facebook Messenger events and messages.

### 2. IF Node
Handles Facebook webhook verification by checking:

- `hub.mode = subscribe`
- `hub.verify_token = Our_shop`

### 3. Respond to Webhook
Returns the Facebook challenge token during webhook verification.

### 4. AI Agent
Processes user queries using Google Gemini AI.

System Prompt:

```text
You are a helpful AI assistant
```

### 5. Google Gemini Chat Model
Provides Large Language Model capabilities for the AI Agent.

### 6. Simple Memory
Stores conversation history using Facebook Sender ID as session key.

### 7. Google Docs Tool
Allows the AI Agent to retrieve information from Google Docs.

### 8. Google Sheets Tool
Allows the AI Agent to retrieve data from Google Sheets.

### 9. HTTP Request Node
Sends generated AI responses back to Facebook Messenger using the Facebook Graph API.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|----------|
| n8n | Workflow Automation |
| Google Gemini | AI Processing |
| Facebook Messenger API | Messaging Platform |
| Google Sheets API | Structured Data Source |
| Google Docs API | Knowledge Base |
| HTTP Requests | API Communication |

---

## 📦 Requirements

- n8n Instance
- Facebook Developer Account
- Facebook Page
- Google Gemini API Key
- Google OAuth Credentials
- Google Sheets Access
- Google Docs Access

---

## ⚙️ Setup Guide

### Step 1: Import Workflow

1. Open n8n.
2. Click **Import Workflow**.
3. Upload the JSON workflow file.

### Step 2: Configure Credentials

Add:

- Google Gemini API
- Google Docs OAuth2
- Google Sheets OAuth2

### Step 3: Configure Facebook Webhook

Set:

```text
Webhook URL:
https://YOUR_N8N_DOMAIN/webhook/DailyGoods_messenger_bot

Verify Token:
Our_shop
```

### Step 4: Subscribe Messenger Events

Enable:

- messages
- messaging_postbacks

### Step 5: Activate Workflow

Turn on the workflow and test by sending a message to your Facebook Page.

---

## 💬 Example Usage

### User

```text
What is my grade?
```

### AI Agent

1. Reads data from Google Sheets.
2. Processes the request using Gemini.
3. Generates a response.

### Messenger Response

```text
Your current grade is A.
```

---

## 🔒 Security Notes

Before publishing:

- Remove Facebook Page Access Tokens.
- Remove Google Credential IDs.
- Store secrets using n8n Credentials Manager.
- Use environment variables whenever possible.

---

## 📁 Project Structure

```text
project/
│
├── workflow.json
├── README.md
└── assets/
    └── workflow-diagram.png
```

---

## 🎯 Future Improvements

- Multi-language support
- Product recommendation system
- Order tracking integration
- Customer support ticket creation
- Database integration
- Voice message support
- Image understanding with Gemini Vision

---

## 👨‍💻 Author

Developed using:

- n8n
- Google Gemini AI
- Facebook Messenger Platform

---

## 📄 License

This project is available under the MIT License.
