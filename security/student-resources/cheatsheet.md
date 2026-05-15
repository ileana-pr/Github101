# 🔐 GitHub Security for Vibe Coders — Cheatsheet

> Keep this open during the session. Every command the instructor runs will be here.

---

## 🚫 `.gitignore` — Keeping Files Out of Git (Segment 2)

```bash
# Create a .gitignore in your project root
touch .gitignore
```

**Standard entries to include:**
```gitignore
# Secrets — NEVER commit these
.env
.env.local
.env.*.local

# Dependencies — always regeneratable
node_modules/

# Build output
dist/
build/
.next/

# OS & IDE junk
.DS_Store
Thumbs.db
.vscode/settings.json

# Logs
*.log
```

**Already committed a file by mistake?**
```bash
# Remove from git tracking WITHOUT deleting the file locally
git rm --cached .env
git commit -m "Remove .env from tracking"
# Then make sure .env is in your .gitignore!
```

> [!TIP]
> Use [gitignore.io](https://gitignore.io) — type your stack (Node, Python, macOS, etc.) and it generates a complete `.gitignore` for you.

---

## 🔑 `.env` Files & API Keys (Segment 3)

**Create your `.env`:**
```bash
touch .env       # your real secrets — NEVER commit
touch .env.example  # safe template — DO commit
```

**`.env` file format:**
```env
# .env — never commit this!
OPENAI_API_KEY=sk-abc123...
DATABASE_URL=postgresql://user:pass@localhost:5432/mydb
STRIPE_SECRET_KEY=sk_live_...
```

**`.env.example` — safe to commit:**
```env
# .env.example — commit this, no real values
OPENAI_API_KEY=your_openai_key_here
DATABASE_URL=your_database_url_here
STRIPE_SECRET_KEY=your_stripe_key_here
```

**Confirm your `.env` is ignored:**
```bash
git status
# .env should NOT appear in the list
```

---

## 🔐 SSH Keys & PATs (Segment 4)

**View your SSH keys:**
```bash
ls ~/.ssh
# id_ed25519      ← private key — NEVER share or commit
# id_ed25519.pub  ← public key — this is what GitHub has
```

**Generate a key with a passphrase (recommended for shared machines):**
```bash
ssh-keygen -t ed25519 -C "your@email.com"
# Enter a passphrase when prompted
```

**Revoke an SSH key:** GitHub → Settings → SSH and GPG keys → Delete

**Personal Access Tokens (PATs):**
- GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens
- Always set an expiry (90 days max recommended)
- Store in `.env` or a password manager — **never in code**

---

## 🔥 "I Pushed a Secret" — Recovery Steps (Segment 5)

### Step 1 — Revoke the secret FIRST (before anything else)
Go to the provider's dashboard and invalidate the exposed key immediately.

### Step 2A — If it was your last commit and not pushed yet:
```bash
git reset HEAD~1
# Edit out the secret or delete the file
# Add the file to .gitignore
git add .
git commit -m "Remove accidental secret"
```

### Step 2B — If it was already pushed (rewrite history):
```bash
# Install git-filter-repo (one-time)
pip install git-filter-repo

# Remove the file from ALL of history
git filter-repo --path .env --invert-paths

# Force push the cleaned history
git push origin --force --all
```

> [!WARNING]
> Force pushing rewrites public history. Tell collaborators first — they'll need to re-clone.

### What NOT to Do
- ❌ Don't just delete the file — it's still in git history
- ❌ Don't make the repo private and hope for the best
- ❌ Don't ignore it — compromised keys get abused fast

---

## 🛡️ Hardening Your Account (Segment 6)

**Enable 2FA:**
GitHub → Settings → Password and authentication → Enable two-factor authentication

**Audit OAuth apps:**
GitHub → Settings → Applications → Authorized OAuth Apps → Revoke anything you don't use

**Audit SSH keys:**
GitHub → Settings → SSH and GPG keys → Delete keys from old/unused machines

**Check for vulnerabilities in dependencies:**
```bash
npm audit
# Lists known vulnerabilities in your node_modules
```

**Enable Dependabot:**
Repo → Settings → Security → Code security and analysis → Enable Dependabot alerts

---

## ✅ Your End-of-Session Security Checklist

- [ ] `.gitignore` is set up and includes `.env`
- [ ] Secrets live in `.env`, never in code
- [ ] `.env.example` exists for collaborators
- [ ] SSH private key is never committed or shared
- [ ] 2FA is enabled on GitHub
- [ ] You know what to do if you push a secret
- [ ] OAuth apps reviewed and cleaned up

---

## 🚀 Resources

| Resource | What It Is |
|---|---|
| [gitignore.io](https://gitignore.io) | Generate `.gitignore` for any stack |
| [GitHub Secret Scanning Docs](https://docs.github.com/en/code-security/secret-scanning) | GitHub's automatic secret detection |
| [BFG Repo Cleaner](https://rtyley.github.io/bfg-repo-cleaner/) | Easier alternative to `git filter-repo` |
| [Have I Been Pwned](https://haveibeenpwned.com) | Check if your email was in a data breach |
| [Bitwarden](https://bitwarden.com) | Free, open source password manager |

---

*Made for: GitHub Security for Vibe Coders Workshop by [@adigitaltati](https://x.com/adigitaltati)*
