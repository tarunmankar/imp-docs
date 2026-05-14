# 🚀 AI-Powered Software Delivery Blueprint (2026 Edition)
### *Zero se App tak — Bina Coding Seekhe, AI se Banao!*

> **Updated:** May 2026 · Next.js 16 · Supabase 2026 · Cursor / Windsurf / VS Code Copilot / Google Antigravity

---

## 📖 Yeh Document Kiske Liye Hai?

Agar aap...
- **Pehli baar** koi web app banana chahte hain
- Coding nahi aati, lekin **AI se kaam nikalwana** chahte hain
- Ek solid system chahte hain jisme **galti ki gunjaish na ho**

...toh yeh document **aapke liye hi** likha gaya hai. 🎯

Hum ek example project **"Kharcha Tracker PRO"** (Expense Tracker App) bananenge — step by step, copy-paste karke.

---

## 🏆 Shuruaat Se Pehle: 5 Sone Ke Niyam

Yeh padhna zaroori hai — agar yeh niyam yaad rahe toh 80% galtiyan hoti hi nahi:

| # | Niyam | Kyon Zaroori Hai |
|---|-------|-----------------|
| 1 | **Database pehle, phir Logic, phir UI** | Ulta karne se baad mein sab todna padta hai |
| 2 | **Ek Kaam Ek Baar (Chunking)** | AI ko sirf ek task do, warna confuse hota hai |
| 3 | **API Keys kabhi code mein mat likho** | Secret keys hamesha `.env.local` file mein |
| 4 | **30-40 messages ke baad Nayi Chat karo** | AI ki memory bhar jaati hai, galat code dene lagta hai |
| 5 | **Test karo, phir Save karo** | Bina browser mein dekhe kabhi git commit mat karo |

---

## 📑 Table of Contents

1. [🧠 AI Editor ka Chunav — 2026 Mein Kaun Best Hai?](#1-ai-editor-ka-chunav--2026-mein-kaun-best-hai)
2. [👥 Kaun Kya Karega? (Aap vs AI)](#2-kaun-kya-karega-aap-vs-ai)
3. [🛠️ Phase 1 — GitHub Setup (Din 1 ka Kaam)](#3-phase-1--github-setup-din-1-ka-kaam)
4. [🤖 Phase 2 — AI Brain Setup (Rules + Planning Files)](#4-phase-2--ai-brain-setup-rules--planning-files)
5. [🏗️ Phase 3 — Pehla Task: Base Architecture](#5-phase-3--pehla-task-base-architecture)
6. [🔁 Phase 4 — Development Loop (Baar Baar Yahi Karein)](#6-phase-4--development-loop-baar-baar-yahi-karein)
7. [🔐 Phase 5 — Security: Supabase RLS Setup](#7-phase-5--security-supabase-rls-setup)
8. [🚀 Phase 6 — Deployment: Vercel Par Live Karo](#8-phase-6--deployment-vercel-par-live-karo)
9. [💻 Commands Cheat Sheet](#9-commands-cheat-sheet)
10. [🆘 Emergency Guide — Jab Sab Toot Jaye](#10-emergency-guide--jab-sab-toot-jaye)

---

## 1. 🧠 AI Editor ka Chunav — 2026 Mein Kaun Best Hai?

> **Simple Language Mein:** AI Editor woh software hai jisme aap apna code likhte hain, aur AI apne aap help karta hai.

Aaj (May 2026) mein **chaar** main options hain:

### Option A: Cursor ⭐ (Beginners ke liye Best)
- VS Code jaisa dikhta hai — switch karna aasaan
- **Composer Mode**: Ek command se multiple files mein changes
- **Pricing**: Free trial → Pro `$20/month`
- **Install**: [cursor.com](https://cursor.com) → Download → Install
- **Rules file location**: `.cursorrules` (root folder mein)

### Option B: Windsurf (Best Value, Beginners Friendly)
- Cursor ka sabse accha alternative
- **Cascade** feature bahut smart hai — context yaad rakhta hai
- **Pricing**: Free tier generous → Pro `$20/month`
- **Install**: [windsurf.com](https://windsurf.com) → Download
- **Rules file location**: `.windsurfrules` (root folder mein)

### Option C: VS Code + GitHub Copilot (Sabse Popular)
- Sabse zyada use hone wala editor (42% market share)
- Agent Mode (2025 se available) — multi-file editing
- **Pricing**: Free (2000 completions/month) → Pro `$10/month`
- **Install**: [code.visualstudio.com](https://code.visualstudio.com) → Download → Extension: GitHub Copilot install karo
- **Rules file location**: `.github/copilot-instructions.md`

### Option D: Google Antigravity ⚡ (FREE + Most Powerful Agent Features)
- Google ka **agent-first** development platform — sirf code likhne wala tool nahi, balki autonomous AI agent jo khud plan karta hai, code likhta hai, terminal chalata hai, aur browser mein test bhi karta hai
- November 2025 mein launch hua, VS Code ka heavily modified fork hai — matlab aapke VS Code extensions seedha kaam karenge
- **100% FREE** public preview mein — Gemini 3 Pro ka generous usage included
- Supported models: **Gemini 3 Pro** (Google), **Claude Sonnet 4.5** (Anthropic), **GPT-OSS** (OpenAI)
- **Install**: [antigravity.google](https://antigravity.google) → Download → Install (Mac / Windows / Linux)
- **Rules file locations** (do options hain):
  - `GEMINI.md` — project ke root folder mein (sabse aasaan, Antigravity-specific)
  - `AGENTS.md` — root folder mein (cross-tool file, Cursor + Antigravity dono padhte hain — March 2026 se)
  - `.agents/rules/` — folder mein alag-alag rule files (advanced)

> 💡 **Antigravity Ka Sabse Bada Fayda:** **Manager View** — ek saath kai alag-alag agents alag-alag kaam par lagao. Ek agent UI bana raha hai, doosra bugs fix kar raha hai — aap bas dekho!

### 💡 Meri Recommendation:
```
Bilkul FREE chahiye + Powerful Agents?  → Google Antigravity (Best Features, Free)
Bilkul Naye Hain? (Desktop)            → Windsurf (Beginner-Friendly)
Thoda Experience?                      → Cursor (Customizable)
Team Use / Budget?                     → VS Code + Copilot (Sabse Sasta)
```

---

## 2. 👥 Kaun Kya Karega? (Aap vs AI)

Responsibilities clear rakhna bahut zaroori hai:

| 🙋 Aapka Kaam (Manager) | 🤖 AI Ka Kaam (Developer) |
|------------------------|--------------------------|
| Project ka idea banana | Poora Frontend code likhna (Tailwind CSS) |
| GitHub par repo banana | Supabase SDK setup karna |
| Supabase Dashboard par project banana | Login / Signup ka logic likhna |
| `.env.local` mein API Keys paste karna | Console errors padhna aur bugs fix karna |
| `npm run dev` chalakar browser mein test karna | Git commit messages likhna |
| AI ke code ko approve karna | Database queries (CRUD) likhna |

> **Yaad Rakho:** Aap **Manager** ho, AI **Developer** hai. Aap decide karo kya banana hai — AI banayega.

---

## 3. 🛠️ Phase 1 — GitHub Setup (Din 1 ka Kaam)

> **GitHub kya hai?** Yeh aapka online code locker hai. Jaise Google Drive files ke liye, GitHub code ke liye hai.

### Step 1: GitHub Account Banao

1. [github.com](https://github.com) par jao
2. **Sign Up** karo (free hai)
3. Email verify karo

### Step 2: Naya Repository (Project Folder) Banao

1. GitHub par login karne ke baad, upar right corner mein **"+"** icon → **"New repository"**
2. Yeh details bharo:
   - **Repository name**: `kharcha-tracker-pro` *(ya apne project ka naam)*
   - **Description**: `AI se banaya hua expense tracker app`
   - **Public / Private**: Private select karo (safe rahega)
   - ✅ **Add a README file** — zaroor tick karo
   - **.gitignore**: `Node` select karo dropdown mein
3. **"Create repository"** button dabao

### Step 3: Project Apne Computer Par Lao (Clone)

**Terminal kaise kholein?**
- Windows: Start menu → "cmd" ya "PowerShell" search karo
- Mac: Spotlight (Cmd+Space) → "Terminal" likho

Terminal mein yeh commands ek-ek karke chalao:

```bash
# Step 1: Project download karo (GitHub ka URL apna daalo)
git clone https://github.com/AAPKA-USERNAME/kharcha-tracker-pro.git

# Step 2: Us folder mein jaao
cd kharcha-tracker-pro
```

### Step 4: Code Editor Mein Kholo

```bash
cursor .      # Cursor ke liye
code .        # VS Code ke liye
```

> 🤖 **Google Antigravity use kar rahe hain?** Antigravity mein left side → **Open Folder** click karo → apna clone kiya hua folder select karo. Ya seedha **Clone Repository** option se GitHub URL daal sakte ho.

> ✅ **Phase 1 Complete!** Ab aapka project GitHub par safe hai aur computer par bhi khula hai.

---

## 4. 🤖 Phase 2 — AI Brain Setup (Rules + Planning Files)

> **Yeh kyon zaroori hai?** In files se AI ko pata chalta hai aapka project kaisa hai, kya rules follow karne hain. Bina in files ke AI random code likhega.

### Folder Structure (Kaisa Dikhega)

```
kharcha-tracker-pro/           ← Aapka Main Folder (Root)
│
├── 📝 AAPKI BANAYI HUI FILES (Aaj Banao):
│   ├── PROJECT_BLUEPRINT.md   ← Tech stack ki jankari
│   ├── TASKS.md               ← To-do list
│   │
│   └── 🤖 AI Rules File — SIRF EK CHUNEIN apne editor ke hisaab se:
│       ├── .cursorrules                      ← Cursor ke liye (ya AGENTS.md)
│       ├── AGENTS.md                         ← Cursor + Antigravity dono padhte hain ✨
│       ├── .windsurfrules                    ← Windsurf ke liye
│       ├── .github/copilot-instructions.md   ← VS Code + Copilot ke liye
│       └── GEMINI.md                         ← Google Antigravity ke liye (Antigravity-specific)
│
└── 🤖 AI BANAYEGA (Baad Mein):
    ├── app/                   ← Pages (Next.js)
    │   ├── page.tsx           ← Home page
    │   ├── login/page.tsx     ← Login page
    │   └── dashboard/page.tsx ← Dashboard
    ├── components/            ← Reusable UI parts
    ├── lib/
    │   └── db.js              ← Supabase connection
    ├── .env.local             ← Secret keys (GitHub par NAHI jayega)
    └── package.json           ← Installed packages list
```

---

### File 1: AI Rules File

**Cursor use kar rahe hain?** Root folder mein `.cursorrules` ya `AGENTS.md` naam ki file banao.
**Windsurf use kar rahe hain?** Root folder mein `.windsurfrules` naam ki file banao.
**VS Code + Copilot?** `.github/copilot-instructions.md` banao.
**Google Antigravity?** Root folder mein `GEMINI.md` banao — ya `AGENTS.md` banao jo Cursor aur Antigravity dono padhte hain (best option agar dono use karte ho).

**Andar yeh content paste karo:**

```markdown
# AI Workspace Rules

You are an expert full-stack developer helping a non-technical founder build their app.

BEFORE planning or writing any code, silently read:
1. PROJECT_BLUEPRINT.md — for Tech Stack and architecture decisions
2. TASKS.md — to know current progress and what to build next

## Core Rules

- Write clean, production-ready code with no placeholder TODOs
- NEVER hardcode API keys — always use `.env.local` with `NEXT_PUBLIC_` prefix
- Use Supabase client-side SDK for browser, server-side for secure operations
- Build mobile-first responsive UI using Tailwind CSS
- When fixing an error, briefly explain the root cause before fixing it
- After completing any task, tell me what to test in the browser

## Tech Stack (Always Follow This)

- Framework: Next.js 16 (App Router)
- Styling: Tailwind CSS + Shadcn UI
- Database + Auth: Supabase
- Deployment: Vercel

## Security Rules (Never Break These)

- Enable RLS on every Supabase table
- Never expose `service_role` key in client code
- Always validate user session before showing protected data
```

---

### File 2: PROJECT_BLUEPRINT.md

Root folder mein `PROJECT_BLUEPRINT.md` naam ki file banao aur yeh paste karo:

```markdown
# Project Blueprint: Kharcha Tracker PRO

## App Ka Maqsad
Ek simple expense tracker jisme user apna daily kharcha add, dekh, aur delete kar sake.

## Tech Stack (May 2026)
- **Framework**: Next.js 16 (App Router) — Latest stable version
- **Styling**: Tailwind CSS v3 + Shadcn UI components
- **Database**: Supabase (PostgreSQL)
- **Auth**: Supabase Auth (Email/Password)
- **Deployment**: Vercel

## Main Features
1. User Login / Register
2. Kharcha (Expense) add karna
3. Apne sare kharchon ki list dekhna
4. Kharcha delete karna
5. Monthly total dekhna

## Database Tables
- `profiles` — User ka naam aur info
- `expenses` — Har kharcha ka record (amount, category, date, user_id)

## Important Rules
- Koi bhi user sirf apna data dekhe (RLS enabled)
- .env.local mein saari keys rakhni hain
- Mobile pe bhi achha dikhe (responsive)
```

---

### File 3: TASKS.md

Root folder mein `TASKS.md` naam ki file banao:

```markdown
# Project Tasks — Kharcha Tracker PRO

## Progress Legend
- [ ] = Abhi karna baaki hai
- [x] = Ho gaya ✅

---

## Module 0 — Setup
- [ ] 0.1 Next.js 16 project install karo
- [ ] 0.2 Tailwind CSS configure karo
- [ ] 0.3 Supabase project create karo (supabase.com par)
- [ ] 0.4 `.env.local` mein Supabase keys daalo
- [ ] 0.5 `lib/supabase.js` client file banao

## Module 1 — Authentication (Login/Register)
- [ ] 1.1 Login page UI banao (`/login`)
- [ ] 1.2 Register page UI banao (`/register`)
- [ ] 1.3 Supabase Auth connect karo
- [ ] 1.4 Login hone par `/dashboard` par bhejo
- [ ] 1.5 Protected route: Bina login ke dashboard nahi khule

## Module 2 — Expenses CRUD
- [ ] 2.1 Supabase mein `expenses` table banao
- [ ] 2.2 RLS policies lagao (user sirf apna data dekhe)
- [ ] 2.3 "Add Expense" form banao
- [ ] 2.4 Expenses ki list/table dikhao
- [ ] 2.5 Expense delete karne ka button lagao

## Module 3 — Dashboard Analytics
- [ ] 3.1 Is month ka total kharcha dikhao
- [ ] 3.2 Category-wise breakdown dikhao
- [ ] 3.3 Simple chart lagao (optional)

## Module 4 — Deployment
- [ ] 4.1 Vercel par connect karo
- [ ] 4.2 Environment variables Vercel mein daalo
- [ ] 4.3 Live link test karo
```

### ✅ Setup Save Karo

Terminal mein yeh chalao:

```bash
git add .
git commit -m "chore: AI brain files setup complete"
git push origin main
```

> **Iska Matlab:** Aapki yeh files GitHub par safe ho gayi hain.

---

## 5. 🏗️ Phase 3 — Pehla Task: Base Architecture

> **Yeh Phase Sirf Ek Baar Hoga.** Isme Next.js install hoga aur Supabase se connection banega.

### Step 1: AI ko Prompt Karo

AI chat mein yeh copy-paste karo:

```
Read TASKS.md and PROJECT_BLUEPRINT.md first.

Then complete Module 0 (Setup):
1. Install Next.js 16 in this folder using: npx create-next-app@latest . 
   (Use these options: TypeScript=Yes, ESLint=Yes, Tailwind=Yes, App Router=Yes)
2. Install Supabase client: npm install @supabase/supabase-js @supabase/ssr
3. Create `lib/supabase.js` with client-side Supabase initialization using env variables
4. Tell me exactly what to put in `.env.local` file

Important: Don't delete my existing markdown files (PROJECT_BLUEPRINT.md, TASKS.md, .cursorrules)
```

### Step 2: AI Jo Commands Dega, Terminal Mein Chalao

AI kuch aisa dega:
```bash
npx create-next-app@latest .
```

> ⚠️ **Install ke waqt questions aayenge:** Arrow keys se "Yes" ya "No" choose karo. App Router = Yes zaroor karo.

### Step 3: Supabase Account Banao

1. [supabase.com](https://supabase.com) par jao → **Sign Up** (free)
2. **New Project** banao
3. Project ka naam: `kharcha-tracker`
4. Password set karo (yaad rakhna!)
5. Region: `Southeast Asia` ya jo sabse kareeb ho
6. **Create Project** — 2 minute wait karo

### Step 4: API Keys Copy Karo

Supabase Dashboard mein:
1. Left sidebar → **Project Settings** (gear icon)
2. **API** tab par click karo
3. Yeh do cheezein copy karo:
   - `Project URL` (jaise: `https://abcd.supabase.co`)
   - `anon public` key (lambi string)

### Step 5: .env.local File Banao

Project ke root folder mein `.env.local` naam ki file banao (manually):

```bash
NEXT_PUBLIC_SUPABASE_URL=https://AAPKA-PROJECT.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=AAPKI-ANON-KEY-YAHAN
```

> 🔐 **Yeh file kabhi GitHub par push nahi hogi** (`.gitignore` mein already listed hai)

### Step 6: App Chalao aur Test Karo

```bash
npm run dev
```

Browser mein jao: `http://localhost:3000`

Agar page dikha → ✅ Kaamyaab! TASKS.md mein Module 0 ke sare boxes tick karo.

```bash
git add .
git commit -m "feat: Next.js 16 + Supabase base setup done"
git push origin main
```

---

## 6. 🔁 Phase 4 — Development Loop (Baar Baar Yahi Karein)

> **Yeh sabse important section hai.** Har module isi cycle mein banayenge. Yaad kar lo: **Pick → Build → Test → Save → Repeat**

```
┌─────────────────────────────────────────┐
│                                         │
│   A. TASKS.md se Module Chuno          │
│              ↓                          │
│   B. AI ko Prompt Karo (Build)         │
│              ↓                          │
│   C. Browser Mein Test Karo           │
│              ↓                          │
│   D. Git Commit (Save)                 │
│              ↓                          │
│   E. TASKS.md Update karo ──────────── ┘
│      Phir Agla Module                   │
└─────────────────────────────────────────┘
```

---

### 🔄 Loop: Module 1 — Authentication (Login/Register)

#### Step A — Pick

TASKS.md kholko, Module 1 dekho.

#### Step B — AI Prompt

```
Read TASKS.md. Now complete Module 1 (Authentication):

1. Create Login page at `/login` with email + password form (Tailwind CSS styling)
2. Create Register page at `/register`  
3. Connect both with Supabase Auth
4. After successful login → redirect to `/dashboard`
5. Make `/dashboard` a protected route — if not logged in, redirect to `/login`

Use Supabase SSR package for session handling.
Show me what to test after you're done.
```

#### Step C — Test Karo (Agar Error Aaye)

Browser mein `F12` dabao → **Console** tab → Error copy karo → AI ko do:

```
Yeh error aa raha hai, fix karo:
[ERROR YAHAN PASTE KARO]
```

Agar sab theek hai:
1. `localhost:3000/register` par jao → naya account banao
2. Supabase Dashboard → **Authentication** → **Users** → naya user dikha? ✅
3. Login karo → `/dashboard` par gaya? ✅

#### Step D — Save Karo

```bash
git add .
git commit -m "feat: Module 1 - Auth complete (Login/Register)"
git push origin main
```

#### Step E — Update aur Repeat

TASKS.md mein Module 1 ke sab boxes tick karo. Ab Module 2 uthao!

---

### 🔄 Loop: Module 2 — Expenses CRUD

#### Step B — AI Prompt

```
Read TASKS.md. Complete Module 2 (Expenses):

1. First, write the SQL to create this table in Supabase:
   - Table: `expenses`
   - Columns: id (uuid), user_id (uuid, references auth.users), 
     amount (numeric), category (text), description (text), 
     date (date), created_at (timestamptz default now())

2. Write RLS policies so users can only see/edit their own expenses

3. Create "Add Expense" form component with: amount, category dropdown, description, date

4. Show expenses in a table on dashboard

5. Add delete button for each expense

Tell me step by step what to do in Supabase dashboard and what to test.
```

#### Supabase Mein Table Banane Ka Tarika

AI jo SQL dega, usse Supabase mein run karna hai:
1. Supabase Dashboard → left sidebar → **SQL Editor**
2. AI ka SQL paste karo
3. **Run** button dabao
4. Success message aaya? ✅

#### Step C — Test Karo

1. Login karo → Dashboard par jao
2. Form bharke expense add karo
3. List mein dikha? ✅
4. Supabase Dashboard → **Table Editor** → `expenses` table → row dikha? ✅
5. Delete button kaam kiya? ✅

#### Step D — Save

```bash
git add .
git commit -m "feat: Module 2 - Expenses CRUD done"
git push origin main
```

---

### 🔄 Loop: Module 3 — Dashboard Analytics (Optional)

#### Step B — AI Prompt

```
Read TASKS.md. Complete Module 3 (Analytics):

1. Show total expenses for current month on dashboard
2. Show breakdown by category (simple list with amounts)
3. Optionally add a simple bar chart using recharts library

Keep it simple and mobile-friendly.
```

#### Save

```bash
git commit -am "feat: Module 3 - Dashboard analytics done"
git push origin main
```

---

## 7. 🔐 Phase 5 — Security: Supabase RLS Setup

> **RLS (Row Level Security) kya hai?** Yeh ek database lock hai. Isse User A ka data sirf User A dekh sakta hai, User B nahi.

### 🚨 Yeh Karna Bahut Zaroori Hai — Warna Koi Bhi Aapka Data Dekh Sakta Hai!

#### Supabase 2026 Mein RLS Automatically Alert Karta Hai

Supabase ab khud dashboard mein warning dikhata hai agar koi table unprotected hai. Phir bhi manually check karo:

1. Supabase Dashboard → **Database** → **Security Advisor**
2. Koi warning hai? Fix karo

#### AI Ko RLS Policies Likhwao

Har naye module ke liye yeh prompt zaroor do:

```
Mere `expenses` table ke liye complete Supabase RLS policies likho:
- SELECT: Sirf apna data dekhe (user_id = auth.uid())
- INSERT: Sirf apna data daale (user_id = auth.uid())
- UPDATE: Sirf apna data update kare
- DELETE: Sirf apna data delete kare

SQL format mein do taaki main Supabase SQL Editor mein paste kar sakun.
```

#### AI Ka Diya Hua RLS SQL (Example)

```sql
-- RLS Enable karo
ALTER TABLE expenses ENABLE ROW LEVEL SECURITY;

-- SELECT: Sirf apna data
CREATE POLICY "Users can view own expenses" 
ON expenses FOR SELECT 
TO authenticated 
USING (auth.uid() = user_id);

-- INSERT: Sirf apna data daalo
CREATE POLICY "Users can insert own expenses" 
ON expenses FOR INSERT 
TO authenticated 
WITH CHECK (auth.uid() = user_id);

-- UPDATE: Sirf apna data
CREATE POLICY "Users can update own expenses" 
ON expenses FOR UPDATE 
TO authenticated 
USING (auth.uid() = user_id);

-- DELETE: Sirf apna data
CREATE POLICY "Users can delete own expenses" 
ON expenses FOR DELETE 
TO authenticated 
USING (auth.uid() = user_id);
```

#### Test Karo RLS Kaam Kar Raha Hai?

1. Do alag accounts banao (User A, User B)
2. User A se login karo → kuch expenses add karo
3. User B se login karo → User A ka data NAHI dikhna chahiye ✅

> ⚠️ **Warning**: `service_role` key (Supabase settings mein milti hai) kabhi bhi frontend code mein use mat karo. Woh RLS bypass kar deti hai — dangerous hai!

---

## 8. 🚀 Phase 6 — Deployment: Vercel Par Live Karo

> **Jab TASKS.md ke sab boxes [x] ho jayen, toh deploy karo!**

### Step 1: Final Push

```bash
git add .
git commit -am "ready for production deployment"
git push origin main
```

### Step 2: Vercel Account Banao

1. [vercel.com](https://vercel.com) par jao → **Sign Up with GitHub**
2. GitHub account se login karo

### Step 3: Project Import Karo

1. Vercel dashboard → **"Add New Project"**
2. Apna GitHub repo `kharcha-tracker-pro` dhundho → **Import**

### Step 4: 🚨 Environment Variables Daalo (BAHUT ZAROORI!)

> **Agar yeh bhool gaye toh app live hoga lekin kaam nahi karega!**

Deploy karne se PEHLE, Vercel mein:
1. **Environment Variables** section mein jao
2. `.env.local` ki saari values copy-paste karo:

| Key | Value |
|-----|-------|
| `NEXT_PUBLIC_SUPABASE_URL` | `https://xxxx.supabase.co` |
| `NEXT_PUBLIC_SUPABASE_ANON_KEY` | `eyJhbGc...` (lambi string) |

3. **Add** karo

### Step 5: Deploy!

**"Deploy"** button dabao → 2-3 minute wait karo → 🎉 App Live!

Vercel ek URL dega jaise: `https://kharcha-tracker-pro.vercel.app`

### Step 6: Live App Test Karo

1. URL par jao
2. Register karo → Login karo → Expense add karo
3. Sab kaam kar raha hai? ✅ Mubarak ho! 🎊

---

## 9. 💻 Commands Cheat Sheet

Yeh sab terminal mein chalti hain:

### Basic Commands

| Kaam | Command |
|------|---------|
| Project clone karna | `git clone <github-url>` |
| Folder mein jaana | `cd folder-name` |
| App shuru karna (test) | `npm run dev` |
| Naya package install karna | `npm install package-name` |
| Packages install karna (first time) | `npm install` |

### Git Commands (Code Save Karna)

| Kaam | Command |
|------|---------|
| Saari files stage karna | `git add .` |
| Code save karna (label ke saath) | `git commit -m "kya kiya"` |
| GitHub par bhejna | `git push origin main` |
| Stage + Commit ek saath | `git commit -am "message"` |

### 🚨 Emergency Commands

| Situation | Command |
|-----------|---------|
| **AI ne code toda, wapas lana hai** | `git restore .` |
| **Purana version dekhna** | `git log --oneline` |
| **Kisi commit par wapas jaana** | `git checkout COMMIT-ID` |

### Supabase CLI (Advanced)

```bash
# Supabase CLI install karo
npm install -g supabase

# Login karo
supabase login

# Local development start karo (optional)
supabase start
```

---

## 10. 🆘 Emergency Guide — Jab Sab Toot Jaye

### Problem 1: AI Galat Code De Raha Hai

**Solution:**
```bash
git restore .
```
Yeh aapka code last commit par wapas le aayega. Phir AI se nayi chat mein try karo.

### Problem 2: npm run dev Chala Nahi

**Solution:**
```bash
# Pehle yeh try karo
npm install

# Phir chalao
npm run dev
```

### Problem 3: Supabase Connection Error

**Check karo:**
1. `.env.local` file exist karti hai root mein?
2. Keys sahi copy ki hain? (koi extra space toh nahi?)
3. Supabase Dashboard par project active hai?

### Problem 4: Vercel Par Deploy Fail Hua

**Check karo:**
1. Environment Variables sahi daale hain?
2. `npm run build` locally chala kar dekho — koi error?
   ```bash
   npm run build
   ```

### Problem 5: AI Ki Memory Full Ho Gayi (Weird Answers)

**Signs:**
- AI wahi code baar baar likh raha hai
- AI keh raha hai "I don't have access to your files"
- Bahut ajeeb ya galat code de raha hai

**Solution:** Nayi chat shuru karo aur likho:
```
Read PROJECT_BLUEPRINT.md and TASKS.md.
I'm working on [MODULE NAME]. Here's the current error/task: [DESCRIBE]
```

### Problem 6: "Port 3000 Already in Use" Error

```bash
# Mac/Linux
kill -9 $(lsof -ti:3000)

# Windows
netstat -ano | findstr :3000
taskkill /PID [NUMBER] /F

# Phir chalao
npm run dev
```

---

## 🎁 Bonus: Best Prompts Collection

### AI se Pehli Baar Milna
```
Mera PROJECT_BLUEPRINT.md aur TASKS.md padho.
Mujhe [FEATURE] banana hai. Mujhe step by step batao 
kya karna hai, aur code likhdo. Main ek non-technical 
founder hun, simple language mein samjhao.
```

### Error Fix Karna
```
Mujhe yeh error aa raha hai:
[ERROR PASTE KARO]

Yeh context hai:
- Main [KYA KAR RAHA THA]
- File: [FILENAME]

Root cause kya hai aur kaise fix karein?
```

### Review Karna
```
Mera [FEATURE] ban gaya hai. Koi security issue,
performance problem, ya better approach batao.
Supabase RLS sahi se lagi hai?
```

### Nayi Feature Add Karna
```
TASKS.md mein [TASK NUMBER] karna hai.
Pehle plan batao, phir code likho.
Testing ke steps bhi batao.
```

---

## ✅ Final Checklist — App Launch Se Pehle

```
□ TASKS.md ke sab modules complete hain
□ App localhost par theek chal raha hai
□ Login/Register kaam kar raha hai
□ Data sirf login user ko dikha raha hai (RLS check)
□ Mobile par bhi theek dikha raha hai
□ .env.local GitHub par nahi gaya (check karo!)
□ Vercel mein Environment Variables daale hain
□ Live URL par test kiya
□ Domain liya (optional: namecheap.com / godaddy.com)
```

---

## 🏁 Conclusion

Aapne seekha:
- **AI Editor** kaise chunna hai (Cursor / Windsurf / VS Code)
- **GitHub** se project manage karna
- **Next.js 16** setup karna
- **Supabase** se database aur auth connect karna
- **RLS** se data secure rakhna
- **Vercel** par deploy karna

**Ab sirf ek kaam bacha hai — Shuru Karo! 🚀**

---

*Document Version: May 2026 | Next.js 16 | Supabase 2026 | Cursor/Windsurf/VS Code*

*Maintained by: [Aapka Naam]*
