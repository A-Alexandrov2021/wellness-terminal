# AI Wellness Terminal 

An edge-ready, fully local voice-interactive AI terminal designed for real-time wellness triage, privacy-first diagnostics, and low-latency audio interaction.

---

## 🏗 Architecture & Hardware Stack

* **Hardware / Environment:** Ubuntu 22.04 / WSL2 on NVIDIA RTX 3060 (12GB VRAM), CUDA 12.x.
* **LLM Engine:** [Ollama](https://ollama.ai/) (`qwen2.5:7b`) — offloaded to **NVIDIA GPU** for fast conversational inference.
* **Speech-to-Text (STT):** [Faster-Whisper](https://github.com/SYSTRAN/faster-whisper) (`small` model) — running on **CPU (int8)** to preserve VRAM for the LLM.
* **Text-to-Speech (TTS):** [Piper TTS](https://github.com/rhasspy/piper) — local neural speech synthesizer with in-memory audio streaming queue.
* **Transport & Frontend:** Flask, Socket.IO, Web Audio API (`AudioContext`) for zero-disk-latency streaming audio playback.
* **Privacy & Offline First:** Strictly zero external telemetry or cloud API dependencies (`HF_HUB_OFFLINE=1`).

---

## 🛠 System Requirements & Prerequisites

* **OS:** Linux (Ubuntu / WSL2)
* **GPU:** NVIDIA GPU with >=6GB VRAM (RTX 3060 12GB recommended)
* **System RAM:** 16GB RAM minimum
* **CUDA Support:** CUDA 12.x drivers installed

---

## ⚡ Quick Start

### 1. Clone & Setup Environment

```bash
git clone [https://github.com/A-Alexandrov2021/wellness-terminal.git](https://github.com/A-Alexandrov2021/wellness-terminal.git)
cd wellness-terminal

python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
