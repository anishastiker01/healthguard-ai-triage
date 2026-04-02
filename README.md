# 🫀 HealthGuard — True Agentic AI Triage System

> An AI-powered health monitoring and emergency triage system built with **Claude AI (Anthropic)** using the **Tool Use API** for true autonomous agentic reasoning.

---

## 🚀 Live Demo

Open `healthguard_triage.html` directly in any browser — no installation, no server needed.

---

## 📌 What is HealthGuard?

HealthGuard is a real-time patient health triage system that:

- **Simulates a live wearable / clinical monitor** connection (BLE / HL7-FHIR)
- **Streams 8 vital parameters** in real-time from the device
- **Runs a true agentic AI loop** powered by Claude (Anthropic Tool Use API)
- **Autonomously classifies** the patient into 3 triage stages
- **Takes action** — recommends doctors (Stage 2) or dispatches ambulance (Stage 3)

---

## 🧠 What Makes It Truly Agentic?

Most AI health apps send one prompt and get one answer. HealthGuard is different.

| Feature | Traditional AI | HealthGuard Agentic AI |
|---|---|---|
| Tool call order | Hardcoded | **Claude decides** |
| Number of loops | Fixed | **Claude decides when to stop** |
| Which tools run | Scripted | **Claude picks based on findings** |
| Replanning | Never | **Claude adapts mid-loop** |
| API calls | 1 total | **Multiple — one per loop** |

Claude receives the patient vitals and a set of medical tools. It then **autonomously decides** which tools to call, in what order, and when it has gathered enough evidence to make a final clinical decision — without any hardcoded steps.

---

## ⚙️ How It Works

```
Wearable Device
      │
      ▼ BLE / HL7-FHIR
┌─────────────────┐
│  Sensor Stream  │  ← 8 vital channels collected automatically
│  HR · SpO2 · BP │
│  Temp · Sleep   │
│  Water · Steps  │
│  Stress         │
└────────┬────────┘
         │
         ▼
┌─────────────────────────────────────┐
│        Claude Agentic Loop          │
│                                     │
│  Claude receives vitals + tools     │
│         │                           │
│         ▼                           │
│   🧠 THINK — What should I check?  │
│         │                           │
│         ▼                           │
│   ⚡ CALL TOOL — Claude's choice    │
│         │                           │
│         ▼                           │
│   👁 OBSERVE — Read result          │
│         │                           │
│         ▼                           │
│   🔁 LOOP — until Claude decides    │
│         │     it has enough info    │
│         ▼                           │
│   ✅ FINAL DECISION                 │
└────────┬────────────────────────────┘
         │
         ▼
┌─────────────────┐
│   TRIAGE RESULT │
│  Stage 1/2/3    │
└─────────────────┘
```

---

## 🏥 Triage Stages

### ✅ Stage 1 — Low Deviation (Lifestyle Correction)
| Vital | Normal Range |
|---|---|
| Heart Rate | 60–100 bpm |
| SpO2 | ≥ 95% |
| Blood Pressure | 90–130 mmHg |
| Temperature | 36.1–37.2 °C |
| Sleep | 7–9 hrs |
| Water Intake | 1.5–3.5 L |
| Stress | 1–4 / 10 |
| Steps | 7,000+ |

→ AI provides personalized sleep, diet, hydration, and exercise advice.

---

### ⚠️ Stage 2 — Medium Deviation (Medical Consultation)
Two or more moderate flags detected.

→ AI recommends nearby specialist doctors and sends the patient's health report directly to them.

```json
[
  { "name": "Dr. Arun Mehta", "specialty": "Cardiology", "distance": "1.8 km" },
  { "name": "Dr. Vikram Rao", "specialty": "Pulmonology", "distance": "2.4 km" },
  { "name": "Dr. Nisha Patel", "specialty": "Neurology", "distance": "3.1 km" }
]
```

---

### 🚨 Stage 3 — Critical Emergency (Ambulance Dispatch)
Any life-threatening vital detected:
- HR > 140 or < 45 bpm
- SpO2 < 90%
- BP > 180 mmHg
- Temperature > 39.5°C

→ AI immediately dispatches nearest ambulance, transmits live vitals to the receiving hospital ER.

---

## 🛠️ Tools Available to Claude

Claude autonomously decides which of these to call:

| Tool | What It Does |
|---|---|
| `check_vital_ranges` | Flags abnormal vitals with severity (NORMAL / ELEVATED / CRITICAL) |
| `compute_health_score` | Returns overall health score 0–100 |
| `detect_risk_pattern` | Detects clinical risk patterns (hypertensive crisis, hypoxia, etc.) |
| `classify_triage_stage` | Classifies patient into Stage 1, 2, or 3 |
| `get_specialist_recommendations` | Returns matched specialist doctors for Stage 2 |
| `dispatch_emergency` | Dispatches ambulance for Stage 3 with ETA and ER details |

---

## 📡 Supported Devices

### ⌚ Wearables
- Fitbit Sense 2 (BLE 5.2)
- Apple Watch Ultra (BLE 5.0)
- Garmin Vívosmart 5 (ANT+)
- Samsung Galaxy Watch 6 (BLE 5.2)

### 🏥 Clinical Health Monitoring Systems
- Philips IntelliVue MX40 (HL7/FHIR)
- Omron HeartGuide BP Monitor (MQTT)
- Masimo Root Monitor (IEEE 11073)
- Biobeat Wireless Patch Monitor (HL7/FHIR)
- GE CARESCAPE B650 (IEEE 11073)

---

## 🖥️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| AI Engine | Claude Sonnet (Anthropic API) |
| AI Pattern | True Agentic — Tool Use API |
| Device Protocol | Simulated BLE 5.2 / HL7-FHIR |
| Deployment | GitHub Pages (static, no server) |

---

## 📁 Project Structure

```
healthguard-ai-triage/
├── healthguard_triage.html    ← Entire app (single file)
└── README.md                  ← This file
```

---

## 🔧 Setup & Usage

### Option 1 — Open directly (no API key)
1. Download `healthguard_triage.html`
2. Double-click to open in any browser
3. Select a device → Click **Collect & Run Agent**
4. Local rule engine runs and shows full triage result

### Option 2 — Full Agentic Mode (with API key)
1. Get your API key from [console.anthropic.com](https://console.anthropic.com)
2. Open the app → paste key in the **API Key** field
3. Select a device → Click **Collect & Run Agent**
4. Watch Claude autonomously call tools, reason, and decide

---

## 🔐 API Key Note

The API key is used **only in your browser** — it is never stored, never sent to any server other than Anthropic's API directly. You can also leave it blank to use the local fallback engine.

---

## 👨‍💻 Author

Built as a final year project demonstrating **Agentic AI in Healthcare**.

- **Technology:** Anthropic Claude AI — Tool Use API
- **Domain:** Health Informatics / AI in Medicine
- **Pattern:** ReAct (Reasoning + Acting) with Anthropic native tool use

---

## 📄 License

MIT License — free to use, modify, and distribute.
