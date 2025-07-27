Overview
**XReconScanner**

is an all-in-one **web reconnaissance automation tool** designed for ethical hackers, bug bounty hunters, and penetration testers. It combines subdomain enumeration, OSINT scanning, directory fuzzing, AI-based attack surface suggestions, and auto-report generation — all inside **Termux**.

---

## 🧠 Features

- 🔍 **Subdomain Enumeration** via APIs & `crt.sh`, `assetfinder`, `amass`
- 🌐 **Live Subdomain Detection** using `httpx`
- 🛠️ **Directory Bruteforcing** with `ffuf`
- 📄 **Sensitive File Discovery**: `.git`, `.env`, `robots.txt`, backups
- 🧪 **Auto XSS & SQLi Payload Testing** *(basic)*
- 📦 **JavaScript Link Extraction**
- 🧠 **AI Suggestions** for attack surface *(GPT-4/3.5 API optional)*
- 🧾 **HTML Report Generator** — everything documented beautifully

---

## 📦 Installation (Termux)

```bash
pkg update && pkg upgrade -y
pkg install git python curl jq -y
git clone https://github.com/codewhishperx/XReconScanner
cd XReconScanner
pip install -r requirements.txt
chmod +x xrecon.sh
./xrecon.sh
````

---

## 📂 Folder Structure

```
XReconScanner/
├── xrecon.sh                  # Main Bash Launcher
├── requirements.txt           # Python dependencies
├── modules/                   # Python modules
│   ├── subdomains.py
│   ├── dirfinder.py
│   ├── ai_suggestor.py
│   └── reporter.py
├── output/
│   └── target.com/
│       ├── subdomains.txt
│       ├── alive.txt
│       └── report.html
├── LICENSE
└── README.md
```

---

## 💡 AI Integration

> Add your OpenAI API key in `modules/ai_suggestor.py` to get GPT-powered bug bounty tips:

```python
openai.api_key = "YOUR_OPENAI_API_KEY"
```

---

## 🖼️ Sample Output

```
💡 Suggestions for target.com:
- Check exposed .env files
- Use ffuf on /admin, /dev, /test paths
- Look for reflected parameters like ?q=
```

📄 Output saved in `output/target.com/report.html`

---

## 🧪 Payload Support

XReconScanner includes basic XSS & SQLi payloads fired on live subdomains:

* `<script>alert(1)</script>`
* `' OR 1=1 --`
* etc.

Advanced scanner versions will be added soon.

---

## ✅ Use Cases

* Bug Bounty Recon Automation
* Penetration Test Scanning
* Lightweight OSINT Toolkit for Termux
* Daily Recon Bot (Cron-friendly)

---

## ⚠️ Disclaimer

> This tool is for **educational and authorized testing** only. Unauthorized usage on systems you do not own is strictly forbidden and illegal.

---

## 📢 Credits

* Developed by **Code Whishper X**
* Tools used: `amass`, `ffuf`, `httpx`,`jq`, `crt.sh`
* Inspired by community projects, simplified for mobile hackers

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

