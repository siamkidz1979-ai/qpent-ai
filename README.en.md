<div align="center">

[ภาษาไทย](./README.md) · **English**

# 🛡️ QPent Community Edition

**AI-powered penetration testing — free, self-hosted, bring-your-own-LLM.**

QPent drives real Kali tools with an AI agent that plans, scans, and explains
findings for you. The Community edition is free for authorized security testing
of systems **you own or are permitted to test**.

[Upgrade to Pro →](https://www.siamlms.online)

</div>

---

## ⚠️ Authorized use only

Penetration testing without the target owner's **written authorization** is
illegal in most jurisdictions. By using QPent you agree to test only systems you
own or have explicit permission to assess. You are solely responsible for how
you use this tool. See [LICENSE](./LICENSE).

Good legal practice targets while you learn: your own lab/VMs,
[OWASP Juice Shop](https://owasp.org/www-project-juice-shop/),
`scanme.nmap.org`, and public pentest playgrounds.

---

## 🚀 Quick start

Requires Docker + Docker Compose.

```bash
# 1. get the compose file
curl -O https://raw.githubusercontent.com/siamkidz1979-ai/qpent-ai/main/docker-compose.yml

# 2. run
docker compose up -d

# 3. open the UI
#    http://localhost:7860
#    login:  admin  /  admin@qpent   (you'll be forced to set a new password)
```

### Add your LLM (bring-your-own-key)

QPent Community does **not** ship an AI key — you plug in your own:

1. Log in → **Settings → Providers**
2. Add a key for any supported provider: **OpenAI, Anthropic (Claude),
   OpenRouter, Gemini, Mistral, Groq, DeepSeek, …**
3. Or run it fully free & local with your own **Ollama** (uncomment `OLLAMA_URL`
   in `docker-compose.yml`).

Then pick your model in **Settings** and start a scan.

---

## ✨ What you get (Community)

- 🤖 AI agent that auto-selects and runs Kali tools (nmap, nikto, sqlmap,
  nuclei, whatweb, gobuster, ffuf, wfuzz, wafw00f, …)
- 🧠 On-screen AI vulnerability analysis (severity, evidence, explanation)
- 🖥️ Live terminal streaming of every command
- 🔑 Bring-your-own-LLM (cloud API key or local Ollama)
- 📄 View the system-generated report on screen

> Community scans are limited to **5 target IPs per run**.

## 🆚 Community vs Pro

| Feature | Community (free) | Pro |
|---|:---:|:---:|
| AI-driven scanning | ✅ | ✅ |
| Targets per scan | 5 IPs | Depends on plan |
| On-screen AI analysis | ✅ | ✅ |
| LLM | your own key / Ollama | hosted for you |
| Export reports (PDF / DOCX / CSV) | — | ✅ |
| Risk management + action plans | — | ✅ |
| Compliance mapping (OWASP/ISO/PCI/HIPAA/PDPA/NIST) | — | ✅ |
| OpenVAS / GVM + ZAP deep VA | — | ✅ |
| Knowledge-base (RAG) augmented analysis | — | ✅ |
| Support & updates | community | priority |

**[See Pro plans → qpent.siamlms.online](https://www.siamlms.online)**

---

## 🔧 Configuration

| Env var | Default | Purpose |
|---|---|---|
| `QPENT_EDITION` | `free` | keep as `free` for the Community edition |
| `DATABASE_URL` | — | PostgreSQL (pgvector) connection string |
| `OLLAMA_URL` | `http://localhost:11434` | point at your own Ollama (optional) |
| `FREE_MAX_IPS` | `5` | max target IPs per scan |
| `QPENT_ADMIN_PW` | `admin@qpent` | initial admin password (change on first login) |

## ❓ FAQ

**Do I need to pay for an AI key?** No. Use your own provider key, or run a local
Ollama model for free.

**Is my data sent anywhere?** Scans run locally in your container. Only your LLM
calls go to whichever provider *you* configure.

**Can I scan more than 5 IPs?** That's a Pro feature — [upgrade here](https://www.siamlms.online).

---

<div align="center">
<sub>© QPent. QPent Community Edition is distributed under a proprietary license — see <a href="./LICENSE">LICENSE</a>. Not affiliated with the Kali Linux / OffSec project; bundled tools remain under their own licenses.</sub>
</div>
