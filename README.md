# Project_LLM — Local LLM Setup Guide (Windows 11 + PowerShell)

A complete guide to set up a **local AI environment** using:

* Ollama for running local LLMs
* Local isolated Python environment
* Open WebUI for browser-based chat UI

This project is designed so that **everything stays inside one folder** and **does not interfere with system Python or existing software**.

---

# Project Goal

This setup creates a fully isolated local AI workspace inside:

```text id="zmg6sa"
D:\Project_LLM\
```

Features:

✅ Local LLM execution
✅ Browser-based chat interface
✅ Isolated Python environment
✅ Local model storage
✅ Dedicated application data storage
✅ No system Python interference
✅ Easy backup / move to another device

---

# Complete Folder Structure

After completing setup:

```text id="h96x2g"
Project_LLM/
│
├── README.md
│
├── ollama/
│   └── README.md
│
├── python/
│   └── README.md
│
├── open-webui/
│   └── README.md
│
├── first-run/
│   └── README.md
│
├── ollama_models/
│   ├── blobs/
│   └── manifests/
│
├── python/
│   ├── installer/
│   │   └── python311.exe
│   │
│   ├── python311/
│   │   ├── python.exe
│   │   └── ...
│   │
│   └── venv/
│       ├── Scripts/
│       ├── Lib/
│       └── ...
│
├── open-webui/
│   └── (Open WebUI files)
│
└── open-webui_data/
    ├── cache/
    ├── uploads/
    ├── database/
    ├── logs/
    └── settings/
```

---

# Setup Order

Follow the documentation in this exact order.

---

## Step 1 — Install Ollama

Documentation:

```text id="9i2otq"
./ollama/README.md
```

This file covers:

* installing Ollama
* setting model storage path
* verifying installation
* downloading first model

Output:

```text id="0qtrqj"
D:\Project_LLM\ollama_models\
```

Models are stored here.

---

## Step 2 — Install Local Python

Documentation:

```text id="cq3l5p"
./python/README.md
```

This file covers:

* downloading correct Python version
* local isolated installation
* creating virtual environment
* verifying Python path

Output:

```text id="h8qjlwm"
D:\Project_LLM\python\
```

This Python is dedicated only for Open WebUI.

System Python remains untouched.

---

## Step 3 — Install Open WebUI

Documentation:

```text id="s9u3xq"
./open-webui/README.md
```

This file covers:

* activating virtual environment
* installing Open WebUI
* setting data directory
* verifying installation

Output:

Application files:

```text id="7u0n0n"
D:\Project_LLM\open-webui\
```

Data files:

```text id="mce3q4"
D:\Project_LLM\open-webui_data\
```

---

## Step 4 — First Launch

Documentation:

```text id="fr1tm7"
./first-run/README.md
```

This file covers:

* starting Ollama service
* launching Open WebUI
* connecting models
* creating account
* first chat
* available features

---

# How Components Connect

System flow:

```text id="rnzzcr"
User Browser
     ↓
Open WebUI
     ↓
Local Python venv
     ↓
Ollama Engine
     ↓
LLM Model
```

Storage flow:

```text id="ck5vsa"
Models  → D:\Project_LLM\ollama_models\
Data    → D:\Project_LLM\open-webui_data\
Python  → D:\Project_LLM\python\
UI      → D:\Project_LLM\open-webui\
```

Everything stays inside one workspace.

---

# Environment Variables Used

## Ollama Models

```powershell id="8p7wnu"
OLLAMA_MODELS=D:\Project_LLM\ollama_models
```

Stores all models locally.

---

## Open WebUI Data

```powershell id="s1uh7t"
DATA_DIR=D:\Project_LLM\open-webui_data
```

Stores:

* chats
* uploads
* settings
* cache
* logs

---

# Daily Usage

Start Ollama:

```powershell id="3t6l9q"
ollama serve
```

Activate Python:

```powershell id="4dwnv8"
D:\Project_LLM\python\venv\Scripts\Activate.ps1
```

Start Open WebUI:

```powershell id="uqs4m5"
open-webui serve
```

Open browser:

```text id="jlwm08"
http://localhost:8080
```

Start chatting with your local model.

---

# Advantages of This Setup

* portable
* clean
* isolated
* organized
* easy to backup
* easy to migrate
* safe for system Python
* easy model management

---

# Documentation Map

```text id="i4uv3p"
README.md                  → master guide
ollama/README.md           → Ollama setup
python/README.md           → Python setup
open-webui/README.md       → Open WebUI setup
first-run/README.md        → First launch guide
```

Follow them in order.

---

# Final Result

You get a complete local AI stack running on Windows:

✅ Ollama engine
✅ Local models
✅ Isolated Python
✅ Open WebUI
✅ Local storage
✅ Browser UI
✅ No system interference
