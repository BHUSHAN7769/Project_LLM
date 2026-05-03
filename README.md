# Project_LLM
A modular, step-by-step guide to deploying a fully isolated local AI environment. This project automates the setup of Ollama and Open WebUI using PowerShell, featuring custom storage paths for LLMs and a dedicated Python environment to ensure zero interference with your system's global settings.


# Project_LLM — Local LLM Setup Guide (Windows 11)

A complete self-contained local AI setup using:

* Ollama for running models locally
* Python (isolated local install) for dependency management
* Open WebUI for browser-based chat interface

This repository is designed so **everything runs inside one project folder** without interfering with your device-wide Python setup.

---

# Project Goal

This setup provides:

✅ Local LLM execution
✅ Isolated Python installation
✅ Dedicated virtual environment
✅ Self-hosted Web UI
✅ Local model storage
✅ Local application data storage
✅ No dependency conflicts with system Python
✅ Portable project structure

---

# Complete Folder Structure

```text id="wbdxdk"
Project_LLM/
│
├── README.md                         # Main guide (this file)
│
├── images/                           # Screenshots / output images
│   ├── ollama_install.png
│   ├── python_setup.png
│   ├── openwebui_install.png
│   ├── first_run.png
│   └── ...
│
├── docs/
│   │
│   ├── 01_ollama_setup.md            # Install Ollama + model storage setup
│   ├── 02_python_setup.md            # Install isolated Python + create venv
│   ├── 03_openwebui_setup.md         # Install Open WebUI + configure data dir
│   ├── 04_first_run.md               # First launch + connect Ollama
│   └── 05_features.md                # Open WebUI features walkthrough
│
├── ollama_models/                    # Downloaded LLM models
│
├── python/
│   ├── installer/
│   │   └── python311.exe
│   │
│   ├── python311/                    # Local isolated Python
│   │   ├── python.exe
│   │   └── ...
│   │
│   └── venv/                         # Virtual environment for Open WebUI
│       ├── Scripts/
│       ├── Lib/
│       └── ...
│
├── open-webui/                       # Open WebUI installation workspace
│
└── open-webui_data/                  # Open WebUI persistent data
    ├── cache/
    ├── uploads/
    ├── logs/
    ├── database/
    └── ...
```

---

# Setup Flow

Follow files in this order:

## Step 1 — Install Ollama

Read:

```text id="x1c7t8"
docs/01_ollama_setup.md
```

This guide covers:

* installing Ollama
* configuring:

```text id="n35x0w"
D:\Project_LLM\ollama_models
```

as model storage

* verifying installation
* downloading your first small LLM

---

## Step 2 — Install Local Python

Read:

```text id="r6rr26"
docs/02_python_setup.md
```

This guide covers:

* downloading Python 3.11.x
* installing it locally in:

```text id="e1h9p2"
D:\Project_LLM\python\python311
```

* creating isolated virtual environment:

```text id="fh7o4f"
D:\Project_LLM\python\venv
```

No changes are made to system Python.

---

## Step 3 — Install Open WebUI

Read:

```text id="ddsj5q"
docs/03_openwebui_setup.md
```

This guide covers:

Installing Open WebUI in:

```text id="af0r18"
D:\Project_LLM\open-webui
```

Setting persistent data path:

```text id="uj47mw"
D:\Project_LLM\open-webui_data
```

This keeps:

* chats
* uploads
* configs
* database
* logs

inside the project.

---

## Step 4 — First Launch

Read:

```text id="wv9i8d"
docs/04_first_run.md
```

This guide will cover:

* starting Ollama server
* starting Open WebUI
* opening browser UI
* creating admin account
* connecting local models
* first chat

---

## Step 5 — Features Walkthrough

Read:

```text id="jlwmwv"
docs/05_features.md
```

This guide will cover:

* model switching
* chats
* file upload
* prompt templates
* settings
* API integrations
* advanced options

---

# PowerShell Commands Quick Start

Start Ollama:

```powershell id="9ft4qh"
ollama serve
```

Activate Python venv:

```powershell id="m0f8h4"
D:\Project_LLM\python\venv\Scripts\Activate.ps1
```

Run Open WebUI:

```powershell id="m0j8o4"
open-webui serve
```

Open browser:

```text id="ax0r47"
http://localhost:8080
```

---

# Environment Variables Used

## Ollama Models

```text id="tmjlwm"
OLLAMA_MODELS=D:\Project_LLM\ollama_models
```

Stores all downloaded models locally.

---

## Open WebUI Data

```text id="u3r0fx"
DATA_DIR=D:\Project_LLM\open-webui_data
```

Stores Open WebUI data locally.

---

# Advantages of This Setup

* Clean structure
* Easy backup
* Easy migration to another PC
* No Python conflicts
* No global package pollution
* Dedicated LLM storage
* Dedicated application storage
* Fully local AI stack

---

# Recommended Reading Order

Read in sequence:

```text id="v78ud1"
README.md
↓
docs/01_ollama_setup.md
↓
docs/02_python_setup.md
↓
docs/03_openwebui_setup.md
↓
docs/04_first_run.md
↓
docs/05_features.md
```

---

# Platform

Tested on:

```text id="2x2scf"
Windows 11 + PowerShell
```

---

# Final Result

After completing all guides, you will have a **fully self-hosted local AI environment** running entirely from:

```text id="g58x7d"
D:\Project_LLM
```

Portable, isolated, and ready for development.

