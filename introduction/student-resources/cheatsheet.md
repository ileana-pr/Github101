# 🐙 GitHub for Vibe Coders — Participant Cheatsheet

> Keep this open on a second screen or tab during the session.
> All commands the instructor runs will appear here.

---

## ⚙️ Git Config — Who Are You? (Segment 2)

Run these once to link your identity to your commits. Use the same email as your GitHub account.

```bash
git config --global user.name "Your Name"
git config --global user.email "your-github-email@example.com"

# Verify it worked
git config --global --list
# Should show your name and email
```

---

## 🔑 Authentication — SSH Key Setup (Segment 3)

```bash
# Step 1: Check if you already have a key
ls ~/.ssh
# If you see id_ed25519 or id_rsa, skip to Step 3

# Step 2: Generate a new key
ssh-keygen -t ed25519 -C "your@email.com"
# Press Enter at every prompt (no passphrase needed for personal machines)

# Step 3: Copy your public key
cat ~/.ssh/id_ed25519.pub
# Select all the output and copy it
```

**Step 4 — Add to GitHub:**
```
GitHub → Settings → SSH and GPG keys → New SSH key
→ Paste your key → Add SSH key
```

**Step 5 — Test it:**
```bash
ssh -T git@github.com
# Success looks like:
# Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access.
# (The 'no shell access' part is normal — it means it worked! ✅)
```

> **Stuck on SSH?** Ask in the session chat — the instructor will help you sort it out.

> [!IMPORTANT]
> When cloning, always use the **SSH** URL (not HTTPS!):
> - ✅ SSH: `git clone git@github.com:USERNAME/REPO.git`
> - ❌ HTTPS: `git clone https://github.com/USERNAME/REPO.git`
> Click the green **Code** button on GitHub and select the **SSH** tab.

---

## 📁 The Core Workflow

```bash
# 1. Clone a repo (download it to your computer)
git clone git@github.com:USERNAME/REPO-NAME.git

# 2. Navigate into it
cd REPO-NAME

# 3. Check what changed
git status

# 4. Stage your changes
git add .

# 5. Take a snapshot (commit)
git commit -m "Your message here"

# 6. Send it to GitHub
git push

# 7. Get the latest changes (always pull before you push!)
git pull
```

---

## 🏠 Create a Repo (GitHub → Local)

1. GitHub.com → click **+** → **New repository**
2. Name it, check **Add a README file**, set to **Public**
3. Click **Create repository**
4. Clone it using the SSH URL: `git clone git@github.com:YOUR-USERNAME/REPO-NAME.git`

---

## 🗂️ Connect a Local Project to GitHub (`git init`)

> Use this when you already have a folder on your computer and want to put it on GitHub.

```bash
# Step 1 — Initialize Git in your local folder
cd your-project-folder
git init

# Step 2 — Create a new repo on GitHub.com
# ⚠️ Do NOT check "Add a README file" — your local files are the source of truth

# Step 3 — Connect and push
git remote add origin git@github.com:YOUR-USERNAME/REPO-NAME.git
git branch -M main
git add .
git commit -m "first commit"
git push -u origin main
# After this first push, plain `git push` works with no flags
```

---

## 🌍 Contribute to Open Source

```bash
# After forking a repo on GitHub.com:

# 1. Clone YOUR fork (SSH URL)
git clone git@github.com:YOUR-USERNAME/REPO-NAME.git
cd REPO-NAME

# 2. Create a branch
git checkout -b my-change

# 3. Make your edits, then:
git add .
git commit -m "Describe what you changed"
git push origin my-change

# 4. Go to GitHub → click "Compare & pull request" → Submit!
```

---

## 📖 Key Vocab

| Word | Meaning |
|---|---|
| **repo** | A project folder on GitHub |
| **clone** | Download a repo to your computer |
| **commit** | Save a snapshot of your work |
| **push** | Send your commits to GitHub |
| **pull** | Download the latest changes |
| **branch** | A safe copy to experiment in |
| **fork** | Your personal copy of someone else's repo |
| **pull request (PR)** | Proposing your changes to a project |
| **main** | The official version of a project |
| **merge** | Combining changes into the main version |

---

## 🚑 Something Broke?

| Error | Fix |
|---|---|
| `Permission denied (publickey)` | SSH key not added to GitHub yet — check Settings → SSH keys |
| `ssh-keygen` not found (Windows) | Open Git Bash, not PowerShell |
| Already have `id_rsa` not `id_ed25519` | Works fine! Use `cat ~/.ssh/id_rsa.pub` instead |
| `failed to push some refs` | Run `git pull` first, then `git push` |
| `nothing to commit` | Did you **save** the file in your editor? |
| `not a git repository` | `cd` into your cloned folder first |
| Used HTTPS URL instead of SSH | Update remote: `git remote set-url origin git@github.com:USER/REPO.git` |

---

## 🚀 What's Next?

| Resource | What It Is |
|---|---|
| [skills.github.com](https://skills.github.com) | Free interactive GitHub courses |
| [ohmygit.org](https://ohmygit.org) | Learn Git through a game |
| [github.com/firstcontributions/first-contributions](https://github.com/firstcontributions/first-contributions) | Safe place to practice your first PR |
| [theodinproject.com](https://www.theodinproject.com) | Full beginner dev curriculum |

---

*Made for: GitHub for Vibe Coders Workshop by [@adigitaltati](https://x.com/adigitaltati)*
