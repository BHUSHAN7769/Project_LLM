# Python Setup for Open WebUI (Windows 11 + PowerShell)

This guide installs a **dedicated local copy of Python** inside `Project_LLM/python/` specifically for **Open WebUI**.

This installation is **fully isolated** from your system Python.

## Benefits

* Does **not** modify existing Python on your PC
* Does **not** affect PATH for device Python
* Does **not** interfere with other Python projects
* Used only for Open WebUI
* Virtual environment created from this local Python only

---

## Folder Structure

After setup:

```text
Project_LLM/
│
├── ollama_models/
├── python/
│   ├── installer/
│   ├── python311/
│   └── venv/
│
├── open-webui/
└── ...
```

Where:

* `installer/` → downloaded Python installer
* `python311/` → local isolated Python installation
* `venv/` → virtual environment used by Open WebUI

---

## Why Python 3.11?

**Open WebUI works most reliably on Python 3.11.x**

Recommended version:

```text
Python 3.11.9 (64-bit)
```

Reason:

* Stable
* Excellent package compatibility
* Avoids dependency issues seen in newer versions

---

## Step 1 — Open PowerShell

Open **Windows PowerShell**

Navigate to project folder:

```powershell
cd D:\Project_LLM
```

Create Python folders:

```powershell
mkdir python
mkdir python\installer
mkdir python\python311
mkdir python\venv
```

---

## Step 2 — Download Python Installer

Download **Python 3.11.9 (64-bit)**:

```powershell
Invoke-WebRequest `
-OutFile ".\python\installer\python311.exe" `
-Uri "https://www.python.org/ftp/python/3.11.9/python-3.11.9-amd64.exe"
```

Verify:

```powershell
Get-ChildItem .\python\installer
```

Expected output:

```text
python311.exe
```

---

## Step 3 — Install Python Locally

Install only inside project folder:

```powershell
Start-Process `
-Wait `
-FilePath ".\python\installer\python311.exe" `
-ArgumentList "/quiet InstallAllUsers=0 PrependPath=0 Include_test=0 TargetDir=D:\Project_LLM\python\python311"
```

### What this does

* `InstallAllUsers=0` → current user only
* `PrependPath=0` → does **not** modify system PATH
* `TargetDir=...` → installs only inside project folder

Your system Python remains untouched.

---

## Step 4 — Verify Local Python

Check version:

```powershell
D:\Project_LLM\python\python311\python.exe --version
```

Expected:

```text
Python 3.11.9
```

Check pip:

```powershell
D:\Project_LLM\python\python311\python.exe -m pip --version
```

If pip runs successfully, installation is correct.

---

## Step 5 — Upgrade pip (Local Only)

Upgrade pip inside local Python:

```powershell
D:\Project_LLM\python\python311\python.exe -m pip install --upgrade pip
```

This only affects project Python.

---

## Step 6 — Create Virtual Environment

Create venv using local Python:

```powershell
D:\Project_LLM\python\python311\python.exe -m venv D:\Project_LLM\python\venv
```

This virtual environment is linked only to local Python 3.11.

---

## Step 7 — Activate Virtual Environment

Activate:

```powershell
D:\Project_LLM\python\venv\Scripts\Activate.ps1
```

Expected terminal:

```text
(venv) PS D:\Project_LLM>
```

---

## Step 8 — Verify Active Python

Check version:

```powershell
python --version
```

Expected:

```text
Python 3.11.9
```

Check executable path:

```powershell
Get-Command python
```

Expected:

```text
D:\Project_LLM\python\venv\Scripts\python.exe
```

This confirms venv is using isolated project Python.

---

## Step 9 — Deactivate Virtual Environment

When finished:

```powershell
deactivate
```

---

## Final Result

You now have:

✅ Local Python 3.11.9 inside project folder
✅ No system PATH changes
✅ No interference with device Python
✅ Dedicated pip installation
✅ Dedicated virtual environment for Open WebUI
✅ Fully self-contained Python setup
