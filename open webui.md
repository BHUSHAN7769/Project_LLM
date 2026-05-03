# Open WebUI Setup (Windows 11 + PowerShell)

This guide installs **Open WebUI** inside your local project folder and configures its data directory to stay inside `Project_LLM`.

This keeps everything isolated and organized.

## Goal

Install Open WebUI in:

```text id="31y5lh"
D:\Project_LLM\open-webui\
```

Store Open WebUI data in:

```text id="dizig4"
D:\Project_LLM\open-webui_data\
```

This includes:

* chats
* settings
* database
* uploaded files
* user data
* cache

Nothing is stored outside your project.

---

## Folder Structure

After setup:

```text id="am4gsg"
Project_LLM/
│
├── ollama_models/
├── python/
│   ├── python311/
│   └── venv/
│
├── open-webui/
├── open-webui_data/
└── ...
```

---

## Prerequisites

Make sure:

* Python local install is completed
* Virtual environment exists
* Ollama is installed

Activate project venv:

```powershell id="04g3b9"
D:\Project_LLM\python\venv\Scripts\Activate.ps1
```

Expected:

```text id="z2snvk"
(venv) PS D:\Project_LLM>
```

---

## Step 1 — Go to Project Folder

```powershell id="b40lrz"
cd D:\Project_LLM
```

Create folders:

```powershell id="9j7m4v"
mkdir open-webui
mkdir open-webui_data
```

---

## Step 2 — Configure Open WebUI Data Path

Set environment variable:

```powershell id="1twx0j"
setx DATA_DIR "D:\Project_LLM\open-webui_data"
```

You should see:

```text id="t8lr6r"
SUCCESS: Specified value was saved.
```

Close PowerShell.

Open a new PowerShell.

Activate venv again:

```powershell id="9w56b3"
D:\Project_LLM\python\venv\Scripts\Activate.ps1
```

Verify:

```powershell id="1vrrq8"
echo $env:DATA_DIR
```

Expected:

```text id="kgr0r5"
D:\Project_LLM\open-webui_data
```

---

## Step 3 — Install Open WebUI

Move into install folder:

```powershell id="n86z3r"
cd D:\Project_LLM\open-webui
```

Install:

```powershell id="6e2g8x"
pip install open-webui
```

Wait for package installation.

This installs Open WebUI inside the project virtual environment.

System Python is not affected.

---

## Step 4 — Verify Installation

Check package:

```powershell id="kkg96i"
pip show open-webui
```

Expected:

```text id="0zod3g"
Name: open-webui
Version: ...
Location: D:\Project_LLM\python\venv\...
```

---

## Step 5 — Verify Data Folder

Run:

```powershell id="d2vzyl"
Get-ChildItem D:\Project_LLM\open-webui_data
```

Folder may be empty initially.

After first launch it will contain:

* database files
* uploads
* configs
* logs

---

## Step 6 — Confirm Isolation

Python executable:

```powershell id="7az7n8"
Get-Command python
```

Expected:

```text id="tq85q6"
D:\Project_LLM\python\venv\Scripts\python.exe
```

Data path:

```powershell id="q8otqk"
echo $env:DATA_DIR
```

Expected:

```text id="jlwm6u"
D:\Project_LLM\open-webui_data
```

This confirms:

* isolated Python
* isolated package install
* isolated Open WebUI data

---

## Final Result

You now have:

✅ Open WebUI installed locally
✅ Uses isolated project Python
✅ No system interference
✅ Dedicated data folder
✅ Chats/config/database stored inside project folder
✅ Clean portable setup

Next step: **First Run / Connect Ollama / Login / Features**
