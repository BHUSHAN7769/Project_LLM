1. Install Ollama via Terminal
Run these commands in PowerShell to download and install Ollama silently.

PowerShell
# Download the Ollama installer to a temporary folder
Invoke-WebRequest -Uri "https://ollama.com/download/OllamaSetup.exe" -OutFile "$env:TEMP\OllamaSetup.exe"

# Run the installer silently
Start-Process -FilePath "$env:TEMP\OllamaSetup.exe" -ArgumentList "/S" -Wait

# Verify installation (You might need to restart PowerShell)
ollama --version
2. Set Custom Model Storage Path
To keep your models inside your Project_LLM/ollama_models folder instead of the default C:\Users directory, set the environment variable.

Note: Replace C:\Path\To\Project_LLM with your actual folder path.

PowerShell
# Set the environment variable for the current user
[System.Environment]::SetEnvironmentVariable("OLLAMA_MODELS", "C:\Path\To\Project_LLM\ollama_models", "User")

# IMPORTANT: 
# 1. Close Ollama from the System Tray (near the clock).
# 2. Restart Ollama for the change to take effect.
3. Download Llama 3.2 (3B)
Once the environment variable is set and Ollama is restarted, pull the model. It will now be saved directly into your project's ollama_models folder.

PowerShell
# Download the Llama 3.2 3B model
ollama pull llama3.2:3b
4. Verify Storage
To ensure the model is in the right place, check your folder:

PowerShell
Get-ChildItem -Path "C:\Path\To\Project_LLM\ollama_models"
