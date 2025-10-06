# 🧠 TFA 2025–2026 — Workshop Setup Guide

Welcome to the **Finance & Python Workshop** 🎓  

Before the first session, please follow this guide carefully so your environment is ready.  
You’ll be using **Python**, **Jupyter notebooks**, and **VS Code** to explore **financial data science**.

---

## 🚀 What you will install
- **Visual Studio Code (VS Code)** — our code editor  
- **Git** — to clone the workshop repository  
- **Python 3.12** — the version used for this workshop  
- A **virtual environment** — keeps your dependencies isolated  
- All required Python libraries — automatically installed from `requirements.txt`  
- Two VS Code extensions: **Python** and **Jupyter**

---

## 💡 Quick Overview

You’ll:
1. Install required tools (VS Code, Python, Git)
2. Clone the workshop repo
3. Create and activate a virtual environment
4. Install dependencies
5. Run the Jupyter notebook

Follow the steps below depending on your operating system.

---

## 🪟 Windows (PowerShell)

### 1️⃣ Install VS Code, Git, and Python
Open **PowerShell as Administrator** and run:
```powershell
winget install -e --id Microsoft.VisualStudioCode
winget install -e --id Git.Git
winget install -e --id Python.Python.3.12
```

Then **close and reopen PowerShell**, and check everything works:
```powershell
python --version
git --version
code --version
```

---

### 2️⃣ Clone the workshop repository
```powershell
git clone https://github.com/arthurdhonneur7/TFA-2025-2026.git
cd TFA-2025-2026
```

(If you don’t have Git, you can also click “Code → Download ZIP” on GitHub, then unzip and open the folder in PowerShell.)

---

### 3️⃣ Create and activate your virtual environment
```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```
You should now see `(.venv)` at the start of your command line.

If you get a security error, run this once as Administrator:
```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```
Then try activating again.

---

### 4️⃣ Install dependencies
```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

This installs everything (pandas, numpy, matplotlib, yfinance, jupyter, etc.).

---

### 5️⃣ Open the project in VS Code
```powershell
code .
```

In VS Code, install these extensions:
- **Python** (by Microsoft)
- **Jupyter** (by Microsoft)

---

### 6️⃣ Select your interpreter
Press **Ctrl+Shift+P → “Python: Select Interpreter” → choose `.venv`**  
(You should see the path ending with `.venv\Scripts\python.exe`.)

---

### 7️⃣ Run the notebook
Open `lecture_1.ipynb`, check the top-right corner says `.venv` as the kernel, and click **Run All** ▶️

---

## 🍎 macOS (Terminal / zsh)

### 1️⃣ Install Homebrew
Run this in **Terminal**:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

After installation, set up your shell:
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

---

### 2️⃣ Install VS Code, Git, and Python
```bash
brew install --cask visual-studio-code
brew install git
brew install python@3.12
```

Check everything works:
```bash
python3 --version
git --version
code --version
```

If `code` isn’t found, open VS Code → **Cmd+Shift+P → “Shell Command: Install 'code' command in PATH”**

---

### 3️⃣ Clone the workshop repository
```bash
git clone https://github.com/arthurdhonneur7/TFA-2025-2026.git
cd TFA-2025-2026
```

---

### 4️⃣ Create and activate a virtual environment
```bash
python3 -m venv .venv
source .venv/bin/activate
```
Your terminal prompt should now start with `(.venv)`.

---

### 5️⃣ Install dependencies
```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

---

### 6️⃣ Open the project in VS Code
```bash
code .
```

Then install the VS Code extensions:
- **Python**
- **Jupyter**

---

### 7️⃣ Select your interpreter
Press **Cmd+Shift+P → “Python: Select Interpreter” → choose `.venv`**  
(The path should end with `.venv/bin/python`.)

---

### 8️⃣ Run the notebook
Open `lecture_1.ipynb`, confirm the top-right kernel says `.venv`, then **Run All** ▶️

---

## ✅ Verify your setup

With the virtual environment activated, run:
```bash
python -c "import sys, pandas as pd, yfinance as yf; print(sys.version); print('pandas', pd.__version__); print('yfinance OK')"
```

Expected output (example):
```
Python 3.12.x
pandas 2.3.2
yfinance OK
```

If you see similar output — you’re ready for the workshop! 🎉

---

## 🧩 Common Issues

**❌ “pip not recognized”**  
→ Make sure Python 3.12 is installed and added to PATH (reopen your terminal after installation).

**❌ “Script execution disabled” (Windows)**  
→ Run:
```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

**❌ Wrong Python version in VS Code**  
→ Use **Command Palette → Python: Select Interpreter → pick `.venv`**.

**❌ macOS: “xcrun: error: invalid active developer path”**  
→ Run:
```bash
xcode-select --install
```

**❌ Installation timeout or network error**  
→ Try again with:
```bash
pip install --default-timeout=100 -r requirements.txt
```

---

## 🧪 Test Cell for the Notebook

You can paste this at the top of your notebook to confirm everything works:
```python
import sys, platform, pandas as pd, matplotlib, numpy as np, yfinance as yf
print("Python:", sys.version)
print("Platform:", platform.platform())
print("pandas:", pd.__version__)
print("matplotlib:", matplotlib.__version__)
print("numpy:", np.__version__)
print("yfinance OK:", hasattr(yf, "download"))
```

---

## 🏁 You’re all set!
Once you can open `lecture_1.ipynb` and run all cells without errors, your setup is complete.  
Bring your laptop to the workshop — we’ll dive right into financial data science!

---

**Repository:** [https://github.com/arthurdhonneur7/TFA-2025-2026](https://github.com/arthurdhonneur7/TFA-2025-2026)
