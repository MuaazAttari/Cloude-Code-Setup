Bhai yeh lo **complete video–ready notes** — bilkul structured, clean, step-by-step, jese tum apni video me use kar sakte ho.
Isme:

✔ Required cheezon ki list
✔ Check commands
✔ Install status ke outputs
✔ Full setup guide (Windows)
✔ Comments ready for video narration

Ye content seedha video script ke notes ban jayega.

---

# 🎥 **CLAUDE-CODE + GEMINI COMPLETE WINDOWS SETUP (VIDEO NOTES)**

*Best for YouTube explanation + students + training.*

---

# ▓ REQUIREMENTS (TOTAL: 6 CHEEZAY)

### **1) Node.js (18+ required)**

### **2) Google Gemini API Key**

### **3) Git Bash (Windows shell)**

### **4) Claude-Code (CLI Tool)**

### **5) Claude-Code-Router (ccr)**

### **6) Environment Variables (API Key + Bash Path)**

---

# ▓ REQUIREMENTS CHECK (BEFORE INSTALLATION)

Ye commands video me run karke check dikhana.

---

## ✅ **1) Check Node.js**

Command:

```
node --version
```

**Installed ho to output:**

```
v18.x.x  (ya koi 20+ version)
```

**Agar installed NA ho to:**

```
node: command not found
```

✔ Solution: [https://nodejs.org](https://nodejs.org) se install.

---

## ✅ **2) Check Git Bash**

Command:

```
where bash
```

**Installed ho to output:**

```
C:\Program Files\Git\bin\bash.exe
```

**Agar installed NA ho to:**

```
INFO: Could not find files
```

✔ Solution: Install Git Bash from:
[https://git-scm.com/download/win](https://git-scm.com/download/win)

---

## ✅ **3) Check Claude-Code**

Command:

```
claude --version
```

**Installed ho to:**

```
claude-code version x.x.x
```

**Agar NA ho to:**

```
claude: command not found
```

---

## ✅ **4) Check Claude-Code-Router (ccr)**

Command:

```
ccr version
```

**Installed ho to:**

```
ccr version x.x.x
```

**Agar NA ho to:**

```
ccr: command not found
```

---

## ✅ **5) Check Environment Variable (Google API Key)**

Command:

```
echo $env:GOOGLE_API_KEY
```

**Agar set ho to:**

```
AIzaSyxxxx...  (your API key)
```

**Agar NA ho to:**
(empty line)

---

## ✅ **6) Check Bash Path Variable**

Command:

```
echo $env:CLAUDE_CODE_GIT_BASH_PATH
```

**Set ho to:**

```
C:\Program Files\Git\bin\bash.exe
```

**Agar NA ho to:**
(empty)

---

# ▓ FULL SETUP GUIDE (WINDOWS) — STEP BY STEP

*Yeh part video me clearly, slowly explain karna.*

---

# 🔥 STEP 0 — Install Node.js

Site: [https://nodejs.org](https://nodejs.org)
Download **LTS (18+)** version → Install.

Check:

```
node --version
```

---

# 🔥 STEP 1 — Get Gemini API Key

1. Open: [https://aistudio.google.com](https://aistudio.google.com)
2. Left Menu → **Get API Key**
3. **Create API Key**
4. Copy the key (e.g.)

```
AIzaSyXXXX...
```

---

# 🔥 STEP 2 — Install Required Tools

PowerShell **(Run as Administrator)**:

```
npm install -g @anthropic-ai/claude-code @musistudio/claude-code-router
```

---

# 🔥 STEP 3 — Create Config Folders

PowerShell (normal):

```
mkdir $HOME/.claude-code-router
mkdir $HOME/.claude
```

---

# 🔥 STEP 4 — Create config.json

Windows me cat command nahi chalti → Notepad method use karein.

Run:

```
notepad $HOME/.claude-code-router/config.json
```

Paste the following JSON:

```json
{
  "LOG": true,
  "LOG_LEVEL": "info",
  "HOST": "127.0.0.1",
  "PORT": 3456,
  "API_TIMEOUT_MS": 600000,
  "Providers": [
    {
      "name": "gemini",
      "api_base_url": "https://generativelanguage.googleapis.com/v1beta/models/",
      "api_key": "$GOOGLE_API_KEY",
      "models": [
        "gemini-2.5-flash",
        "gemini-2.0-flash"
      ],
      "transformer": {
        "use": ["gemini"]
      }
    }
  ],
  "Router": {
    "default": "gemini,gemini-2.5-flash",
    "background": "gemini,gemini-2.5-flash",
    "think": "gemini,gemini-2.5-flash",
    "longContext": "gemini,gemini-2.5-flash",
    "longContextThreshold": 60000
  }
}
```

Save → Close.

---

# 🔥 STEP 5 — Set API Key (Windows method)

PowerShell (Admin):

```
[System.Environment]::SetEnvironmentVariable('GOOGLE_API_KEY', 'YOUR_KEY_HERE', 'User')
```

Example:

```
[System.Environment]::SetEnvironmentVariable('GOOGLE_API_KEY', 'AIzaSyXXXX...', 'User')
```

Restart PowerShell → test:

```
echo $env:GOOGLE_API_KEY
```

---

# 🔥 STEP 6 — Set Git Bash Path

If Git Bash installed at:

```
C:\Program Files\Git\bin\bash.exe
```

Then set:

```
[System.Environment]::SetEnvironmentVariable('CLAUDE_CODE_GIT_BASH_PATH', 'C:\Program Files\Git\bin\bash.exe', 'User')
```

Restart PowerShell → test:

```
echo $env:CLAUDE_CODE_GIT_BASH_PATH
```

---

# 🔥 STEP 7 — Verify Everything

Run:

```
claude --version
ccr version
echo $env:GOOGLE_API_KEY
echo $env:CLAUDE_CODE_GIT_BASH_PATH
```

Agar chaaron ka output aaya → setup done! ✔

---

# 🔥 STEP 8 — RUN THE ROUTER (backend)

Terminal 1:

```
ccr start
```

Wait until:

```
✔ Service started successfully
```

---

# 🔥 STEP 9 — RUN CLAUDE CODE (frontend)

Terminal 2:

```
ccr code
```

Or:

```
eval "$(ccr activate)"
claude
```

---

# 🎉 FINAL TEST

In Claude terminal type:

```
hi
```

Agar reply aaye →
**Congratulations! Claude Code + Gemini working FREE!!**

---

# 💡 If you want I can also make:

✔ A short version
✔ Thumbnail text
✔ Script for your speaking
✔ On-screen text list
✔ Full PDF notes for download

Just tell me bhai.
