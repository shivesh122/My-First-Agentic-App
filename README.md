# 🚀 Agentic AI: AI‑Powered Data Project Analyzer & Publisher  
> **Turn raw data projects into polished, AI‑enhanced content—and publish it to GitHub or LinkedIn in one click.**

---

## 🔖 Badges  

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)  
![Flask](https://img.shields.io/badge/Flask-000?style=flat&logo=flask&logoColor=white)  
![Requests](https://img.shields.io/badge/Requests-005571?style=flat&logo=requests&logoColor=white)  
![Groq](https://img.shields.io/badge/Groq-FF00FF?style=flat&logo=groq&logoColor=white)  
![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)  

---

## 🎯 Why This Project Exists  

In the modern data‑science landscape, turning a notebook or a dataset into a consumable story is time‑consuming. **Agentic AI** bridges that gap by:

* **Automating analysis** – Leverage the power of the Groq LLM to extract insights, generate summaries, and suggest improvements.
* **Streamlining publishing** – One‑click integration with GitHub and LinkedIn eliminates manual formatting and deployment.
* **Accelerating collaboration** – Share AI‑enhanced content with teammates or the public without leaving your browser.

For hiring managers and product leaders, this means **faster onboarding, higher code quality, and greater visibility** for data initiatives—all built on a minimal, easily maintainable stack.

---

## 🚀 Key Features  

* ⚡ **Single‑page UI** – Upload a ZIP, a notebook, or raw data; receive instant AI‑generated summaries.
* 🧠 **Groq LLM integration** – Fast, cost‑effective inference powered by the cutting‑edge `groq` SDK.
* 🔗 **Social & code publishing** – Post the results to a GitHub repo or a LinkedIn article with a single button.
* 🔐 **OAuth authentication** – Secure GitHub and LinkedIn credentials via environment‑backed secrets.
* 📦 **Zero‑config deployment** – Vercel‑ready (`vercel.json`) with a single command to deploy.
* 🛠️ **Portable Python stack** – Flask, Werkzeug, requests, and Groq – all tested and production‑ready.

---

## 🏗️ Architecture / Tech Stack Overview  

```
+-------------------+      +------------------+      +------------------+
|  Client Browser   | ---> |  Flask Web App   | ---> |   Groq LLM API   |
| (HTML + JS)       |      |  (Python, REST)  |      |  (OpenAI‑style)  |
+-------------------+      +------------------+      +------------------+
                                   |
                                   v
                        +-----------------------+
                        |  GitHub / LinkedIn    |
                        |  (OAuth 2.0)          |
                        +-----------------------+
```

* **Frontend** – Lightweight HTML template served by Flask; no external JS frameworks, keeping the bundle small.
* **Backend** – Pure Python using Flask for routing, Werkzeug for file handling, `requests` for HTTP, and `groq` for LLM calls.
* **Data Flow**  
  1. User uploads a file or folder.  
  2. Flask receives, unzips (if necessary), and sends content to Groq.  
  3. Groq returns AI‑generated analysis.  
  4. User chooses to publish; the app authenticates with GitHub/LinkedIn and posts the content.

* **Deployment** – Vercel’s `@vercel/python` build target; routes are proxied to `app.py`.  
* **Security** – All secrets are pulled from environment variables; `FLASK_SECRET_KEY` is static for Vercel.

---

## 💻 Getting Started / Installation  

### Prerequisites  
* Python 3.9+ (tested on 3.10)  
* A **Groq API key** – register at https://groq.com  
* **GitHub** and **LinkedIn** OAuth credentials (client ID & secret)  

### 1️⃣ Clone the repo  
```bash
git clone https://github.com/your-username/Agentic-Ai-App.git
cd Agentic-Ai-App
```

### 2️⃣ Create a virtual environment (optional but recommended)  
```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
```

### 3️⃣ Install dependencies  
```bash
pip install -r requirements.txt
```

### 4️⃣ Configure environment variables  
Create a `.env` file at the repo root (or set them in your deployment platform):

```dotenv
GROQ_API_KEY=YOUR_GROQ_API_KEY
GITHUB_CLIENT_ID=YOUR_GITHUB_CLIENT_ID
GITHUB_CLIENT_SECRET=YOUR_GITHUB_CLIENT_SECRET
LINKEDIN_CLIENT_ID=YOUR_LINKEDIN_CLIENT_ID
LINKEDIN_CLIENT_SECRET=YOUR_LINKEDIN_CLIENT_SECRET
FLASK_SECRET_KEY=YOUR_FLASK_SECRET_KEY   # Use a secure, static string
```

> **Tip:** For local development you can use `python-dotenv` to load `.env` automatically.

### 5️⃣ Run locally  
```bash
export FLASK_APP=app.py
flask run --debug
```
Navigate to `http://127.0.0.1:5000` in your browser.

### 6️⃣ Deploy to Vercel (optional)  
* Install Vercel CLI: `npm i -g vercel`  
* Log in: `vercel login`  
* Deploy: `vercel` (follow prompts to set env vars in Vercel)

> The provided `vercel.json` will automatically use the Python builder and route all traffic to `app.py`.

---

## 📚 Usage Guide  

1. **Upload** a ZIP file of your data project or a single notebook file.  
2. **Wait** for the AI analysis to finish (Groq response time is usually < 5 s).  
3. **Review** the summary, insights, and suggestions.  
4. **Publish**  
   * *GitHub* – Provide a repo name and optional branch; the app will create a new repo or push to an existing one.  
   * *LinkedIn* – The app will post a new article using your LinkedIn account.

---

## 🤝 Contributing  

Feel free to submit issues or PRs!  
* Create a branch named `feature/…` or `bugfix/…`.  
* Run tests (if added) and lint with `flake8`.  
* Open a PR with a clear description of the change.

---

## 📄 License  

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---