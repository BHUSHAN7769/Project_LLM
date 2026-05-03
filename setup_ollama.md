# Ollama Setup (Windows 11 + PowerShell)

This guide explains how to install **Ollama** locally inside the `Project_LLM` workspace, configure model storage inside the project folder, verify installation, and download a small LLM for testing.

---

# Folder Structure

After setup, your project should look like:

```text
Project_LLM/
│
├── ollama_models/      # All downloaded LLM models stored here
├── python/             # Local Python installation / venv (used later)
├── open-webui/         # Open WebUI installation (used later)
└── ...
```

---

# Step 1 — Open PowerShell

Open **Windows PowerShell** as **Administrator**.

You can do this by:

* Press `Win + X`
* Click **Windows PowerShell (Admin)**

or search:

```text
PowerShell
```

then choose:

```text
Run as Administrator
```

---

# Step 2 — Install Ollama

Run:

```powershell
winget install Ollama.Ollama
```

Wait until installation completes.

This installs the Ollama engine on Windows.

---

# Step 3 — Verify Installation

Close PowerShell and open a new PowerShell window.

Check installation:

```powershell
ollama --version
```

Expected output:

```text
ollama version x.x.x
```

Check service:

```powershell
ollama list
```

Expected output (first time):

```text
NAME    ID    SIZE    MODIFIED
```

(Empty list is normal.)

---

# Step 4 — Create Local Model Folder

Navigate to your project:

```powershell
cd D:\Project_LLM
```

Create model storage:

```powershell
mkdir ollama_models
```

---

# Step 5 — Set Model Storage Path

By default, Ollama stores models in your user profile.
We will redirect storage to:

```text
D:\Project_LLM\ollama_models
```

Set environment variable:

```powershell
setx OLLAMA_MODELS "D:\Project_LLM\ollama_models"
```

You should see:

```text
SUCCESS: Specified value was saved.
```

Restart PowerShell.

Verify:

```powershell
echo $env:OLLAMA_MODELS
```

Expected:

```text
D:\Project_LLM\ollama_models
```

---

# Step 6 — Start Ollama

Run:

```powershell
ollama serve
```

Keep this terminal running.

Ollama is now ready to serve models locally.

---

# Step 7 — Download a Small Test Model

Open a **new PowerShell window**.

Download a lightweight model:

```powershell
ollama pull gemma3:4b
```

This may take several minutes depending on internet speed.

---

# Step 8 — Verify Download

Check installed models:

```powershell
ollama list
```

Example:

```text
NAME         SIZE
gemma3:4b    ...
```

Check folder contents:

```powershell
Get-ChildItem D:\Project_LLM\ollama_models
```

Model files should appear there.

---

# Step 9 — Test the Model

Run:

```powershell
ollama run gemma3:4b
```

Example:

```text
>>> Hello
```

Model response confirms installation is working.

Exit:

```text
/bye
```

---

# Notes

* Keep `ollama serve` running whenever using local models.
* All downloaded models will now be stored inside:

```text
Project_LLM/ollama_models
```

* This keeps your project self-contained and organized.

---

# Completed

You now have:

✅ Ollama installed
✅ Local model storage configured
✅ Environment variable set
✅ Installation verified
✅ Small LLM downloaded
✅ Model tested successfully
