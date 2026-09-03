<div align="center">

**ภาษาไทย** · [English](./README.en.md)

<img src="https://www.siamlms.online/logo.png" alt="Siam LMS" width="170"/>

# 🛡️ QPent Community Edition

**เครื่องมือทดสอบเจาะระบบขับเคลื่อนด้วย AI — ฟรี ติดตั้งเองได้ ใช้ LLM ของคุณเอง**

QPent สั่งงานเครื่องมือ Kali จริงด้วย AI agent ที่วางแผน สแกน และอธิบายช่องโหว่ให้คุณอัตโนมัติ
รุ่น Community ใช้ฟรีสำหรับการทดสอบความปลอดภัยของระบบที่ **คุณเป็นเจ้าของหรือได้รับอนุญาต** เท่านั้น

[อัปเกรดเป็น Pro →](https://www.siamlms.online)

</div>

---

## ⚠️ ใช้กับระบบที่ได้รับอนุญาตเท่านั้น

การทดสอบเจาะระบบโดยไม่มี **หนังสืออนุญาต** จากเจ้าของระบบ ถือเป็นความผิดตามกฎหมายในเกือบทุกประเทศ
เมื่อใช้ QPent คุณยอมรับว่าจะทดสอบเฉพาะระบบที่คุณเป็นเจ้าของหรือได้รับอนุญาตชัดเจนเท่านั้น
คุณเป็นผู้รับผิดชอบการใช้งานแต่เพียงผู้เดียว (ดู [LICENSE](./LICENSE))

เป้าหมายฝึกซ้อมที่ถูกกฎหมาย: เครื่อง/VM ของคุณเอง,
[OWASP Juice Shop](https://owasp.org/www-project-juice-shop/),
`scanme.nmap.org`, และสนามฝึก pentest สาธารณะต่าง ๆ

---

## 🚀 เริ่มใช้งาน

ต้องมี Docker + Docker Compose

```bash
# 1. ดาวน์โหลดไฟล์ compose
curl -O https://raw.githubusercontent.com/siamkidz1979-ai/qpent-ai/main/docker-compose.yml

# 2. รัน
docker compose up -d

# 3. เปิดหน้าเว็บ
#    http://localhost:7860
#    เข้าสู่ระบบ:  admin  /  admin@qpent   (ระบบจะบังคับให้ตั้งรหัสใหม่ทันที)
```

### ใส่ LLM ของคุณเอง (bring-your-own-key)

QPent Community **ไม่แถม** API key ของ AI มาให้ — คุณใส่ของตัวเอง:

1. เข้าสู่ระบบ → **Settings → Providers**
2. ใส่ key ของผู้ให้บริการที่รองรับ: **OpenAI, Anthropic (Claude),
   OpenRouter, Gemini, Mistral, Groq, DeepSeek, …**
3. หรือใช้ฟรี 100% ด้วย **Ollama** ในเครื่องคุณเอง (uncomment `OLLAMA_URL` ใน `docker-compose.yml`)

จากนั้นเลือกโมเดลใน **Settings** แล้วเริ่มสแกนได้เลย

---

## ✨ ความสามารถ (Community)

- 🤖 AI agent เลือกและรันเครื่องมือ Kali อัตโนมัติ (nmap, nikto, sqlmap,
  nuclei, whatweb, gobuster, ffuf, wfuzz, wafw00f, …)
- 🧠 วิเคราะห์ช่องโหว่ด้วย AI บนหน้าจอ (ระดับความรุนแรง, หลักฐาน, คำอธิบาย)
- 🖥️ สตรีมคำสั่งที่รันสด ๆ ในเทอร์มินัล
- 🔑 ใช้ LLM ของคุณเอง (API key คลาวด์ หรือ Ollama ในเครื่อง)
- 📄 ดูรายงานที่ระบบสร้างบนหน้าจอได้

> รุ่น Community สแกนได้สูงสุด **5 IP ต่อครั้ง**

## 🆚 เทียบ Community กับ Pro

| ความสามารถ | Community (ฟรี) | Pro |
|---|:---:|:---:|
| สแกนด้วย AI | ✅ | ✅ |
| เป้าหมายต่อการสแกน | 5 IP | ตามแพ็กเกจ |
| วิเคราะห์ด้วย AI บนหน้าจอ | ✅ | ✅ |
| LLM | key ของคุณเอง / Ollama | เราจัดให้ (hosted) |
| ดาวน์โหลดรายงาน (PDF / DOCX / CSV) | — | ✅ |
| บริหารความเสี่ยง + แผนแก้ไข | — | ✅ |
| Compliance (OWASP/ISO/PCI/HIPAA/PDPA/NIST) | — | ✅ |
| OpenVAS / GVM + ZAP (VA เชิงลึก) | — | ✅ |
| วิเคราะห์เสริมด้วยฐานความรู้ (RAG) | — | ✅ |
| การสนับสนุน & อัปเดต | ชุมชน | ลำดับความสำคัญสูง |

**[ดูแพ็กเกจ Pro → www.siamlms.online](https://www.siamlms.online)**

---

## 💻 ความต้องการของระบบ

ความต้องการสำหรับติดตั้งและใช้งานจริง (รวมชุดเครื่องมือสแกน + ฐานข้อมูล):

| | ขั้นต่ำ | แนะนำ |
|---|---|---|
| ระบบปฏิบัติการ | Linux 64-bit (Ubuntu 22.04+/Debian 12+) | Linux 64-bit |
| CPU | 16 cores (x86_64 / arm64) | 32+ cores |
| RAM | 16 GB | 32 GB+ |
| ดิสก์ | 500 GB SSD | 1 TB SSD ขึ้นไป |
| ซอฟต์แวร์ | Docker 24+ และ Docker Compose v2 | — |
| เครือข่าย | อินเทอร์เน็ต (สำหรับเรียก LLM API ที่คุณตั้งค่า) | — |

### 🚀 สเปคขั้นสูง — กรณีรัน LLM ในเครื่องเอง (Ollama, ไม่พึ่งคลาวด์)

ถ้าเลือกรันโมเดลในเครื่อง (ผ่าน `OLLAMA_URL`) ต้องใช้เครื่องสเปคสูงขึ้นตามขนาดโมเดล:

| ขนาดโมเดล | RAM / VRAM ขั้นต่ำ | GPU ที่แนะนำ |
|---|---|---|
| เล็ก (7–8B เช่น `qwen2.5:7b`) | 8 GB+ | GPU ≥ 8GB VRAM หรือ Apple Silicon (M1/M2/M3) |
| กลาง (14B) | 16 GB+ | GPU ≥ 12–16GB VRAM |
| ใหญ่ (30B+ เช่น `qwen3:30b`) | 32 GB+ | GPU ≥ 24GB VRAM (เช่น RTX 3090/4090) |

- แนะนำ **GPU NVIDIA (CUDA)** เพื่อความเร็ว — รันบน CPU อย่างเดียวได้แต่ช้ามาก
- เผื่อ **ดิสก์เพิ่ม 5–40 GB** สำหรับเก็บไฟล์โมเดล
- ต้องมีการสแกนพร้อมกันหลายรายการ ให้เพิ่ม CPU/RAM ตามสัดส่วน

## 🔧 การตั้งค่า

| ตัวแปร Env | ค่าเริ่มต้น | หน้าที่ |
|---|---|---|
| `QPENT_EDITION` | `free` | คงไว้เป็น `free` สำหรับรุ่น Community |
| `DATABASE_URL` | — | สตริงเชื่อมต่อ PostgreSQL (pgvector) |
| `OLLAMA_URL` | `http://localhost:11434` | ชี้ไป Ollama ของคุณเอง (ไม่บังคับ) |
| `FREE_MAX_IPS` | `5` | จำนวน IP สูงสุดต่อการสแกน |
| `QPENT_ADMIN_PW` | `admin@qpent` | รหัส admin เริ่มต้น (เปลี่ยนตอน login ครั้งแรก) |

## ❓ คำถามที่พบบ่อย

**ต้องจ่ายค่า AI key ไหม?** ไม่ต้อง ใช้ key ผู้ให้บริการของคุณเอง หรือรัน Ollama ในเครื่องฟรีก็ได้

**ข้อมูลถูกส่งออกไปไหนไหม?** การสแกนทำงานในเครื่อง/คอนเทนเนอร์ของคุณ มีเพียงการเรียก LLM เท่านั้นที่ส่งไปยังผู้ให้บริการที่ *คุณ* ตั้งค่าไว้

**สแกนเกิน 5 IP ได้ไหม?** เป็นฟีเจอร์ของ Pro — [อัปเกรดที่นี่](https://www.siamlms.online)

---

<div align="center">
<sub>© QPent. QPent Community Edition เผยแพร่ภายใต้สัญญาอนุญาตแบบ proprietary — ดู <a href="./LICENSE">LICENSE</a> · ไม่ได้มีส่วนเกี่ยวข้องกับโครงการ Kali Linux / OffSec; เครื่องมือที่รวมมาอยู่ภายใต้สัญญาอนุญาตของตนเอง</sub>
</div>
