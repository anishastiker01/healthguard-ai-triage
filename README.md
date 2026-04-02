# 🫀 HealthGuard — True Agentic AI Triage System

> An AI-powered health monitoring and emergency triage system built with **Claude AI (Anthropic)** using the **Tool Use API** for true autonomous agentic reasoning.

---

## 🚀 Live App

### 👉 [CLICK HERE TO OPEN THE APP](https://anishastiker01.github.io/healthguard-ai-triage/) 👈

> Opens directly in your browser — no installation, no server, no setup needed.

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

| Feature | Traditional AI | HealthGuard Agentic AI |
|---|---|---|
| Tool call order | Hardcoded | **Claude decides** |
| Number of loops | Fixed | **Claude decides when to stop** |
| Which tools run | Scripted | **Claude picks based on findings** |
| Replanning | Never | **Claude adapts mid-loop** |
| API calls | 1 total | **Multiple — one per loop** |

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
│  🧠 THINK — What should I check?   │
│  ⚡ CALL TOOL — Claude's choice     │
│  👁 OBSERVE — Read result           │
│  🔁 LOOP — until Claude is ready    │
│  ✅ FINAL DECISION                  │
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

→ AI gives personalized sleep, diet, hydration and exercise advice.

---

### ⚠️ Stage 2 — Medium Deviation (Medical Consultation)
Two or more moderate flags detected.

→ AI recommends nearby specialist doctors and sends the health report.

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

→ AI immediately dispatches nearest ambulance and transmits live vitals to ER.

---

## 🛠️ Tools Available to Claude

| Tool | What It Does |
|---|---|
| `check_vital_ranges` | Flags abnormal vitals with severity |
| `compute_health_score` | Returns overall health score 0–100 |
| `detect_risk_pattern` | Detects clinical risk patterns |
| `classify_triage_stage` | Classifies patient into Stage 1, 2, or 3 |
| `get_specialist_recommendations` | Returns matched specialist doctors |
| `dispatch_emergency` | Dispatches ambulance with ETA |

---

## 📡 Supported Devices

### ⌚ Wearables
- Fitbit Sense 2 · Apple Watch Ultra · Garmin Vívosmart 5 · Samsung Galaxy Watch 6

### 🏥 Clinical Monitors
- Philips IntelliVue MX40 · Omron HeartGuide · Masimo Root · Biobeat Patch · GE CARESCAPE B650

---

## 🖥️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| AI Engine | Claude Sonnet (Anthropic API) |
| AI Pattern | True Agentic — Tool Use API |
| Device Protocol | Simulated BLE 5.2 / HL7-FHIR |
| Deployment | GitHub Pages |

---

## 👨‍💻 Author

**anishastiker01** — Final year project demonstrating Agentic AI in Healthcare.

---

## 📄 License

MIT License — free to use, modify, and distribute.
