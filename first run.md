# First Run Guide — Launch Open WebUI and Connect Your Local LLM

This guide explains how to start your local AI stack for the first time, connect **Ollama** with **Open WebUI**, create your admin account, and explore Open WebUI features.

---

# Prerequisites

Make sure you completed:

```text id="p0i9rj"
./ollama/README.md
./python/README.md
./open-webui/README.md
```

Required folders:

```text id="olttq7"
D:\Project_LLM\
├── ollama_models\
├── python\
├── open-webui\
└── open-webui_data\
```

---

# Startup Flow

Every time you use Project_LLM:

```text id="0xj7sx"
1. Start Ollama
2. Activate Python venv
3. Start Open WebUI
4. Open browser
5. Chat with your local model
```

---

# Step 1 — Start Ollama Service

Open **PowerShell Window #1**

Run:

```powershell id="7y6m7m"
ollama serve
```

Expected output:

```text id="z5g4nh"
Listening on 127.0.0.1:11434
```

Keep this terminal running.

This terminal acts as your **LLM engine backend**.

---

# Step 2 — Activate Python Environment

Open **PowerShell Window #2**

Activate project Python:

```powershell id="u2pn4q"
D:\Project_LLM\python\venv\Scripts\Activate.ps1
```

Expected:

```text id="blwq1f"
(venv) PS D:\Project_LLM>
```

---

# Step 3 — Start Open WebUI

Run:

```powershell id="2yb3ul"
open-webui serve
```

Expected:

```text id="4mtr2q"
Uvicorn running on http://127.0.0.1:8080
```

Keep this terminal running.

This is your **frontend UI server**.

---

# Step 4 — Open Browser

Open:

```text id="hl8u4z"
http://localhost:8080
```

or

```text id="of8xpd"
http://127.0.0.1:8080
```

Open WebUI homepage will appear.

---

# Step 5 — Create Admin Account

First launch will ask for signup.

Create:

* Name
* Email
* Password

This becomes your local admin account.

Data is stored in:

```text id="t1k63m"
D:\Project_LLM\open-webui_data\
```

No cloud account required.

Everything stays local.

---

# Step 6 — Verify Ollama Connection

Go to:

```text id="w5f1yr"
Settings → Connections
```

You should see:

```text id="u6o8nh"
Ollama Connected
http://localhost:11434
```

If connected successfully, Open WebUI can use your local models.

---

# Step 7 — Select Model

At top-left model dropdown, choose:

Example:

```text id="7vqte5"
gemma3:4b
```

Then start chatting.

Example prompt:

```text id="v8rfrn"
Hello, introduce yourself.
```

If model replies → setup complete.

---

# Open WebUI Features

## 1) Chat Interface

Features:

* clean modern UI
* markdown rendering
* code formatting
* long conversation memory
* multiple chat sessions
* regenerate response
* edit prompts
* copy responses

---

## 2) Multiple Models

Can switch instantly between models:

Example:

* Gemma
* Qwen
* Llama
* DeepSeek
* Phi
* Mistral

Useful for comparing outputs.

---

## 3) Chat History

Stores:

* conversation history
* titles
* timestamps
* search chats
* organize chats

Saved locally.

---

## 4) File Upload

Upload:

* PDF
* TXT
* DOCX
* CSV
* code files
* images (supported models)

Model can analyze uploaded content.

---

## 5) RAG / Knowledge Base

Create private knowledge collections:

Example:

* project docs
* college notes
* manuals
* research papers

Then ask questions on them.

---

## 6) Prompt Templates

Save reusable prompts:

Example:

* coding assistant
* teacher
* analyst
* recruiter
* document summarizer

One click reuse.

---

## 7) Model Parameters

Control:

* temperature
* top_p
* context length
* repetition penalty
* max tokens

Fine-tune behavior.

---

## 8) Tools Support

Depending on model/backend:

* web search
* calculator
* code execution
* custom tools
* APIs

Can create agent workflows.

---

## 9) User Management

Supports:

* multiple users
* admin panel
* access control
* shared resources

Useful for teams/labs.

---

## 10) Local Privacy

Benefits:

* no cloud dependency
* local execution
* private chats
* private files
* offline capable

Ideal for private work.

---

# Recommended Starter Models

## Lightweight (4–8 GB VRAM)

| Model             |    Size |   VRAM |
| ----------------- | ------: | -----: |
| Gemma 3 4B        | ~3–4 GB | 4–6 GB |
| Phi-4 Mini        | ~2–4 GB | 4–6 GB |
| Qwen 2.5 3B       | ~2–3 GB | 4–5 GB |
| Qwen 2.5 Coder 7B | ~4–5 GB | 6–8 GB |
| Llama 3.2 3B      | ~2–3 GB | 4–5 GB |

Best for mid-range PCs.

---

## Medium (8–16 GB VRAM)

| Model          |     Size |     VRAM |
| -------------- | -------: | -------: |
| Gemma 3 12B    |  ~7–9 GB | 10–14 GB |
| Qwen 2.5 14B   | ~8–10 GB | 12–16 GB |
| Mistral 7B     |  ~4–5 GB |   6–8 GB |
| DeepSeek R1 8B |  ~5–7 GB |  8–10 GB |

Strong quality / performance balance.

---

## Large (16+ GB VRAM)

| Model           |       Size |   VRAM |
| --------------- | ---------: | -----: |
| Llama 3 70B     | very large | 40+ GB |
| Qwen 2.5 32B    |      large | 24+ GB |
| DeepSeek R1 32B |      large | 24+ GB |

Best for workstation/server builds.

---

# Daily Run Commands

Terminal 1:

```powershell id="r5c4cn"
ollama serve
```

Terminal 2:

```powershell id="v1h5qs"
D:\Project_LLM\python\venv\Scripts\Activate.ps1
open-webui serve
```

Browser:

```text id="f7m6gd"
http://localhost:8080
```

---

# Setup Complete

You now have:

✅ Local LLM engine
✅ Web-based chat UI
✅ Local storage
✅ Private AI workspace
✅ Multi-model support
✅ File upload support
✅ Knowledge base support
✅ Prompt templates
✅ Fully offline-capable local AI stack
