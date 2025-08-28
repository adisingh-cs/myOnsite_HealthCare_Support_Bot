# n8n Customer Support Automation for myOnsite HealthCare

An **n8n workflow** that integrates Telegram, Google Sheets, Zep API, and OpenAI to handle customer support tickets automatically.  
Generates tickets, fetches user data, provides AI-driven responses, stores conversations, and maintains a knowledge base for future interactions.

---

## Features

- **Telegram Trigger:** Receive messages from users in real-time.  
- **Ticket Generation:** Automatically create unique ticket IDs for every interaction.  
- **User Verification:** Check if the user exists in the Zep API database.  
- **New User Registration:** Register new users in Zep automatically.  
- **AI-Powered Assistance:**  
  - **New Users:** Generates personalized responses using OpenAI GPT-4.1-nano.  
  - **Existing Users:** Analyzes past conversation history and spreadsheet records to provide informed responses.  
- **Memory Storage:**  
  - Logs conversation data in Zep for context-aware responses.  
  - Stores ticket data in Google Sheets for reporting and tracking.  
- **Multilingual Support:** Detects the user’s language but responds exclusively in English.  
- **Automated Response Delivery:** Sends AI-generated replies back to the user on Telegram.

---

## Workflow Overview

1. **Telegram Trigger:** Listens for new messages.  
2. **Fetch & Parse Users:** Checks if the user exists in Zep.  
3. **User Validation:** Determines if the user is new or existing.  
4. **Ticket Generation:** Generates a unique ticket ID.  
5. **AI Assistance:**  
   - New users: `New User Assistant` node.  
   - Existing users: `Existing User Assistant` node (using Google Sheets & Zep memory).  
6. **Memory Logging:** Updates Zep with conversation data.  
7. **Google Sheets Logging:** Appends ticket and response data.  
8. **Send Response:** Delivers AI-generated reply back to Telegram.

---

## Requirements

- n8n >= 2.x  
- Telegram Bot API credentials  
- Google Sheets OAuth2 credentials  
- Zep API credentials  
- OpenAI API key  

---

## Setup Instructions

1. Import the workflow JSON into n8n.  
2. Configure credentials for:
   - Telegram
   - Google Sheets
   - Zep API
   - OpenAI
3. Activate the workflow.  
4. Start sending messages to your Telegram bot. AI responses will be automatically generated, logged, and delivered.

