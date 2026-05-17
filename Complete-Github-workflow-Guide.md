# 🚀 GitHub Company Workflow — Complete Beginner Guide
### *Ek Company Kaise Chalati Hai GitHub Par — Zero se Hero tak*

> **Audience:** Bilkul naye log jo Git/GitHub seekh rahe hain aur apni team ke saath project manage karna chahte hain  
> **Level:** Absolute Beginner → Professional  
> **Language:** Hinglish (Simple aur seedha)

---

## 📋 Table of Contents

1. [Git aur GitHub kya hai?](#1-git-aur-github-kya-hai)
2. [GitHub Account Banana](#2-github-account-banana)
3. [Git Install aur First Time Setup](#3-git-install-aur-first-time-setup)
4. [Push Fail Hua? HTTPS aur SSH Fix](#4-push-fail-hua-https-aur-ssh-fix)
5. [Big Picture — Poora System Ek Nazar Mein](#5-big-picture)
6. [Branch Kya Hota Hai?](#6-branch-kya-hota-hai)
7. [.gitignore — Ye Files Mat Bhejo GitHub Par](#7-gitignore--ye-files-mat-bhejo-github-par)
8. [Project Setup — Owner Shuru Karta Hai](#8-project-setup)
9. [Employee ka Daily Workflow](#9-employee-daily-workflow)
10. [Feature Complete — PR aur Merge](#10-feature-complete--pr-aur-merge)
11. [GitHub Issues — Task Tracking](#11-github-issues--task-tracking)
12. ["Aage Peeche" Problem aur Conflicts](#12-aage-peeche-problem-aur-conflicts)
13. [Hotfix — Emergency Bug](#13-hotfix--emergency-bug)
14. [Real Scenario — Teen Logon Wali Team](#14-real-scenario)
15. [Commands Cheat Sheet](#15-commands-cheat-sheet)
16. [Company Rules](#16-company-rules)

---

## 1. Git aur GitHub kya hai?

### Git — Local Tool (Teri Machine Par)

Git ek **version control system** hai. Simple bhasha mein:

> Git ek magical **"Save History"** button hai jo teri files ka poora history rakhta hai. Kabhi bhi kisi bhi purani state mein wapas ja sakta hai.

```
Bina Git ke:
  project_final.zip
  project_final_v2.zip
  project_FINAL_USE_THIS.zip
  project_FINAL_REAL_THIS_ONE.zip   ← 😩

Git ke saath:
  project/   ← Ek hi folder, Git sab history track karta hai ✅
```

### GitHub — Cloud Website (Online)

GitHub ek **website** hai jahan tu apna Git project online store karta hai.

```
Git    = Teri local hard drive ka system
GitHub = Google Drive jaise — online backup + team sharing
```

**Analogy:**
- Git = Ghar mein likhi dairy (local)
- GitHub = Wahi dairy Google Docs par upload (online, sab dekh sakte hain)

---

## 2. GitHub Account Banana

**Sirf ek baar karna hai — employee aur owner dono ke liye.**

1. **https://github.com** par jao
2. **"Sign up"** button click karo
3. Fill karo:
   - Email address
   - Password (strong rakho)
   - Username — **ye important hai**, yahi tera GitHub identity hoga  
     Example: `tarun-mankar` ya `tarundev`
4. Free plan choose karo — bilkul sufficient hai
5. Email verify karo

### Username Kaisa Rakho

```
✅ tarun-mankar       (naam + surname)
✅ tarundev           (naam + profession)
✅ tarun-ai           (tera brand)

❌ xXx_coder_xXx      (unprofessional)
❌ user123456         (random, yaad nahi rahega)
```

> 💡 **Kyun sochna chahiye:** GitHub username tera developer identity hai. Clients, teammates, future employers — sab yehi dekhen ge. Professional rakho.

---

## 3. Git Install aur First Time Setup

### Git Install Karo

- **Windows:** https://git-scm.com/download/win → Download karo, Next-Next-Finish
- **Mac:** Terminal mein `git --version` type karo → Automatically install offer karega
- **Linux:** `sudo apt install git`

Verify karo:
```bash
git --version
# OUTPUT: git version 2.x.x  ← Dikha diya to install ho gaya ✅
```

### Pehli Baar Setup — Apna Naam aur Email Dalo

**Ye SABSE PEHLE karo** — sirf ek baar karna padta hai:

```bash
git config --global user.name "Tarun Mankar"
git config --global user.email "tarun@example.com"

# Verify karo
git config --list
# OUTPUT mein user.name aur user.email dikhai dega ✅
```

> ⚠️ **Kyun zaroori hai:** Har commit par tera naam aur email stamp hota hai — pata chale kaun ne kya kiya.

---

## 4. Push Fail Hua? HTTPS aur SSH Fix

Jab pehli baar `git push` karo, aksar ye problems aati hain:

### Problem 1 — Username/Password Maang Raha Hai

```bash
git push origin main
# Username for 'https://github.com': 
# Password for 'https://...':        ← Password dala aur ERROR! 😩
# remote: Support for password authentication was removed.
```

**GitHub ne 2021 mein password login band kar diya.** Ab do options hain:

---

### Option A — Personal Access Token (PAT) — Asaan

1. GitHub → Top right avatar → **Settings**
2. Left sidebar bottom → **Developer settings**
3. **Personal access tokens** → **Tokens (classic)**
4. **"Generate new token (classic)"**
5. Note: `my-git-token`
6. Expiration: `90 days` ya `No expiration`
7. Scopes mein ✅ **repo** check karo
8. **"Generate token"** → **Token copy karo (ek baar hi dikhta hai!)**

Ab push karo:
```bash
git push origin main
# Username: TERA_GITHUB_USERNAME
# Password: WAHI_TOKEN_PASTE_KARO  ← Password ki jagah token daalo
```

> 💡 **Token save karo** — Notepad mein ya password manager mein. Dobara nahi milega.

---

### Option B — SSH Key (Ek Baar Setup, Phir Kabhi Password Nahi)

```bash
# Step 1: SSH key banao
ssh-keygen -t ed25519 -C "tarun@example.com"
# Enter dabao 3 baar (default settings theek hain)

# Step 2: Key copy karo
# Windows:
type %USERPROFILE%\.ssh\id_ed25519.pub
# Mac/Linux:
cat ~/.ssh/id_ed25519.pub
# OUTPUT: ssh-ed25519 AAAA... tarun@example.com  ← Ye poora copy karo

# Step 3: GitHub par add karo
# GitHub → Settings → SSH and GPG keys → "New SSH key"
# Title: "Mera Laptop"
# Key: paste karo
# "Add SSH key" click karo

# Step 4: Test karo
ssh -T git@github.com
# OUTPUT: Hi tarun-mankar! You've successfully authenticated ✅

# Step 5: Remote URL change karo (HTTPS → SSH)
git remote set-url origin git@github.com:TERA_USERNAME/REPO_NAME.git
```

Ab se kabhi password nahi maangega. ✅

---

### Problem 2 — Permission Denied

```bash
git push origin main
# ERROR: Permission to USER/REPO.git denied to TERA_USERNAME
```

**Matlab:** Tu is repo ka collaborator nahi hai. Owner se add karwao (Settings → Collaborators).

---

## 5. Big Picture

Pehle poora picture samjho, phir details mein jao.

### Sochlo Ek Film Ki Shooting Jaise

```
main     → Released movie (Jo cinema mein chal rahi hai — Live app/website)
develop  → Editing room (Post-production chal rahi hai — Testing)
feature  → Alag alag scenes shoot karna (Har feature = ek scene)
```

### Seedha Flow — Kaise Kaam Hota Hai

```
                    ┌─────────────────────────────────────────┐
                    │                                         │
feature/login ──────┤                                         │
                    ├──────────────────► develop ────────────► main
feature/payment ────┤     (PR + Review)             (Release)  │
                    │                                         │
feature/dashboard ──┘                                         │
                                                              │
hotfix/bug ───────────────────────────────────────────────────┘
                                              (Direct emergency fix)
```

### Simple Rules

| Kya | Kahan Jata Hai |
|-----|----------------|
| Naya feature | feature branch → develop |
| Tested develop | develop → main |
| Emergency live bug | hotfix branch → main + develop |
| **Main mein direct push** | **❌ KABHI NAHI** |

---

## 6. Branch Kya Hota Hai?

### Branch = Alag Kopy Jahan Tu Experiment Kar Sakta Hai

```
Imagine karo ek Google Doc hai:
  ─ Original doc (main)
  ─ "Duplicate kar ke alag version mein edit karo" (branch)
  ─ Jab ready ho tab original mein merge karo (merge)
  ─ Agar bakwaas nikla to duplicate delete karo — original safe hai
```

### Real Example

```bash
# Ek project hai: e-commerce website
main                  → Live website (customers use kar rahe hain)
develop               → Staging (test ho raha hai)
feature/user-login    → Rahul sirf login feature bana raha hai
feature/payment       → Priya sirf payment bana rahi hai
feature/dashboard     → Amit sirf dashboard bana raha hai
```

**Key point:** Rahul ka kaam Priya ke kaam ko affect nahi karta — dono alag-alag branches mein hain. 🎯

### Branch Types — Kaun Sa Kab Use Karo

| Branch | Use | Direct Push? |
|--------|-----|-------------|
| `main` | Live production — customers yahan hain | ❌ Never |
| `develop` | Testing — stable but not live | ❌ Only via PR |
| `feature/xyz` | Ek feature ka kaam | ✅ Haan, apna branch hai |
| `bugfix/xyz` | Non-urgent bug fix | ✅ Haan |
| `hotfix/xyz` | URGENT — live mein kuch toot gaya | ✅ Haan, then PR fast |
| `release/v1.2` | Release prepare karna | ❌ Only via PR |

### Branch Naming Convention — Naam Kaise Rakho

```bash
feature/user-login          # feature/kya-bana-rahe-ho
feature/payment-gateway
feature/email-notifications

bugfix/login-button-broken   # bugfix/kya-tha-problem
bugfix/cart-total-wrong

hotfix/app-crash-on-startup  # hotfix/emergency-kya-hai

release/v1.0.0               # release/version
release/v2.3.1
```

> 💡 **Rule:** Sirf lowercase, hyphens use karo — spaces aur capitals mat rakho.

---

## 7. .gitignore — Ye Files Mat Bhejo GitHub Par

### .gitignore Kya Hai?

Ek special file jo Git ko bolta hai — **"Ye files track mat karo, GitHub par mat bhejo."**

### Kyun Zaroori Hai?

```bash
# Bina .gitignore ke ye sab GitHub par chala jaata hai:
node_modules/       ← 50,000+ files, 200MB+ — bilkul zaroori nahi
.env                ← SECRET KEYS, PASSWORDS — KABHI NAHI bhejo!
.DS_Store           ← Mac ki system file — kisi kaam ki nahi
dist/               ← Build files — auto-generate hoti hain
*.log               ← Log files — useful nahi
```

> 🔴 **CRITICAL:** `.env` file mein API keys, database passwords hote hain. Agar GitHub par chali gayi — **IMMEDIATELY keys change karo.** Bots scan karte hain publicly.

### .gitignore Kaise Banao

Project root mein `.gitignore` file banao:

```bash
# Terminal mein:
touch .gitignore   # Mac/Linux
# Windows: Notepad se banao, naam ".gitignore" rakho (koi extension nahi)
```

**Node.js project ke liye:**

```
# .gitignore file ka content:

# Dependencies
node_modules/

# Environment variables (SECRET!)
.env
.env.local
.env.production

# Build output
dist/
build/

# OS files
.DS_Store         # Mac
Thumbs.db         # Windows

# Logs
*.log
npm-debug.log*

# Editor files
.vscode/
.idea/
```

**Python project ke liye:**

```
__pycache__/
*.pyc
venv/
.env
dist/
*.egg-info/
```

### Shortcut — GitHub Khud Banata Hai

Naya repo banate waqt:
- **"Add .gitignore"** dropdown → Apni language choose karo (Node, Python, etc.)
- GitHub automatically sahi `.gitignore` bana deta hai ✅

### Agar Galti Se Commit Ho Gayi

```bash
# File ko tracking se hatao (file delete nahi hogi)
git rm --cached .env
git rm --cached -r node_modules/

# .gitignore mein add karo
echo ".env" >> .gitignore
echo "node_modules/" >> .gitignore

git add .
git commit -m "Remove accidentally tracked files, add to gitignore"
git push origin main
```

---

## 8. Project Setup

### Step 1 — GitHub Par Repo Banao (Owner)

1. github.com par jao → Login karo
2. **"New repository"** button click karo
3. Name daalo: `my-awesome-project`
4. **Private** ya **Public** choose karo
5. ✅ "Add a README file" check karo
6. **"Create repository"** click karo

### Step 2 — Local Mein Clone Karo

**Clone = GitHub se apni machine par copy laana**

```bash
# Terminal/Command Prompt kholao
# Jahan project rakhna hai wahan jao (example: Desktop)
cd Desktop

# Clone karo
git clone https://github.com/TERA_USERNAME/my-awesome-project.git

# Folder mein jao
cd my-awesome-project

# Check karo kya hai andar
ls        # Mac/Linux
dir       # Windows
```

> 💡 **Clone URL kahan se milega:** GitHub → Repository → Green "Code" button → HTTPS URL copy karo

### Step 3 — Develop Branch Banao

```bash
# Pehle main par ho — confirm karo
git branch
# OUTPUT: * main  ← Star = current branch

# develop branch banao
git checkout -b develop

# GitHub par push karo (ye branch online bhi banegi)
git push origin develop

# Verify karo
git branch
# OUTPUT:
# * develop   ← Ab develop par hai
#   main
```

### Step 4 — Branch Protection Lagao (IMPORTANT)

GitHub par settings se koi bhi galti se main mein push na kar sake:

1. GitHub → Repository → **Settings** tab
2. Left sidebar → **Branches**
3. **"Add branch ruleset"** ya **"Add rule"** click karo
4. Branch name: `main`
5. In boxes ko check karo:
   - ✅ **Require a pull request before merging**
   - ✅ **Require approvals** → Minimum: `1`
6. Save karo

Yahi process `develop` ke liye bhi karo.

> 🔒 **Ab kya hoga:** Koi bhi — including owner — directly `main` mein push nahi kar sakta. Sirf PR se hi ho sakta hai.

### Step 5 — Employees Ko Access Do

1. GitHub → Repository → **Settings**
2. Left sidebar → **Collaborators**
3. **"Add people"** click karo
4. Employee ka GitHub username ya email daalo
5. Role choose karo:

| Role | Kise Do | Kya Kar Sakta Hai |
|------|---------|-------------------|
| `Write` | Normal developers | Code push, PR banao |
| `Maintain` | Senior dev / Team lead | Settings bhi touch kar sakta hai |
| `Admin` | Sirf owner | Sab kuch |

---

## 9. Employee Daily Workflow

### Pehli Baar — Repo Clone Karo

Employee ko sirf ek baar karna hai:

```bash
git clone https://github.com/OWNER_USERNAME/my-awesome-project.git
cd my-awesome-project
```

### Roz Ka Kaam — Step by Step

#### 🌅 Subah Shuruaat — HAMESHA Ye Karo

```bash
# Step 1: develop branch par jao
git checkout develop

# Step 2: Latest code lo (kaafi important!)
git pull origin develop

# Step 3: Naya feature branch banao
git checkout -b feature/user-login

# Ab kaam shuru karo 👨‍💻
```

> ⚠️ **Bhool gaye to kya hoga:** Purane code par kaam karoge. Jab merge karoge to bohot conflicts aayenge. "Aage peeche" wala problem yehi se shuru hota hai.

#### ☀️ Din Mein — Kaam Karo + Commit Karo

```bash
# Kaam kiya... kuch files banaye/edit kiye

# Kya kya badla dekho
git status
# OUTPUT:
# Changes not staged for commit:
#   modified:   src/login.js
#   modified:   src/auth.js
# Untracked files:
#   src/loginForm.js   ← Nayi file

# Sab files stage karo
git add .

# Ya specific file
git add src/login.js

# Commit karo — snapshot liya!
git commit -m "Add login form UI with email and password fields"
```

#### Good Commit Messages Kaise Likhein

```bash
# ✅ ACHHA — Kya kiya woh clearly bata raha hai
git commit -m "Add user login form with validation"
git commit -m "Fix: login button not working on mobile Safari"
git commit -m "Update: password minimum length changed to 8"
git commit -m "Remove: unused CSS from login page"

# ❌ BURA — Koi idea nahi 2 hafte baad kya kiya tha
git commit -m "fix"
git commit -m "changes"
git commit -m "working now"
git commit -m "asdfgh"
```

**Formula:** `[Kya kiya]: [Kahan kiya/kyun]`

#### 🌆 GitHub Par Save Karo (Push)

```bash
# Din mein baar baar karo — tera kaam online safe rahega
git push origin feature/user-login
```

> 💡 **Push kyun karna chahiye baar baar:**
> - Laptop kharab ho jaye → GitHub par backup hai
> - Owner progress dekh sake
> - Teammates jaan sakein tum kya kar rahe ho

---

## 10. Feature Complete — PR aur Merge

### Pull Request (PR) Kya Hota Hai?

> **PR = "Boss, mera kaam complete ho gaya, check kar lo aur approve karo"**

PR ek formal request hai jisme tu kehta hai:
- "Ye mera code hai"
- "Ye kaam karta hai (mujhe lagta hai)"
- "Please review karo aur develop mein merge karo"

### Merge Karne Ka Process — Step by Step

#### Step 1 — Apna Branch Update Karo

```bash
# Pehle develop ki latest lo
git checkout develop
git pull origin develop

# Apne branch par wapas jao
git checkout feature/user-login

# Develop ki changes apne branch mein laao
git merge develop

# Agar koi conflict nahi aaya:
git push origin feature/user-login
```

#### Step 2 — GitHub Par PR Banao

1. GitHub → Teri Repository → **"Compare & pull request"** button (yellow/green banner)
2. Fill karo:

```
Title:    Feature: User Login System with JWT

Description:
## Kya kiya?
User login functionality add ki — email, password, JWT token.

## Kaise test karein?
1. npm run dev karo
2. http://localhost:3000/login par jao
3. Email: test@test.com, Password: test123
4. Dashboard redirect hona chahiye

## Screenshots
[screenshot lagao yahan]
```

3. **Reviewers** mein owner ya team lead assign karo
4. **Base branch:** `develop` (feature → develop merge hoga)
5. **"Create pull request"** click karo

#### Step 3 — Owner Review Karta Hai

Owner ke 3 options hain:

```
✅ Approve + Merge  →  Feature develop mein aa gaya!
💬 Request Changes  →  "Line 45 mein bug hai, fix karo"
❌ Close            →  "Ye feature abhi nahi chahiye"
```

Agar changes maanga:
```bash
# Fix karo
git add .
git commit -m "Fix: error message improved as per review feedback"
git push origin feature/user-login
# PR automatically update ho jaata hai — dobara PR banane ki zarurat nahi
```

#### Step 4 — Merge Ho Gaya! Clean Up Karo

```bash
# GitHub par "Delete branch" button click karo (PR merge hone ke baad)

# Local mein bhi clean karo
git checkout develop
git pull origin develop          # Latest develop lo (tera feature ab yahan hai)
git branch -d feature/user-login # Local branch delete karo
```

---

## 11. GitHub Issues — Task Tracking

### Issue Kya Hota Hai?

> **Issue = Ek task card** — "Kya kaam karna hai" likhte hain, kisi ko assign karte hain, phir track karte hain.

GitHub Issues ek built-in task manager hai. Jira, Trello ki zarurat nahi — seedha GitHub mein hota hai.

### Issue Kaise Banao (Owner/Team Lead)

1. GitHub → Repository → **"Issues"** tab
2. **"New issue"** click karo
3. Fill karo:
   - **Title:** `Feature: User Login System`
   - **Description:** Detail mein kya chahiye
   - **Assignees:** Rahul ko assign karo
   - **Labels:** `feature` / `bug` / `urgent`
4. **"Submit new issue"** → Issue #23 ban gaya

### Issue → Branch → PR — Sab Link Karo

```bash
# Issue #23 ke liye branch banao
git checkout -b feature/user-login-23   # Number daalo naam mein

# Kaam karo, commit karo
git commit -m "Add login form — refs #23"

# PR description mein likho:
# "Fixes #23"  ← Ye magic words hain!
# PR merge hone par Issue automatically CLOSE ho jaata hai ✅
```

### Labels Use Karo

| Label | Matlab |
|-------|--------|
| `feature` | Naya feature |
| `bug` | Kuch toot gaya |
| `urgent` | Jaldi fix chahiye |
| `in progress` | Kaam chal raha hai |
| `review needed` | PR ready, review karo |
| `blocked` | Kisi cheez ka wait hai |

### Milestones — Release Planning

Issues ko milestone mein group karo:

```
Milestone: v1.0.0 Release
  ✅ Issue #21 — User Login
  ✅ Issue #22 — Dashboard  
  ⏳ Issue #23 — Payment Gateway  ← Pending
  
Progress: 2/3 complete (67%)
```

GitHub → Issues → Milestones → "New milestone" → Issues assign karo.

---

## 12. "Aage Peeche" Problem aur Conflicts

### Samjho — Problem Kab Aata Hai

```
Din 1:
  Rahul:  develop se branch banaya → feature/login
  Priya:  develop se branch banaya → feature/dashboard

Din 3:
  Priya ka feature pehle complete hua → develop mein merge ho gaya
  Ab develop mein Priya ka code hai

Din 5:
  Rahul ka feature complete hua
  Lekin Rahul ke branch mein Priya ka code NAHI hai
  → "Aage peeche" ho gaya! Rahul purane develop par based hai
```

**Visually:**

```
Rahul ka branch:   A─B─C─D─E  (apna code, develop se 3 commits peeche)
                   │
develop:           A─B─C─F─G  (Priya ka code F,G aaya)
                         ↑
                   Rahul yahan tak hai lekin develop aage badh gaya
```

### Solution — Hamesha Sync Karo

```bash
# Rahul ye kare roz subah AUR PR banane se pehle:
git checkout develop
git pull origin develop         # develop latest lo (F, G commits aaye)
git checkout feature/user-login
git merge develop               # Ye commits apne branch mein laao

# Ab Rahul ka branch:
# A─B─C─F─G─D─E   ← Up to date!
```

### Conflict Kab Aata Hai

Agar Rahul aur Priya ne **same file ka same part** badla ho:

```
Rahul:  login.js ki line 45 mein likha "Welcome User"
Priya:  login.js ki line 45 mein likha "Hello Friend"
```

Dono ka develop mein merge hoga → Git confuse → **CONFLICT!**

### Conflict Solve Karna

```bash
git merge develop
# OUTPUT: CONFLICT (content): Merge conflict in src/login.js
# Automatic merge failed; fix conflicts and then commit the result.
```

**File kholne par ye dikhai dega:**

```javascript
<<<<<<< HEAD          ← Yahan se... tera code hai
Welcome User
=======               ← Beech mein line
Hello Friend
>>>>>>> develop       ← ...yahan tak develop ka code hai
```

**Tu decide kar — kya rakhna hai:**

```javascript
// Option 1: Tera code rakh
Welcome User

// Option 2: Unka code rakh
Hello Friend

// Option 3: Dono rakh
Welcome User, Hello Friend!

// Conflict markers (<<<<, ====, >>>>) hataao — ye sirf markers hain
```

**Phir:**

```bash
git add src/login.js
git commit -m "Resolve conflict: keep 'Welcome User' message"
git push origin feature/user-login
```

> 💡 **VS Code Users:** File mein automatically colored buttons aate hain:
> - "Accept Current Change" = Tera code rakh
> - "Accept Incoming Change" = Unka code rakh
> - "Accept Both Changes" = Dono rakh
>
> Manually `<<<<` dhundhne ki zarurat nahi!

### Conflict Avoid Karne Ka Best Practice

```bash
# Roz subah ye 4 commands — bas!
git checkout develop
git pull origin develop
git checkout feature/tera-branch
git merge develop
```

Isse tera branch kabhi zyada peeche nahi padega → Kam conflicts.

---

## 13. Hotfix — Emergency Bug

### Situation: Live Website Mein Kuch Toot Gaya!

```
Raat ke 2 baj rahe hain
User complain kar raha hai ki payment page crash ho rahi hai
Fix ABHI karna hai — develop mein kuch aur half-done kaam pada hai
```

### Hotfix Workflow

```bash
# ⚠️ MAIN se branch banao — develop se nahi!
# (Develop mein incomplete features ho sakte hain)
git checkout main
git pull origin main
git checkout -b hotfix/payment-crash

# Bug fix karo
git add .
git commit -m "Hotfix: fix payment gateway null pointer exception"
git push origin hotfix/payment-crash

# GitHub par PR banao → main mein merge
# (Urgent hai to owner khud merge karta hai)

# Main mein merge hone ke baad:
# Develop mein bhi ye fix laao
git checkout develop
git merge main
git push origin develop

# Branch delete karo
git branch -d hotfix/payment-crash
```

**Flow:**

```
hotfix/payment-crash ──────────────────► main  (Live fix!)
                       │
                       └────────────────► develop  (Future builds mein bhi rahega)
```

---

## 14. Real Scenario

### Team: Tarun (Owner), Rahul, Priya, Amit

**Project: E-Commerce Website**

---

**📅 MONDAY — Tarun Tasks Assign Karta Hai**

```
Rahul  → Feature: User Login System     (feature/user-login)
Priya  → Feature: Product Dashboard     (feature/dashboard)
Amit   → Feature: Payment Gateway       (feature/payment)
```

---

**🌅 TUESDAY MORNING — Sab Shuru Karte Hain**

```bash
# Rahul
git checkout develop && git pull origin develop
git checkout -b feature/user-login

# Priya
git checkout develop && git pull origin develop
git checkout -b feature/dashboard

# Amit
git checkout develop && git pull origin develop
git checkout -b feature/payment
```

---

**☀️ TUESDAY-THURSDAY — Kaam Hota Rahta Hai**

```bash
# Rahul roz commit karta hai
git add . && git commit -m "Add login form"
git add . && git commit -m "Add JWT authentication"
git push origin feature/user-login

# Priya
git add . && git commit -m "Add product list component"
git push origin feature/dashboard
```

---

**🌆 THURSDAY EVENING — Priya Done Pehle**

```bash
# Priya PR banati hai
git checkout develop && git pull origin develop
git checkout feature/dashboard
git merge develop  # Sync karo
git push origin feature/dashboard
# → GitHub par PR: feature/dashboard → develop
```

**Tarun review karta hai → Approve → Merge!**

---

**🌅 FRIDAY MORNING — Rahul Sync Karta Hai**

```bash
# Priya ka code ab develop mein hai
# Rahul ko wo bhi apne branch mein chahiye
git checkout develop
git pull origin develop          # Priya ka code aaya
git checkout feature/user-login
git merge develop                # Rahul ke branch mein bhi aaya
# → Sab sync!
```

---

**🌆 FRIDAY EVENING — Rahul Done**

```bash
git checkout develop && git pull origin develop
git checkout feature/user-login
git merge develop
git push origin feature/user-login
# → PR banaya: feature/user-login → develop
# → Tarun ne review kiya, ek comment: "Error message improve karo"
git add . && git commit -m "Fix: improve login error messages"
git push origin feature/user-login
# → Tarun ne approve kiya → Merge!
```

---

**📦 FRIDAY NIGHT — Weekly Release**

```bash
# Tarun release karta hai
git checkout main
git pull origin main
git merge develop
git push origin main

git tag -a v1.2.0 -m "Release: User login + Dashboard features"
git push origin v1.2.0
```

**Result:**

```
✅ User Login → LIVE
✅ Dashboard  → LIVE
⏳ Payment    → Next week (Amit abhi bhi kaam kar raha hai)
```

---

## 15. Commands Cheat Sheet

### 🟢 Roz Use Hone Wale Commands

```bash
git status                          # Kya kya badla?
git add .                           # Sab stage karo
git add src/login.js                # Specific file stage karo
git commit -m "message"             # Commit karo
git push origin feature/my-branch  # GitHub par bhejo
git pull origin develop             # Latest lo
```

### 🔵 Branch Commands

```bash
git branch                          # Saare branches dekho (* = current)
git checkout develop                # develop par jao
git checkout -b feature/xyz         # Naya branch banao aur usmein jao
git checkout feature/xyz            # Existing branch par jao
git branch -d feature/xyz          # Branch delete karo (safe — merged hone ke baad)
git branch -D feature/xyz          # Branch force delete (unmerged bhi)
```

### 🟡 Sync Commands (Roz Karo)

```bash
# Develop se apna branch update karo
git checkout develop
git pull origin develop
git checkout feature/mera-branch
git merge develop
git push origin feature/mera-branch
```

### 🔴 Undo Commands — Galti Ho Gayi

```bash
# Last commit undo karo (code safe raha, sirf commit hata)
git reset --soft HEAD~1

# Last commit aur code dono undo karo (DANGEROUS)
git reset --hard HEAD~1

# Ek file ko last commit wali state mein wapas laao
git restore src/login.js

# Sab unstaged changes undo karo
git restore .

# Pichle commits dekho
git log --oneline -10
```

### 🟣 Helpful Commands

```bash
git diff                            # Kya badla (stage se pehle)
git diff --staged                   # Kya stage hua
git stash                           # Kaam temporarily side mein rakho
git stash pop                       # Side wala kaam wapas laao
git log --oneline --graph --all     # Visual branch history
git remote -v                       # Remote URL dekho
```

---

## 16. Company Rules

### 🏆 Golden Rules — Ye Kabhi Mat Bhulo

```
Rule 1: main mein DIRECT PUSH = NEVER. Koi excuse nahi.

Rule 2: Naya kaam = HAMESHA naya feature branch.
        Ek branch mein do alag features mat karo.

Rule 3: PR se pehle HAMESHA develop sync karo.
        (git pull develop → git merge develop → tab PR)

Rule 4: MEANINGFUL commit messages.
        Future mein khud ko samjhana padega kya kiya tha.

Rule 5: Roz push karo.
        "Mera laptop mein pada hai" acceptable nahi.

Rule 6: Review ke bina merge nahi.
        Apna khud ka PR khud approve nahi karte.
```

### 📝 PR Description Template

Is template ko `.github/pull_request_template.md` mein save karo — automatically fill hoga:

```markdown
## Kya kiya?
<!-- Short mein explain karo -->

## Kyun kiya?
<!-- Issue number agar hai: Fixes #23 -->

## Kaise test karein?
1. 
2. 
3. 

## Screenshots (agar UI change hai)
<!-- Screenshot paste karo -->

## Checklist
- [ ] Code kaam karta hai locally
- [ ] Koi console errors nahi
- [ ] Mobile responsive check kiya (agar UI)
- [ ] Test cases likhe (agar applicable)
```

---

## 🎯 Quick Summary — Ek Page Mein Poora System

```
OWNER — EK BAAR KARO:
  ① GitHub par repo banao
  ② main + develop branch banao
  ③ Branch protection rules lagao
  ④ Employees add karo (Collaborators)

═══════════════════════════════════════

EMPLOYEE — HAR FEATURE KE LIYE:
  ① git checkout develop
  ② git pull origin develop         ← SABSE IMPORTANT STEP
  ③ git checkout -b feature/xyz     ← Naya branch
  ④ [kaam karo]
  ⑤ git add . && git commit -m "..."
  ⑥ git push origin feature/xyz
  ⑦ GitHub par PR banao → develop
  ⑧ Review ka wait karo
  ⑨ Approved → Merge → Branch delete

═══════════════════════════════════════

OWNER — RELEASE KE WAQT:
  ① develop mein sab features test ho
  ② git checkout main
  ③ git merge develop
  ④ git push origin main
  ⑤ git tag -a v1.0.0 -m "Release note"
  ⑥ git push origin v1.0.0

═══════════════════════════════════════

EMERGENCY BUG (Hotfix):
  ① git checkout main
  ② git checkout -b hotfix/xyz
  ③ [fix karo]
  ④ PR → main (fast review)
  ⑤ Phir develop mein bhi merge karo
```

---

## 🔗 Aage Kya Seekho?

| Topic | Kab | Kya Milega |
|-------|-----|-----------|
| **GitHub Issues** | Abhi | Task tracking — Kaunsa kaam kisko diya |
| **GitHub Projects (Kanban)** | Week 2 | Trello jaisa board team ke liye |
| **GitHub Actions (CI/CD)** | 1 mahine baad | Auto-test, auto-deploy |
| **Git Rebase** | 2 mahine baad | Cleaner commit history |
| **Semantic Versioning** | Pehle release par | v1.2.3 ka matlab samjhna |
| **Code Review Best Practices** | Jab team 3+ ho | Achhi review kaise karein |

---

---

# 🧠 Part 2 — Beginner Confusions: Real Questions, Simple Answers

> *Ye section un sawalon ke liye hai jo har naye developer ke mann mein aate hain — lekin poochha nahi jaata.*

---

## 💡 Pehle Samjho — Local vs Remote

Ye ek concept clear ho gaya to 80% confusion khatam.

```
🖥️  LOCAL  = Tera computer
☁️  REMOTE = GitHub (online)

Dono automatically sync NAHI hote.
Tu manually sync karta hai:

  Tera code → GitHub:   git push
  GitHub → Tera code:   git pull
```

---

## ❓ Confusion 1 — "Maine commit kiya, GitHub par kyun nahi dikha?"

**Reality:** `git commit` sirf teri machine par save karta hai. GitHub ko pata nahi.

```bash
# Galat soch:
git commit -m "Login page banaya"   ← Sirf local save hua

# Sahi flow:
git add .
git commit -m "Login page banaya"   ← Local save
git push origin feature/login       ← Ab GitHub par gaya ✅
```

> 💡 **Analogy:** Commit = Diary mein likha. Push = Diary scan karke WhatsApp par bheja.

---

## ❓ Confusion 2 — "Commit aur Push mein kya fark hai?"

| Command | Kya Karta Hai | Kahan Jaata Hai |
|---------|--------------|----------------|
| `git add .` | Files select karo | Staging area |
| `git commit` | Snapshot lo | Teri machine |
| `git push` | Upload karo | GitHub |

```
Think karo aise:
  git add    = Parcel pack karo
  git commit = Parcel par label lagao
  git push   = Parcel courier ko do
```

---

## ❓ Confusion 3 — "Teammate ne code push kiya, mujhe kyun nahi dikh raha?"

Kyunki tera local code purana hai. GitHub se lo:

```bash
git pull origin develop
# Ab tera code latest ho gaya ✅
```

> ⚠️ **Roz subah pehla kaam:** `git pull` — jaise WhatsApp messages check karte ho.

---

## ❓ Confusion 4 — "Maine Login page banaya, dusre ne Signup — dono kaise milenge?"

Agar **alag files** hain — Git automatically merge kar deta hai, koi conflict nahi:

```
Developer A bana raha hai:  Login.js
Developer B bana raha hai:  Signup.js

Dono alag files → Git khud merge kar dega ✅

Final result:
  ✅ Login.js
  ✅ Signup.js
  Dono saath!
```

Problem tabhi hoti hai jab **same file ka same part** dono ne badla ho.

---

## ❓ Confusion 5 — "Merge conflict exactly kab aata hai?"

**Same file + Same line + Do alag changes = CONFLICT**

```js
// Original code:
const color = "blue";

// Developer A ne badla:
const color = "red";

// Developer B ne badla:
const color = "green";

// Git confuse: Kaun sahi hai? → CONFLICT! 😱
```

Git file mein ye dikhaata hai:

```
<<<<<<< HEAD
const color = "red";        ← Tera code
=======
const color = "green";      ← Unka code
>>>>>>> feature-branch
```

**Tu decide kar** — kaunsa rakhna hai — phir markers hata do aur commit karo.

---

## ❓ Confusion 6 — "Mera code mere machine par kaam karta hai, server par nahi — kyun?"

Classic **"Works on my machine"** problem. Reasons:

```
❌ node_modules different version
❌ .env file nahi hai server par (secret keys)
❌ git pull nahi kiya latest
❌ API response kisi ne change kiya
❌ OS alag hai (Windows vs Linux)
```

**Fix:**
```bash
# Sab latest lo
git pull origin develop

# .env file check karo — server par bhi same values hain?
# Dependencies sync karo
npm install   # ya pip install -r requirements.txt
```

---

## ❓ Confusion 7 — "Testing mushkil kyun hoti hai merge se pehle?"

Kyunki features ek dusre par depend karte hain:

```
Situation:
  Signup page → Login page par redirect karta hai
  Login feature abhi develop mein merge NAHI hua

Result:
  Signup test karo → Login page milta hi nahi → CRASH 💥

Possible issues:
  ❌ Route missing
  ❌ API missing
  ❌ Auth logic missing
  ❌ UI crash
```

**Solution:** Feature branches ko develop mein milate raho regularly — sync raho.

---

## ❓ Confusion 8 — "Merge ke baad achanak bugs kyun aate hain?"

Kyunki alag alag features akele kaam karte hain, **saath mein nahi**:

```
Developer A: API ka response badla → { user: {...} }
Developer B: Purana response expect karta tha → { data: {...} }

Dono ka kaam apne branch mein theek tha.
Merge ke baad → APPLICATION CRASH 💥
```

**Isliye:** Merge ke baad hamesha poora app test karo — sirf apna feature nahi.

---

## ❓ Confusion 9 — "git add kya karta hai exactly?"

Git mein 3 stages hain:

```
📁 Working Directory   → File edit ki (Git ko abhi pata nahi)
📋 Staging Area        → git add kiya (Git ready hai)
💾 Repository          → git commit kiya (Permanently save)
```

```bash
# Example:
# Login.js edit kiya
git status          # "modified: Login.js" dikhega
git add Login.js    # Staging mein gaya
git commit -m "Fix login validation"   # Permanently save ✅
```

> 💡 **Kyun staging area hai?** Taki tu choose kar sake — kaun si files is commit mein jaayengi, kaun si nahi.

---

## ❓ Confusion 10 — "origin kya hota hai?"

`origin` = Tera GitHub repo ka shortcut naam

```bash
# Ye dono same hain:
git push origin main
git push https://github.com/tarun/my-project.git main

# origin sirf ek nickname hai — full URL yaad nahi rakhna padta
```

Verify karo:
```bash
git remote -v
# OUTPUT:
# origin  https://github.com/tarun/my-project.git (fetch)
# origin  https://github.com/tarun/my-project.git (push)
```

---

## ❓ Confusion 11 — "HEAD kya hota hai?"

HEAD = **"Tu abhi kahan hai"** — Git ka current position marker

```bash
git log --oneline
# OUTPUT:
# a1b2c3d (HEAD -> feature/login)  ← Tu yahan hai
# e4f5g6h Add signup page
# i7j8k9l Initial commit
```

```
HEAD → develop      = Tu develop branch par hai
HEAD → main         = Tu main branch par hai
HEAD → a1b2c3d      = Tu ek specific commit par hai (detached HEAD)
```

---

## ❓ Confusion 12 — "Merge aur Rebase mein kya fark hai?"

| | Merge | Rebase |
|--|-------|--------|
| **Kya karta hai** | Dono branches milata hai | Tera kaam latest changes ke upar rakhta hai |
| **History** | Merge commit banta hai | Clean, seedhi line |
| **Beginner ke liye** | ✅ Easy, safe | ⚠️ Advanced, careful |
| **Use karo** | Team mein | Personal branch clean karne |

```bash
# Merge (beginners ke liye)
git merge develop

# Rebase (seekhne ke baad)
git rebase develop
```

> 💡 **Rule:** Pehle merge seekho. Rebase baad mein aayega.

---

## ❓ Confusion 13 — "CI/CD kya hota hai aur kyun companies use karti hain?"

**CI = Continuous Integration** — Har PR par automatic tests chalte hain  
**CD = Continuous Deployment** — Test pass hone par auto deploy hota hai

```
Bina CI/CD:
  Developer → PR banao → Owner manually test kare → Merge → Deploy
  (Slow, human error possible)

CI/CD ke saath:
  Developer → PR banao → Robot automatically:
    ✅ Build check karta hai
    ✅ Tests chalata hai
    ✅ Lint errors dhundta hai
    ✅ Deploy karta hai
  (Fast, automatic, reliable)
```

Beginner ke liye abhi zaroori nahi — **GitHub Actions** seekhna tab jab basic workflow comfortable lage.

---

## 🚨 Common Beginner Mistakes — Aur Unka Fix

| ❌ Galti | 😱 Problem | ✅ Fix |
|---------|-----------|-------|
| Main par directly kaam karna | Poori team affect | Hamesha feature branch banao |
| Pull nahi kiya subah | Conflicts baad mein | Roz `git pull` pehle |
| Ek bade commit mein sab kuch | Debug impossible | Chhote chhote commits karo |
| Branch nahi banaya | Chaos | Har feature = alag branch |
| Broken code push kiya | Build fail | Locally test karo pehle |
| Conflict ignore kiya | Hidden bugs | Conflict carefully padho aur solve karo |
| Merge ke baad test nahi kiya | App crash | Hamesha full test karo |
| `.env` push kar diya | Security breach 🔴 | `.gitignore` mein daalo |

---

## 🛡️ Beginner ke Liye Golden Rules

```
✅ Rule 1: Roz subah git pull karo — fresh start hamesha

✅ Rule 2: Har feature ke liye naya branch — main touch mat karo

✅ Rule 3: Chhote commits — "Add login button" better than "All changes"

✅ Rule 4: Pull ke baad test karo — dependencies change ho sakti hain

✅ Rule 5: Conflict aaye to PANIC mat karo
           Git sirf pooch raha hai: "Kaun sa code rakhun?"
           Padho, decide karo, resolve karo.

✅ Rule 6: .env kabhi push mat karo — secret keys = danger

✅ Rule 7: PR banane se pehle develop se sync karo hamesha
```

---

## 🎯 Git Ko Ek Line Mein Samjho

```
Git = Ek smart history + collaboration system for code.

Asli challenge commands nahi hai.
Asli challenge hai:
  "Multiple developers, related code, alag alag time par changes."

Ye 5 cheezein samjh lo — Git easy ho jaata hai:
  1. Local vs Remote
  2. Commit vs Push
  3. Pull before work
  4. Branches use karo
  5. Conflicts se daro mat
```

> 🏆 **Yaad rakho:** Har experienced developer ne bhi pehle confusing merges kiye hain. Practice se comfortable hota hai — theory se nahi.

---

*Made with ❤️ — GitHub Workflow Guide for Beginners*  
*Version: 3.0 | Language: Hinglish | Audience: Absolute Beginners*
