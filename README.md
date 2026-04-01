# 🔒 Phishing Analysis Automation Bot

> An intelligent, AI-powered phishing URL detection system built with **n8n**, **VirusTotal**, **URLScan.io**, and **GPT-4o-mini** — delivered instantly via **Telegram**.

---

## 📌 Overview

This project automates the detection and analysis of phishing URLs using a multi-source threat intelligence pipeline. Users simply send a suspicious URL to a Telegram bot, and within seconds receive a structured security assessment — powered by real threat feeds and an AI security analyst.

---

## 🏗️ Architecture & Workflow

```
User (Telegram)
      │
      ▼
[Telegram Trigger]
      │
      ▼
[Validate URL Input]
      │
   ┌──┴──────────────────────┐
   │                         │
   ▼                         ▼
[URLScan.io Analysis]   [VirusTotal Analysis]
   │                         │
   └──────────┬──────────────┘
              │
              ▼
        [Merge Results]
              │
              ▼
      [AI Security Analyst]
       (GPT-4o-mini via LangChain)
              │
              ▼
        [Format Report]
              │
              ▼
    [Send Results to Telegram]
```

> If the input is not a valid URL, the bot sends a help message guiding the user to provide a proper link.

---

## ✨ Key Features

- **Dual Threat Intelligence** — Simultaneously queries URLScan.io and VirusTotal for comprehensive coverage
- **AI-Powered Analysis** — GPT-4o-mini acts as a cybersecurity analyst, synthesizing raw scan data into actionable insights
- **Real-Time Delivery** — Results sent back to the user on Telegram in seconds
- **Input Validation** — Automatically detects and rejects non-URL inputs with a helpful message
- **Structured Reports** — Every report includes threat rating, findings, indicators of compromise, and recommendations

---

## 📊 Sample Output Report

```
🔒 PHISHING ANALYSIS REPORT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🔗 ANALYZED URL
`https://suspicious-site.example.com`

📅 SCAN DATE
April 01, 2025 at 14:32:10 UTC

━━━━━━━━━━━━━━━━━━━━━━━━━━━━

THREAT ASSESSMENT
🚨 MALICIOUS

URLSCAN.IO FINDINGS
Domain registered <48 hours ago. Mimics a known banking portal.
Page contains credential harvesting form fields.

VIRUSTOTAL FINDINGS
14/92 vendors flagged as Phishing.
Detected by: Google SafeBrowsing, Kaspersky, Bitdefender...

INDICATORS OF COMPROMISE
• Lookalike domain targeting financial institution
• Suspicious redirect chain detected
• No HTTPS certificate from trusted authority

RECOMMENDATION
Do NOT visit this URL. Report to your IT/security team immediately.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 SCAN REFERENCES
• URLScan: https://urlscan.io/result/...
• VirusTotal: https://www.virustotal.com/gui/url/...
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| [n8n](https://n8n.io/) | Workflow automation engine |
| [Telegram Bot API](https://core.telegram.org/bots/api) | User interface for input/output |
| [VirusTotal API v3](https://developers.virustotal.com/) | Multi-vendor malware & phishing detection |
| [URLScan.io API](https://urlscan.io/docs/api/) | URL behavior and screenshot analysis |
| [OpenAI GPT-4o-mini](https://platform.openai.com/) | AI-powered threat report generation |
| [LangChain (n8n)](https://docs.n8n.io/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/) | AI agent orchestration |


---

## 📁 Project Structure

```
phishing-analysis-bot/
│
├── Phishing_Analysis.json    # n8n workflow export
└── README.md                 # Project documentation
```

---

## 🔐 Security Notice

> API keys in the workflow JSON have been rotated and invalidated. **Never commit live API keys to a public repository.** Use n8n's built-in credential manager to store all sensitive keys securely.

---

## 💡 Use Cases

- **Security Operations** — Quickly triage suspicious links received via email or messaging apps
- **IT Teams** — Empower non-technical staff to self-verify URLs before clicking
- **Security Awareness Training** — Demonstrate phishing detection in real-time
- **Personal Safety** — Check any link before opening it on your devices

---

## 🗺️ Future Enhancements

- [ ] Add WHOIS domain age lookup
- [ ] Integrate Shodan for IP reputation checks
- [ ] Add screenshot preview of scanned URL
- [ ] Support for bulk URL scanning via CSV upload
- [ ] Dashboard for historical scan results

---

## 👤 Author

**ROHIT**  
Cybersecurity Enthusiast | Automation Engineer  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://linkedin.com/in/YOUR_PROFILE)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?logo=github)](https://github.com/rohit-1006)

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use, modify, and distribute.

---

> ⭐ If you found this project useful, consider giving it a star on GitHub!
