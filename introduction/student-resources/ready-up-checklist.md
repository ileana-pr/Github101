# ✅ GitHub for Vibe Coders — Pre-Requisite Checklist

> Complete this **before** the session so we can hit the ground running!
> Estimated time: **15–20 minutes**

---

## What You Need

### 1. 🐙 A GitHub Account

Create your account at **[github.com](https://github.com)** before the session:
1. Click **Sign up**
2. Choose a professional username — `firstname-lastname` works great. This will be your portfolio URL someday.
3. **Verify your email address** — check spam if you don't see it within a minute
4. You're in!

> [!IMPORTANT]
> Use an email you can access during the session. You'll need the same email address when we configure Git in class.

---

### 2. 📧 That Same Email Address
- Keep a note of which email you used for GitHub
- You'll use it in class to configure Git — this is how your commits get linked to your profile

---

### 3. 💻 A Way to Run Commands (pick one)

You only need **one** of the following — whichever feels most comfortable:

#### Option A — AI-First IDE *(recommended for vibe coders)*
Pick any one — they all have a built-in terminal and work great with Git:

| IDE | Download | Notes |
|---|---|---|
| **Cursor** | [cursor.com](https://cursor.com) | Most popular AI IDE — built-in terminal + AI |
| **Windsurf** | [codeium.com/windsurf](https://codeium.com/windsurf) | Strong Cursor alternative, generous free tier |
| **PearAI** | [trypear.ai](https://trypear.ai) | Open source AI IDE |

> [!NOTE]
> **Also using Claude Code?** That works too — it runs in your terminal alongside any IDE above. Install it with `npm install -g @anthropic-ai/claude-code` and run `claude` from inside your project folder.

#### Option B — Any Terminal / CLI
- **Mac:** Terminal (built-in) or iTerm2
- **Windows:** Git Bash (recommended — installed with Git) or Windows Terminal
- **Linux:** Any terminal emulator

> [!NOTE]
> You only need one of the above. If you're already comfortable in a terminal, you don't need an IDE at all.

---

### 4. ⚙️ Git Installed

Git is the engine that GitHub is built on — you need it for everything we'll do in the terminal.

**Step 1 — Check if you already have it:**
```bash
git --version
```
If you see a version number like `git version 2.49.0`, **you're done — Git is already installed!**

---

**Step 2 — Install Git (if needed):**

#### 🍎 Mac
Run this in Terminal:
```bash
git --version
```
If Git isn't installed, macOS will automatically pop up a prompt to install **Xcode Command Line Tools** — click Install and wait. This takes a few minutes but handles everything automatically.

Alternatively, install via Homebrew if you have it:
```bash
brew install git
```

#### 🪟 Windows
- Download the installer from **[git-scm.com](https://git-scm.com)**
- Before opening it: right-click the `.exe` → **Properties** → check **Unblock** → Apply (avoids a common Windows security error)
- Run as administrator — when in doubt, use the default options **except for these two:**
  - "Default editor": change from Vim → **your IDE of choice** (Cursor, Windsurf, Nano, etc.)
  - "Adjusting PATH": select **"Git from the command line and also from 3rd-party software"** (middle option)
- After install, open **Git Bash** (installed alongside Git) — this gives you a Unix-style terminal on Windows that matches what the instructor uses

#### 🐧 Linux
```bash
# Ubuntu / Debian
sudo apt update && sudo apt install git

# Fedora
sudo dnf install git

# Arch
sudo pacman -S git
```

> [!NOTE]
> **Git configuration** (linking your name and email to Git) will be done together in class right after account setup — no need to do it now.

## ✅ You're Ready If...

- [ ] GitHub account created and email verified
- [ ] You have an IDE or terminal ready (Cursor, Windsurf, PearAI, or any terminal)
- [ ] Running `git --version` returns a version number

---

## ❓ Common Pre-Req Issues

| Problem | Fix |
|---|---|
| `git` not found | Install from git-scm.com (Windows) or run `git` in Mac Terminal to trigger install |
| Windows installer won't open | Right-click → Properties → check **Unblock** → Apply, then run as administrator |



---

*If you run into issues, drop a message in Discord before the session starts!*

*Made for: GitHub for Vibe Coders Workshop by [@adigitaltati](https://x.com/adigitaltati)*
