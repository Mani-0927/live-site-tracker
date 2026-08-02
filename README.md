# live-site-tracker

An automated web monitoring system that tracks specific data (price, stock status, text, etc.) on any website, detects changes, and sends real-time alerts — no manual checking required.

## 🚀 Features

- **Automated Scraping** — Checks configured URLs every 3 minutes
- **Smart Change Detection** — Only alerts on real changes; no-change data is silently logged
- **AI-Powered Summaries** — Google Gemini AI generates a short summary and sentiment (positive/negative/neutral) for every change
- **Telegram Alerts** — Instant Telegram notification the moment a change is detected
- **Error Handling** — Automatic Slack alert if the scraper fails
- **Live Dashboard** — Custom frontend that displays the latest data in real time
- **Weekly Email Reports** — Summary email via Gmail every Monday
- **History Tracking** — Uses Google Sheets as a backend database to maintain a full change history

## 🛠️ Tech Stack

- **Automation Engine:** n8n (workflow orchestration)
- **AI:** Google Gemini API (change summarization)
- **Database:** Google Sheets API
- **Notifications:** Telegram Bot API, Slack API, Gmail API
- **Frontend:** HTML, CSS, JavaScript

## ⚙️ How It Works

1. **Scheduled Trigger** — A scraper workflow runs every 3 minutes
2. **Config-Driven** — Reads URLs and tracking rules from a Google Sheet
3. **Extract & Compare** — Pulls the value from the page and compares it with the previous value
4. **AI Summary** — If a change is detected, Gemini AI generates a short summary
5. **Alert + Log** — Sends a Telegram alert and updates the Data/History sheet
6. **Error Recovery** — A separate workflow sends a Slack alert on any failure
7. **Dashboard API** — The frontend fetches live data via a webhook workflow

## 📁 Project Structure

├── index.html     # Live dashboard frontend
├── WF1-error-handler.json
├── WF2-main-scraper.json
├── WF3-frontend-webhook.json
└── WF4-weekly-report.json

## 🔗 Live Demo

view live dashboard - https://live-site-tracker.onrender.com

<img width="1908" height="969" alt="image" src="https://github.com/user-attachments/assets/9fc0f33c-69ba-440d-9c06-49f3e1e7732b" />

<img width="839" height="772" alt="image" src="https://github.com/user-attachments/assets/827374e1-a0ff-4ab0-b9ac-a0bae5e444d5" />

## 📌 Note

The workflow JSON files are exported from n8n and included for reference. The live automation runs on a privately hosted n8n instance.

---

Built as a learning project to explore workflow automation, API integrations, and AI-assisted data processing.
