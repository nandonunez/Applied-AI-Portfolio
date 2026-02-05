
# Public Healthcare Agent 🏥🗣️

**Conversational AI voice assistant for public health services.** Sabela is a bilingual agent for appointment management, patient validation, and real-time scheduling, supporting natural language in Galician and Spanish. Easily adaptable for any public healthcare system.

## 🚀 Key Features

- **Bilingual & Native**: Responds primarily in Galician, adapting to Spanish when users prefer (configurable per patient profile)
- **Real-time Appointment Management**: SQL-integrated scheduling with live availability checking (Mon-Fri), booking, listing, and cancellation
- **Low Latency**: FastRTC streaming for real-time audio interactions
- **Modular AI Stack**:
  - **LLM**: Groq (Llama/GPT-OSS) & OpenAI support
  - **STT**: Groq Whisper, Azure Speech, local models (Moonshine)
  - **TTS**: Azure Speech, RunPod (Orpheus), local models (Kokoro)
- **Production-Ready**: LangGraph orchestration, SQLModel persistence, Docker & `uv` deployment

## 🏗️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Voice/AI** | FastRTC, LangGraph, Groq/OpenAI APIs |
| **Speech** | Whisper (STT), Azure Speech/Kokoro (TTS) |
| **Backend** | Python 3.11+, FastAPI |
| **Database** | SQLite/PostgreSQL, SQLModel ORM |
| **Infrastructure** | Docker, uv package manager |
| **Infrastructure** | Healthcare standards (HL7, FHIR) |

## 📦 Project Structure

```
sergas-agent/
├── src/realtime_phone_agents/
│   ├── agent/           # LangGraph workflows & FastRTC integration
│   ├── avatars/         # Sabela personality & prompts
│   ├── infrastructure/  # DB models & connection layer
│   └── services/        # Business logic (appointments, patients)
├── data/                # SQLite persistence
├── notebooks/           # Flow validation & testing
├── scripts/             # DB seeding, utilities
└── pyproject.toml       # UV-managed dependencies
```

## 🚀 Quick Start

```bash
# Install dependencies
uv sync

# Seed database with test data
uv run scripts/seed_db.py

# Validate agent workflows (notebooks)
jupyter notebook notebooks/

# Launch voice UI
uv run scripts/run_gradio_application.py
```

## ⚙️ Requirements

- Python 3.11+
- `uv` package manager
- Groq API key (minimum), optional: Azure/OpenAI keys
- Docker (optional, for full deployment)
