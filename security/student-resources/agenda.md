# 🔐 GitHub Security for Vibe Coders — Course Agenda

**Format:** Live Zoom session | **Duration:** ~60 minutes
**Instructor:** [@adigitaltati](https://x.com/adigitaltati)

---

## 🎯 What You'll Be Able to Do After This Session

By the end of today you will:
- ✅ Know exactly what to put in `.gitignore` and why
- ✅ Understand how to keep API keys and secrets out of your code with `.env`
- ✅ Know the difference between SSH keys and Personal Access Tokens — and when to use each
- ✅ Know the exact steps to take if you accidentally push a secret
- ✅ Have 2FA enabled and your GitHub account hardened

No secret will ever end up in your code again.

---

## 📋 Session Outline

| # | Topic | Time |
|---|---|---|
| 1 | **Why this matters** — real stories of what goes wrong | 5 min |
| 2 | **`.gitignore`** — what Git should never see | 10 min |
| 3 | **`.env` files & API keys** — where secrets live safely | 10 min |
| 4 | **SSH keys & PATs** — a deeper look at authentication | 10 min |
| 5 | **"I pushed a secret"** — the recovery drill | 10 min |
| 6 | **Hardening your account** — 2FA, OAuth apps, key audits | 10 min |
| 7 | **Wrap-up** — your security checklist & resources | 5 min |

---

## 🧰 What to Have Ready

- ✔️ Completed the [pre-req checklist](./prereq_checklist.md)
- ✔️ This agenda open on one screen
- ✔️ The [security cheatsheet](./cheatsheet.md) open on another tab

---

## 💬 Key Vocab We'll Cover

| Term | Plain English |
|---|---|
| **.gitignore** | A file that tells Git which files to never track or commit |
| **.env** | A file where your secret keys and config live — never committed |
| **API key** | A secret token that proves you have permission to use a service |
| **Personal Access Token (PAT)** | A GitHub-issued token used instead of a password |
| **2FA** | Two-factor authentication — a second step to verify it's really you |
| **OAuth app** | A third-party app you've given access to your GitHub account |
| **git filter-repo** | A tool to rewrite git history and remove secrets permanently |
| **Dependabot** | GitHub's bot that alerts you to security vulnerabilities in your dependencies |

---

## 🚀 After the Session

- Enable Dependabot on all your active repos
- Audit your third-party OAuth apps at github.com/settings/applications
- Share your `.env.example` pattern with collaborators
- Set up a password manager if you haven't yet ([Bitwarden](https://bitwarden.com) is free)

---

*GitHub Security for Vibe Coders by [@adigitaltati](https://x.com/adigitaltati)*
