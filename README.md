# 🌤️ AI-Powered Weather Assistant (n8n Workflow)

This project is an **AI-driven weather assistant** built with **n8n**.  
It listens to chat messages, processes them using an **AI Agent**, fetches live weather information, and delivers a **personalized weather report** directly to your email inbox.  

---

## ✨ Features
- 🤖 **AI Agent** – Powered by Groq Chat Model for smart responses.  
- 🧠 **Context Memory** – Remembers recent chat context with a simple memory buffer.  
- 🌍 **Live Weather Data** – Fetches real-time weather details from [Open-Meteo API](https://open-meteo.com/).  
- 📩 **Email Reports** – Sends weather updates via Gmail with an AI-generated subject & message.  
- 🔗 **Workflow Integration** – Supports calling other n8n workflows as tools for expansion.  

---

## ⚙️ Workflow Overview
1. **Trigger** → Starts when a chat message is received.  
2. **Groq Chat Model** → Processes the query and interacts with the AI Agent.  
3. **Weather API Tool** → Fetches weather details (temperature, rainfall, daylight, sunshine, etc.).  
4. **Memory Buffer** → Maintains context for better chat experience.  
5. **Email Tool** → Sends a personalized weather report to your email.  
6. **Workflow Caller** → Connects with other workflows if needed.  

---

## 📌 Tech Stack
- **[n8n](https://n8n.io/)** – Workflow automation platform  
- **Groq AI** – Fast and efficient chat model  
- **Open-Meteo API** – Free weather API  
- **Gmail Tool** – For sending reports  

---

## 🚀 Getting Started

### 1. Import the Workflow
Download [`schedule.json`](./schedule.json) and import it into your **n8n instance**.

### 2. Configure Credentials
- **Groq API Key** → Add under `Groq account` credentials.  
- **Gmail OAuth2** → Authenticate your Gmail account in n8n.  

### 3. Update Email Receiver
By default, the workflow sends emails to:  
sravanthim674@gmail.com
Change this in the **send_email** node if needed.

### 4. Activate Workflow
Turn on the workflow in n8n, send a chat message, and you’ll receive a **weather report** straight in your inbox.  

---

## 🔮 Future Improvements
- 🌆 Add **multi-city weather tracking**  
- 🎙️ Support **voice input/output**  
- 📅 Create **daily scheduled weather briefings**  
- 💬 Integrate with **Slack/Telegram notifications**  

---

## 📜 License
This project is open-source and available under the **MIT License**.  


## 📸 Workflow Diagram
```mermaid
graph TD;
    A[💬 Chat Trigger] --> B[🤖 AI Agent]
    B --> C[🌍 Get Weather API]
    B --> D[📩 Send Email]
    B --> E[🔗 Call n8n Workflow]
    F[🧠 Memory Buffer] --> B
    G[Groq Chat Model] --> B
