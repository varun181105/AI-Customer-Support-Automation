# 📧 AI Email Automation System

An AI-powered email automation system built with **n8n** and **OpenAI** that automatically classifies incoming emails, sends intelligent automated replies, and logs all interactions to Google Sheets — fully hands-free.

---

## 🚀 What This Workflow Does

1. **Triggers** when a new email arrives via Gmail
2. **Filters** emails based on subject keywords
3. **Classifies** the email using OpenAI (order / inquiry / support)
4. **Routes** the email using a Switch node based on category
5. **Sends** an automated, context-aware reply via Gmail
6. **Logs** all email activity to Google Sheets for tracking

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **n8n** | Workflow automation engine |
| **OpenAI API** | Email classification & reply generation |
| **Gmail** | Trigger on new emails + send replies |
| **Google Sheets** | Log all email interactions |

---

## 📂 Workflow Structure

```
Gmail Trigger
  └─► Filter (subject keyword check)
        └─► OpenAI AI Classification
              └─► Switch (order / inquiry / support)
                    ├─► Order     → Send Automated Reply
                    ├─► Inquiry   → Send Automated Reply
                    └─► Support   → Send Automated Reply
                                        └─► Log Email Data in Google Sheets
```

---

## ⚙️ Setup Instructions

### Prerequisites
- [n8n](https://n8n.io/) account (cloud or self-hosted)
- OpenAI API Key
- Google account (Gmail + Google Sheets)

### Steps

1. **Clone this repository**
   ```bash
   git clone https://github.com/varun181105/AI-Email-Automation-System.git
   ```

2. **Import the workflow into n8n**
   - Open your n8n instance
   - Go to **Workflows → Import from File**
   - Upload the `.json` file from this repo

3. **Configure credentials in n8n**
   - **OpenAI**: Add your OpenAI API key
   - **Gmail**: Connect your Google account via OAuth2
   - **Google Sheets**: Connect your Google account via OAuth2

4. **Set up Google Sheets**
   - Create a spreadsheet with a sheet named `Email Logs`
   - Copy the Sheet ID from the URL and update it in the Google Sheets node

5. **Activate the Workflow**
   - Click **Activate** in the top right of n8n
   - The workflow will now run automatically on every new email

---

## 📊 Google Sheets Log Structure

| Column | Description |
|--------|-------------|
| Timestamp | Date & time email was received |
| Sender | Email address of the sender |
| Subject | Subject line of the email |
| Category | AI-classified category |
| Message | Original email body |

---

## 🧠 AI Classification Categories

| Category | Description |
|----------|-------------|
| `order` | Questions or issues related to orders |
| `inquiry` | General customer inquiries |
| `support` | Technical or account support requests |

---

## 💡 Use Cases

- **Customer support automation** — handle emails 24/7 without manual effort
- **Small business email handling** — auto-reply to common questions instantly
- **Lead inquiry response** — respond to leads the moment they reach out
- **AI productivity tools** — reduce inbox overload with smart automation

---

## 👤 Author

**Varun Kumar**
- GitHub: [@varun181105](https://github.com/varun181105)
- LinkedIn: [Varun Kumar](https://www.linkedin.com/in/varun-kumar-1706743b0/)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

⭐ **If you found this useful, please give it a star!**
