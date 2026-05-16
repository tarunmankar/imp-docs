# 🤖 AI-First Development: Complete Workflow Bible
### *Har Cheez Ek Jagah — GitHub-Ready — Production-Grade*

> **"Aap Vision set karo. AI execution sambhale. Aap Architect raho, AI Engineer bane."**

---

## 📑 Table of Contents

| # | Section |
|:--|:--------|
| 1 | [🧠 Core Philosophy — AI-First Kya Hai?](#1--core-philosophy) |
| 2 | [📁 The Architect Pattern — `.ai/` Folder Setup](#2--the-architect-pattern) |
| 3 | [⚙️ `.antigravityrules` + `README.md` — Exact Templates](#3--antigravityrules--readmemd-exact-templates) |
| 4 | [📄 8 Files Ka Complete Blueprint](#4--8-files-ka-complete-blueprint) |
| 5 | [🔄 Correct Workflow Order — Step by Step](#5--correct-workflow-order-step-by-step) |
| 6 | [🤖 Human vs AI — Kya Manually Karna Hai?](#6--human-vs-ai-responsibility-matrix) |
| 7 | [🛑 Halt & Ask Rule — Sabse Important Control](#7--halt--ask-rule) |
| 8 | [🚫 AI Auto-Commit Problem + 3-Level Solution](#8--ai-auto-commit-problem--3-level-solution) |
| 9 | [🔒 Git & GitHub Safety Protocol](#9--git--github-safety-protocol) |
| 10 | [📜 Master Prompts Library — Copy-Paste Ready](#10--master-prompts-library) |
| 11 | [🌐 Supabase / Firebase Adaptation](#11--supabase--firebase-cloud-adaptation) |
| 12 | [🖥️ Multi-IDE Compatibility — Antigravity, Cursor, Copilot...](#12--multi-ide-compatibility) |
| 13 | [🧭 Tech Stack Decision Matrix](#13--tech-stack-decision-matrix) |
| 14 | [📊 Project Type → Language & DB Guide](#14--project-type--language--db-guide) |
| 15 | [⚖️ React Native vs Flask vs Android](#15--react-native-vs-flask-vs-android) |
| 16 | [🗓️ Daily Workflow Routine](#16--daily-workflow-routine) |
| 17 | [✅ Final Pre-Flight Checklist](#17--final-pre-flight-checklist) |
| 18 | [💡 Smart Workflow Benefits](#18--smart-workflow-benefits) |

---

## 1. 🧠 Core Philosophy

### AI-First Development Kya Hai?

Traditional development: Developer pehle code likhta hai → phir AI se madad maangta hai.

**AI-First:** Aap pehle rules, constraints, aur vision define karte ho → AI woh rules padh kar structured code generate karta hai → Aap sirf **approve aur test** karte ho.

```
❌ Old Way:
"AI, yeh bug fix karo." → AI guesses context → Random output → Aap confuse

✅ AI-First Way:
00_PRD.md (Vision) + AGENTS.md (Laws) + TASKS.md (Tasks)
→ AI sab padh kar → Predictable, correct, on-track output
```

### Yeh Workflow Kyun Zaroori Hai?

| Problem (Without Workflow) | Solution (With AI Foundation Files) |
|:--------------------------|:-------------------------------------|
| AI baar-baar context bhool jaata hai | `.ai/` folder mein permanently locked context |
| Code inconsistent — kabhi Tailwind, kabhi inline | `AGENTS.md` ke strict styling rules |
| AI khud se features add karta hai | `00_PRD.md` constraints scope creep rokते hain |
| Same bug baar baar repeat hoti hai | `ERROR_LOGS.md` AI ki permanent memory bank |
| AI galat direction mein chala jaata hai | `Halt & Ask` — har step par human approval |
| Stack confusion — Firebase vs SQLite | `00_PRD.md` mein explicitly defined hai |

---

## 2. 📁 The Architect Pattern

### AI IDEs Sabse Pehle Kya Padhte Hain?

Antigravity, Cursor, GitHub Copilot jaise tools yeh scan karte hain:
1. **`README.md`** — Standard entry point
2. **`package.json`** — Tech stack & commands
3. **`.antigravityrules` / `.cursorrules`** — Persistent AI directives
4. **`.ai/` folder** — Agar `README.md` mein mention ho

**Solution — "The Architect Pattern":**
Saari AI instruction files ek dedicated `.ai/` folder mein rakho. `README.md` AI ko wahan bhejo.

### 📂 Final Recommended Folder Structure

```text
project-root/
├── .ai/                         🔒 AI Brain Folder
│   ├── 00_PRD.md                🧠 Master Seed (AAPNE likhna hai)
│   ├── ARCHITECTURE_MASTER.md   ⚙️  Engine & wiring
│   ├── SCHEMA.md                🗃️  Database blueprint
│   ├── AGENTS.md                📜 Constitution / Laws
│   ├── GEMINI.md                💻 IDE / Environment rules
│   ├── PROJECT_BLUEPRINT.md     🗺️  Folder map & screens
│   ├── TASKS.md                 📋 Daily to-do list (phased)
│   └── ERROR_LOGS.md            🐛 Memory bank (khali shuru)
│
├── .antigravityrules            ⚡ Persistent AI rules (auto-loads)
├── README.md                    📖 Entry point → .ai/ ka context map
├── .gitignore                   🚫 node_modules/, .env*, dist/, *.sqlite
├── package.json / requirements.txt
└── src/                         💻 Actual Application Code
    ├── /features/               🧩 Isolated modules (billing, inventory)
    ├── /shared/                 🔗 Common (components, utils, hooks)
    └── /main/                   🏠 Entry / Backend
```

> [!TIP]
> `ai-context/` (without dot) use karein agar koi tool hidden `.ai/` folder scan nahi karta.

> [!WARNING]
> **Project path mein KABHI SPACE mat rakho.**
> `D:\dev\my-app` ✅ | `C:\My Projects\App` ❌
> Space hone se SQLite paths, npm scripts, aur AI indexing sab break hote hain.

---

## 3. ⚙️ `.antigravityrules` + `README.md` Exact Templates

### ⚡ `.antigravityrules` — Root Mein Banao

Yeh file Antigravity/Cursor jaise IDEs **har naye session ke start par automatically load** karte hain.

```markdown
# 🤖 AI AGENT DIRECTIVES

1. ALWAYS load & read ALL files in `.ai/` before generating any code.
2. STRICTLY enforce `.ai/AGENTS.md` rules — especially "Halt & Ask".
3. NEVER execute `git add`, `git commit`, or `git push` automatically.
4. NEVER write directly to `main` branch. Use `feat/*` or `fix/*` only.
5. If any instruction conflicts with `.ai/AGENTS.md`, follow `.ai/AGENTS.md`.
6. Use English for code. Hinglish for complex logic comments.
7. Tailwind v4 utility classes ONLY. Zero inline `style={{}}`.
8. When in doubt: HALT → Report status → Ask for explicit permission.
```

> `.antigravityrules` detect na ho toh `.cursorrules` naam se rename karo — dono same spec follow karte hain.

---

### 📖 `README.md` — Root Mein Banao

```markdown
# 🚀 [Your Project Name]

> 🤖 **AI AGENT INSTRUCTIONS:**
> Before starting ANY task, read ALL files in the `.ai/` directory.
> They contain the complete blueprint, schema, behavioral rules, and tasks.
> Do NOT proceed without loading `.ai/00_PRD.md` and `.ai/AGENTS.md` first.

## 🛠️ Quick Start
```bash
npm install
npm run dev
```

## 📚 AI Context Files (`.ai/` folder)
| File | Purpose |
|:-----|:--------|
| `00_PRD.md` | Master requirements & vision (Human-written) |
| `AGENTS.md` | Behavioral rules — Halt & Ask, Git safety, Styling |
| `TASKS.md` | Current execution checklist |
| `SCHEMA.md` | Database design & security rules |
| `ARCHITECTURE_MASTER.md` | Tech stack & data flow |
| `ERROR_LOGS.md` | Past bugs — DO NOT repeat |

## ⚠️ Important Rules
- 🚫 Project path NO SPACES (`D:\dev\myapp` ✅)
- 🛑 AI follows "Halt & Ask" — always review diffs before approving
- 🔄 `main` is protected — AI only creates PRs to feature branches
```

---

### 🔍 Verify Karein — AI Sahi Context Load Kar Raha Hai?

Chat mein likhein:
```
"List all files in .ai/ and summarize the current task from .ai/TASKS.md"
```
Agar AI correct files & task dikhata hai → ✅ Setup perfect hai.

---

## 4. 📄 8 Files Ka Complete Blueprint

### 🧠 `00_PRD.md` — The Master Seed *(Sirf Aapka Kaam)*

> [!IMPORTANT]
> Yeh **sabse pehli** file hai. **Sirf aap** likhte hain. Baaki 6 files AI is ek file ko base maan kar generate karta hai. Jitna detailed, utna accurate output.

| Section | Description | Example |
|:--------|:------------|:--------|
| 🏷️ **App ka Naam & Vision** | 1 line description | *Shree Ram Medical Billing — Offline pharmacy POS* |
| 👥 **Target Audience** | Kaun, kahan, kaise | *Non-tech users, Windows PC, no internet* |
| ⚙️ **Strict Tech Stack** | Exact technologies + versions | *Electron JS, React+Vite, SQLite, Tailwind v4, Zustand* |
| 📦 **Core Features** | Point-wise must-haves | *Inventory, POS, barcode scan, PDF export, low stock alerts* |
| 🚫 **Business Constraints** | Rules jo AI kabhi nahi todega | *Invoice soft-delete only. Stock never negative. No Firebase.* |
| 🤖 **Agentic Preferences** | Coding style & environment | *Comments Hinglish mein. Windows + Antigravity IDE.* |

**🔮 The Magic Prompt — File ke ekdum end mein paste karein:**
```text
AI Instruction: Read this 00_PRD.md very carefully and generate 
ARCHITECTURE_MASTER.md, SCHEMA.md, AGENTS.md, GEMINI.md, 
PROJECT_BLUEPRINT.md, and TASKS.md based on these exact requirements.
```

---

### ⚙️ `ARCHITECTURE_MASTER.md` — Single Source of Truth *(AI Generate Karega)*

Project ka **engine aur wiring**. AI code likhte waqt ise base maanta hai.

- **Tech Stack Summary** — All libraries + exact versions
- **Data Flow Diagram:**
  - Offline: `React Component → IPC Renderer → IPC Main → SQLite`
  - Cloud: `React/Vite → Supabase SDK → PostgreSQL (RLS)`
  - Mobile: `Composable UI → ViewModel → Repository → Room DAO`
- **State Management** — `useState` (local) vs `Zustand/Redux` (global) kab
- **Security Rules** — PIN login? Encryption? `anon` key only (Supabase)?
- **Naming Conventions:**
  - Components → `PascalCase.jsx`
  - Utils/Hooks → `camelCase.js`
  - DB Columns → `snake_case`

---

### 🗃️ `SCHEMA.md` — Database Blueprint *(AI Generate Karega)*

**Sirf database ka naksha.** Koi extra cheez nahi.

**SQLite / Offline Example:**
```sql
CREATE TABLE products (
  id        INTEGER PRIMARY KEY AUTOINCREMENT,
  name      TEXT    NOT NULL,
  barcode   TEXT    UNIQUE,
  price     REAL    DEFAULT 0,
  stock_qty INTEGER DEFAULT 0 CHECK (stock_qty >= 0)
);
CREATE INDEX idx_products_barcode ON products(barcode);
```

**Supabase / PostgreSQL Example:**
```sql
CREATE TABLE public.products (
  id         UUID    DEFAULT uuid_generate_v4() PRIMARY KEY,
  sku        TEXT    UNIQUE NOT NULL,
  name       TEXT    NOT NULL,
  price      NUMERIC(10,2) CHECK (price >= 0),
  stock_qty  INTEGER DEFAULT 0 CHECK (stock_qty >= 0),
  created_at TIMESTAMPTZ DEFAULT now()
);

-- Row Level Security (MANDATORY for Supabase):
ALTER TABLE public.products ENABLE ROW LEVEL SECURITY;
CREATE POLICY "Admins can manage products" ON public.products
  FOR ALL USING (
    EXISTS (SELECT 1 FROM profiles WHERE id = auth.uid() AND role = 'admin')
  );
```

**Strict Rules:**
- SQLite → `NO UUIDs`. Standard `INTEGER AUTOINCREMENT` only
- Supabase → `UUID` + `RLS` mandatory on ALL tables
- Firebase → NoSQL Collections + `firestore.rules` format

---

### 📜 `AGENTS.md` — The Constitution *(AI Generate Karega)*

> [!IMPORTANT]
> Yeh project ka **samvidhan** hai. Koi bhi AI, koi bhi session — yeh rules kabhi nahi todega.

**🛑 TOP PRIORITY — The Halt & Ask Rule:**
```
"Never proceed to the next task automatically.
 Always stop, report test status, and ask for permission."
```

**Mandatory Coding Rules:**
```
✅ Always use functional components. No class components.
✅ Only Tailwind v4 utility classes. Zero inline style={{}}.
✅ Code in English. Complex logic explain in Hinglish comments.
✅ One component = One file. Max 150 lines per file.
✅ No spaghetti code. One module = One concern.
```

**Git Safety Rules (Non-Negotiable):**
```
🚫 NEVER run git add, commit, push, or merge automatically.
🚫 NEVER write to `main` branch directly.
🚫 NEVER git push --force.
✅ Always show diff + suggest commit message → ask "Proceed?"
✅ Only execute git commands after explicit "Yes/Proceed".
✅ Always use feat/*, fix/*, docs/*, hotfix/* branches.
```

---

### 💻 `GEMINI.md` — Environment / IDE Overrides *(AI Generate Karega)*

Antigravity ya kisi bhi AI IDE ke liye specific environment rules.

```markdown
- Artifacts: "Create Implementation Plan before writing/modifying code."
- Terminal: "Use Windows PowerShell. No paths with spaces."
- Ports: "Vite → 5173. Busy? Auto-switch to 5174."
- Git: "READ-ONLY git status/diff only. ALL commits need explicit approval."
- Auto-commit blocked: "If auto-push triggers, HALT → report → wait for command."
- Sub-agents: "For DB + UI tasks: DB first, then UI. Ask confirmation before running."
```

---

### 🗺️ `PROJECT_BLUEPRINT.md` — The Map *(AI Generate Karega)*

Folders aur screens ki list — AI galat jagah file nahi banayega.

```text
/src
├── /features              # Isolated modules
│   ├── /billing           # BillingScreen, BillingViewModel, BillingRepo
│   └── /inventory         # InventoryPage, InventoryRepo
├── /shared                # Common reusable code
│   ├── /components        # Buttons, Inputs, Modals, DataTable
│   ├── /utils             # Formatters, Validators, Loggers
│   └── /hooks             # Custom React hooks
└── /main                  # Electron backend / Entry point
```

**Routing Map:**
- `/ → Dashboard.jsx`
- `/billing → BillingMain.jsx`
- `/inventory → InventoryPage.jsx`

**Core Components to Build First:**
`Sidebar`, `TopNav`, `LayoutWrapper`, `DataTable`, `ModalDialog`

---

### 📋 `TASKS.md` — The Execution Checklist *(AI Generate Karega)*

| Phase | Kya Hoga |
|:------|:---------|
| Phase 1 | 🏗️ Foundation — Init, Tailwind, IPC, Base layout, Git setup |
| Phase 2 | 🗄️ DB Init — Connection, Tables from SCHEMA, Seed data |
| Phase 3 | 🧩 Feature Modules — Feature-by-feature, UI + logic |
| Phase 4 | 🧪 Testing & Deploy — Build, sign, CI/CD, deploy |

**Har Task Ka Format:**
```
Task ID      : 2.1
Goal         : Create SQLite connection & run schema
Target File  : src/main/db.js
Test Condition: Run app → verify DB file created at /data/app.db → SELECT 1 returns success
```

---

### 🐛 `ERROR_LOGS.md` — The Memory Bank *(Shuru Mein Khali)*

Har bug fix ke baad AI ise update karega taaki same mistake repeat na ho.

```markdown
### 🐛 Bug: 2025-06-15 | 14:32
* **Module:** Billing PDF Generator
* **Error:** TypeError: Cannot read property 'map' of undefined
* **Root Cause:** invoice_items fetch se pehle render ho raha tha
* **The Fix:** Added null check + loading state before .map() call
* **Status:** ✅ Resolved
```

---

## 5. 🔄 Correct Workflow Order (Step by Step)

> [!WARNING]
> **Pehle `npm create` ya scaffolding mat karo.** Pehle `00_PRD.md` likho — AI khud sahi commands suggest karega.

---

### 🟦 STEP 0 — Environment Setup *(100% Aapka Kaam)*

**Kya karna hai:**

1. Ek naya folder banao — **path mein koi SPACE nahi honi chahiye**
   - ✅ `D:\dev\my-billing-app`
   - ❌ `C:\My Projects\Billing App`

2. Terminal/PowerShell us folder mein kholo aur yeh commands chalaao:
   ```bash
   git init
   ```

3. `.gitignore` file banao, andar yeh likho:
   ```
   node_modules/
   .env*
   dist/
   *.sqlite
   .DS_Store
   ```

4. `.ai/` folder banao aur andar 8 khali files banao:
   ```
   .ai/00_PRD.md
   .ai/ARCHITECTURE_MASTER.md
   .ai/SCHEMA.md
   .ai/AGENTS.md
   .ai/GEMINI.md
   .ai/PROJECT_BLUEPRINT.md
   .ai/TASKS.md
   .ai/ERROR_LOGS.md
   ```

5. Root mein `.antigravityrules` file banao — Section 3 ka exact content paste karo

6. Root mein `README.md` file banao — Section 3 ka exact template paste karo

7. GitHub par naya repo banao (private ya public)

8. Yeh commands chalaao:
   ```bash
   git add .
   git commit -m "chore: init project structure"
   git branch -M main
   git remote add origin https://github.com/AAPKA-USERNAME/REPO-NAAM.git
   git push -u origin main
   ```

9. GitHub par `main` branch protect karo:
   - Repo → **Settings → Branches → Add rule**
   - ✅ Require a pull request before merging
   - ✅ Require 1 approval
   - ❌ Allow force pushes → OFF karo

**✅ Verify karein:**
- `git status` → "nothing to commit" aana chahiye
- GitHub par main branch ke paas 🔒 icon dikhna chahiye
- `.ai/` folder mein 8 files honi chahiye

---

### 🟩 STEP 1 — `00_PRD.md` Fill Karo *(100% Aapka Kaam)*

> 💡 Yeh sabse important step hai. Jitna detailed likhoge, utna accurate AI output milega.

**Kya karna hai:**

1. `.ai/00_PRD.md` file kholo

2. Yeh sections fill karo — **apne project ke hisaab se:**
   ```markdown
   ## 🏷️ App ka Naam & Vision
   Name: [Aapke project ka naam]
   Vision: [Ek line mein — kya problem solve karta hai?]

   ## 👥 Target Audience & Environment
   Users: [Kaun use karega?]
   Environment: [Web / Desktop / Mobile? Online / Offline?]

   ## ⚙️ Strict Tech Stack
   Frontend: [React + Vite / Next.js / React Native]
   Styling: [Tailwind v4]
   Backend/DB: [Supabase / SQLite / Firebase / Flask]
   Hosting: [Vercel / Netlify / Electron / Play Store]

   ## 📦 Core Features (Must-Haves)
   - [ ] Feature 1
   - [ ] Feature 2
   - [ ] Feature 3

   ## 🚫 Business Constraints (AI kabhi nahi todega)
   - Invoice soft-delete only, kabhi hard delete nahi
   - Stock negative nahi jaana chahiye
   - No Firebase / No Cloud (agar offline chahiye)

   ## 🤖 Agentic Preferences
   - Comments: Hinglish mein
   - IDE: Antigravity + Windows OS
   - Testing: Manual verify
   ```

3. File ke **bilkul end mein** yeh Magic Prompt paste karo:
   ```
   AI Instruction: Read this 00_PRD.md very carefully and generate
   ARCHITECTURE_MASTER.md, SCHEMA.md, AGENTS.md, GEMINI.md,
   PROJECT_BLUEPRINT.md, and TASKS.md based on these exact requirements.
   ```

4. File save karo, phir Git mein commit karo:
   ```bash
   git add .ai/00_PRD.md
   git commit -m "docs: add master PRD"
   git push
   ```

**✅ Verify karein:**
- PRD ko khud 2 baar padho — kya tech stack clear hai?
- Constraints unambiguous hain?
- Magic Prompt file ke end mein hai?

---

### 🟨 STEP 2 — AI Se Foundation Files Generate Karwao

**Kya karna hai:**

1. Apna AI tool kholo (Antigravity / Cursor / Claude / Copilot)

2. **Master Prompt #1** paste karo (Section 10 mein diya hua hai)

3. AI `00_PRD.md` padhega aur yeh generate karega:
   - Exact `npm create...` terminal commands
   - 6 foundation files ka complete content

4. AI ke diye hue **terminal commands** copy karke run karo:
   ```bash
   # AI jo commands dega, woh kuch aisi hongi:
   npm create vite@latest . -- --template react-ts
   npm install
   npm install tailwindcss zustand
   # (exact commands aapke PRD ke hisaab se different hongi)
   ```

5. AI ke generate kiye hue 6 files ka content copy karke `.ai/` folder ki respective files mein paste karo aur save karo

6. Git mein commit karo:
   ```bash
   git checkout -b feat/init-ai-context
   git add .
   git commit -m "docs: generate AI foundation files & scaffold project"
   git push origin feat/init-ai-context
   ```

7. GitHub par is branch ka **Pull Request** banao → Review karo → `main` mein merge karo

**✅ Verify karein:**
- `.ai/AGENTS.md` kholo — "Halt & Ask" rule present hai?
- `.ai/TASKS.md` kholo — Phase 1, Phase 2 tasks hain?
- `.ai/SCHEMA.md` kholo — Database tables/entities hain?
- `package.json` kholo — correct dependencies hain?

---

### 🟧 STEP 3 — Phase 1 Execute Karo (Foundation & DB)

**Kya karna hai:**

1. `.ai/TASKS.md` kholo → **Phase 1, Task 1.1** ka content copy karo

2. AI ko **Master Prompt #2** do (Section 10 mein diya hua) — Task ID, Goal, Target File paste karo

3. AI code generate karega aur **ruk jaayega** (Halt & Ask) — yeh dikhega:
   ```
   ✅ Task 1.1 Complete. Changes made in: src/main/db.js
   🧪 Test: App start karo, DB file /data/app.db create hogi.
   🛑 HALT. Task 1.2 shuru karu? Proceed?
   ```

4. AI ka generate kiya hua diff review karo

5. Terminal mein app run karo:
   ```bash
   npm run dev
   ```

6. TASKS.md ki **Test Condition** manually verify karo — DB file bani? Connection hua?

7. Sab theek ho toh AI ko bolo: `"✅ Approved. Commit to feat/phase1-db and push."`

8. AI commit message suggest karega — aap yeh commands chalaao:
   ```bash
   git add .
   git commit -m "feat: init db connection & config"
   git push origin feat/phase1-db
   ```

9. GitHub PR banao → merge karo → agle task par jao

**✅ Verify karein:**
- App bina crash ke chal rahi hai?
- DB file/connection verify hua?
- AI ne bina pooche commit nahi kiya?
- `main` branch untouched hai?

---

### 🟥 STEP 4 — Features Build Karo (Repeat karo har task ke liye)

**Yeh loop har feature ke liye repeat karo:**

1. `.ai/TASKS.md` se **next task** lo

2. AI ko **Master Prompt #2** do — task details paste karo

3. AI code likhega → **Halt & Ask** karega

4. Code diff review karo

5. TASKS.md ki Test Condition verify karo:
   - UI render hua? Tailwind apply hua?
   - Button click → expected action?
   - DB insert/update successful?

6. **Bug aaya?** AI ko yeh bolo:
   ```
   🐛 Bug: [exact error message]
   Log this in .ai/ERROR_LOGS.md with date, root cause, and fix.
   Fix the bug, test again, then Halt & Ask.
   ```

7. Sab pass ho toh approve karo aur commit karo:
   ```bash
   git checkout -b feat/task-[number]
   git add .
   git commit -m "feat: add [feature name]"
   git push origin feat/task-[number]
   ```

8. GitHub PR → review → merge → agle task par jao

9. **Context lost lag raha ho?** Yeh prompt do:
   ```
   🔄 Context Refresh: Re-read all .ai/ files. Resume from last approved task.
   ```

---

### 🟪 STEP 5 — Deploy Karo

**Kya karna hai:**

1. AI ko bolo: `"Help me configure deployment for [Vercel / Netlify / Electron]"`

2. AI build config aur steps suggest karega — aap run karo:
   ```bash
   npm run build
   ```

3. `.env` variables production mein set karo

4. Deploy karo (Vercel/Netlify par push, ya Electron installer banao)

5. Live verify karo — app chal rahi hai? Auth/DB kaam kar raha hai?

6. Production release tag karo:
   ```bash
   git tag v1.0.0
   git push origin v1.0.0
   ```

7. GitHub par **Release** banao

**✅ Verify karein:**
- `npm run build` → 0 errors/warnings?
- Live URL/app load ho rahi hai?
- DB sync/auth kaam kar raha hai?

---

## 6. 🤖 Human vs AI Responsibility Matrix

| Task | 🧑‍💻 Human (Manual) | 🤖 AI (Assisted / Auto) |
|:-----|:------------------|:----------------------|
| Vision & Business Rules | ✅ PRD likhna, constraints set | ❌ Nahi |
| Folder Structure & Git Init | ✅ `git init`, `.gitignore`, remote | ❌ Nahi |
| Foundation Files (`.ai/`) | ✅ Prompt dena, output save | ✅ Generate karta hai |
| Code Writing & Logic | ✅ Review, approve, test | ✅ Feature-by-feature code |
| DB Schema & Queries | ✅ Approve, run migrations | ✅ SQL/ORM structure, indexes, RLS |
| Git Operations | ✅ Branch switch, PR create, merge | ✅ Suggest only — execute nahi bina approval |
| Testing & Debugging | ✅ Run app, verify, approve | ✅ Test scripts suggest, `ERROR_LOGS.md` update |
| Deployment | ✅ CI/CD setup, env vars, push | ✅ Build config & steps draft |

---

## 7. 🛑 Halt & Ask Rule

**Yeh rule kisi IDE ki setting nahi — yeh AI behavior control prompt hai.**

### Kaise Kaam Karta Hai?

```
1. HALT   → Task complete hote hi AI ruk jaata hai

2. REPORT → AI batata hai:
              ✅ Kya bana/modify kiya?
              🧪 Kaise test kiya? Result?
              ⚠️ Koi warning ya alternative?

3. ASK    → "Task 2.1 complete. Next: Task 2.2 shuru karu?"

4. YOU DECIDE:
              "Proceed"           → AI next task shuru karta hai
              "Pehle yeh fix karo" → AI changes karega
              "Explain step Z"    → AI explain karega
```

### Real Example:

```
🤖 AI Output:
✅ Task 2.1 Complete: SQLite connection established.
   DB file created at /data/app.db
🧪 Test: SELECT 1 → Success. Connection stable.
🛑 HALT. Task 2.2 (SCHEMA tables create karna) shuru karu?

👤 Options:
  → "Yes, proceed."
  → "Pehle ek dummy table bana ke dikhao."
  → "Ruko, foreign key constraints pehle review karo."
```

### AI Bina Pooche Aage Badh Jaye Toh:

```
⚠️ STOP. You violated the "Halt & Ask" rule from AGENTS.md.
   Do NOT proceed further.
   Report what you just did, show diff, and wait for my approval.
```

### Har Tool Mein Kaam Karega?

**Haan.** Jab tak `AGENTS.md` ya system prompt mein yeh line hai:
> `"Never proceed automatically. Stop, report status, and ask for explicit permission before next task."`

...tab tak **koi bhi AI** (Antigravity, Cursor, Copilot, Claude, Gemini) ise follow karega.

---

## 8. 🚫 AI Auto-Commit Problem + 3-Level Solution

Kuch AI IDEs by default auto-commit/push kar dete hain. Iska solution 3 levels par hai:

### Level 1 — AGENTS.md / System Prompt Mein Add Karein

```markdown
🚫 STRICT GIT RULE (NON-NEGOTIABLE):
"Never run git add, git commit, git push, or git sync automatically.
 Only generate the commit message & diff summary, then ask:
 '✅ Changes ready. Shall I commit & push to GitHub?'
 Wait for explicit 'Yes/Proceed' before executing any git command."
```

### Level 2 — GEMINI.md / IDE Settings Update

```markdown
🔒 GIT PERMISSION OVERRIDE:
- AI can ONLY run `git status` & `git diff` for review.
- ALL commit/push actions require explicit human approval.
- If auto-push is triggered by tool config, HALT immediately
  and report: "⚠️ Auto-commit blocked by AGENTS.md rule."
```

**IDE Settings:**

| Tool | Setting | Action |
|:-----|:--------|:-------|
| Cursor / Copilot | `Auto-Commit / Auto-Push` | ❌ Disable in Settings → AI → Git Actions |
| Antigravity | `Agent Git Permissions` | 🔒 Set to `Read-Only` or `Ask Every Time` |
| GitHub CLI | `GITHUB_TOKEN` scope | 🔐 Limit to `pull_request` only, disable `contents: write` |

### Level 3 — GitHub Branch Protection (Fallback Safety)

```
Repo Settings → Branches → main → Add rule:
  ✅ Require a pull request before merging
  ✅ Require 1 approval
  ❌ Allow force pushes → DISABLE
  🔒 Restrict who can push → Sirf aapka account
```

### AI Ka Correct Git Flow (After Fixes):

```
1. Code generate karo
2. `git status` & `git diff --stat` dikhao
3. Suggested conventional commit message do
4. 🛑 HALT & ASK: "Commit & push karu? Branch: feat/xyz"
5. Aap "Yes" bole → Tab hi AI git commands run karega
```

---

## 9. 🔒 Git & GitHub Safety Protocol

### Branch Strategy:

| Branch | Purpose | Example |
|:-------|:--------|:--------|
| `feat/*` | Naya feature | `feat/task-2.1-inventory-db` |
| `fix/*` | Bug fix | `fix/stock-negative-crash` |
| `docs/*` | Documentation | `docs/update-schema-rls` |
| `hotfix/*` | Emergency | `hotfix/invoice-null-pointer` |
| `main` | **PRODUCTION ONLY** | Sirf approved PRs se update |

### Conventional Commit Messages:

```
feat: add barcode scanner to inventory screen
fix: prevent stock quantity from going negative
docs: update SCHEMA.md with Supabase RLS policies
chore: update npm dependencies
refactor: split billing into sub-components
```

### Git Workflow Summary:

```
New Feature:
  git checkout -b feat/feature-name
  [AI generates code → you review]
  git add .
  git commit -m "feat: description"
  git push origin feat/feature-name
  [Create PR on GitHub → Review → Merge to main]

Bug Fix:
  git checkout -b fix/bug-name
  [AI fixes → logs in ERROR_LOGS.md → you verify]
  git commit -m "fix: description"
  git push → PR → Merge
```

---

## 10. 📜 Master Prompts Library

### 🔹 Prompt #1 — PRD Read + Foundation Generate

```text
📚 Context Load: Read .ai/00_PRD.md carefully.

Based on this PRD:
1. Suggest EXACT terminal commands to scaffold the project
   (npm create..., npm install, .gitignore content, folder structure)
2. Generate these files inside .ai/:
   - ARCHITECTURE_MASTER.md
   - SCHEMA.md
   - AGENTS.md (include "Halt & Ask" + strict Git safety rules)
   - GEMINI.md
   - PROJECT_BLUEPRINT.md
   - TASKS.md (phased with Task ID, Goal, Target File, Test Condition)

📤 Output only file contents and setup commands.
   Do NOT run any git/npm commands automatically.
```

### 🔹 Prompt #2 — Task Execute (Git-Integrated)

```text
🎯 Task: [TASKS.md se copy: Task ID + Goal + Target File]

📚 References:
- .ai/ARCHITECTURE_MASTER.md (tech stack & data flow)
- .ai/SCHEMA.md (DB design — if DB related)
- .ai/AGENTS.md (coding rules — strictly follow)
- .ai/PROJECT_BLUEPRINT.md (folder structure)

🌿 Git Flow: Switch to feat/[task-slug]. Create from main if new.
⚠️ Rules: Follow AGENTS.md. Tailwind v4. Hinglish comments. Zero inline CSS.

🛑 After coding:
1. Show diff (file-by-file)
2. Run test condition, share result
3. Suggest conventional commit message
4. Ask: "✅ Ready to commit & push to feat/[slug]? Proceed?"
```

### 🔹 Context Refresh Prompt

```text
🔄 Context Refresh:
Re-read ALL files in .ai/ folder:
00_PRD.md, ARCHITECTURE_MASTER.md, AGENTS.md, TASKS.md, SCHEMA.md, ERROR_LOGS.md

Confirm once loaded. Resume from last approved task in TASKS.md.
```

### 🔹 Bug Fix + Log Prompt

```text
🐛 Bug: [Exact error message from console/logcat]

📚 Ref: .ai/ERROR_LOGS.md, .ai/SCHEMA.md
🎯 Fix → Test locally → Log in ERROR_LOGS.md:
   - Date/Time
   - Module name
   - Root cause
   - Fix applied
🛑 Halt & Ask before committing.
```

### 🔹 PR Ready Suggestion

```text
📦 PR Ready:
- Branch: feat/[task-slug]
- Changes: [AI summary of what changed]
- Suggested commit: feat: [description]

🛑 WAIT for my review. Do NOT merge.
   I will handle PR creation & merge manually.
```

### 🔹 Halt & Ask Enforcement

```text
⚠️ STOP. You violated the "Halt & Ask" rule from AGENTS.md.
   Do NOT proceed further.
   Report: 1) What you just did  2) Diff  3) Any issues
   Then wait for my explicit "Proceed" command.
```

---

## 11. 🌐 Supabase / Firebase Cloud Adaptation

Yeh workflow kisi specific stack se bound nahi hai. Cloud apps ke liye **sirf andar ka content adjust hota hai — structure, rules, aur workflow 100% same rehta hai.**

### Kya Change Hoga?

| File | Offline/Desktop | Supabase/Firebase (Cloud) |
|:-----|:----------------|:--------------------------|
| `00_PRD.md` | `"Strictly Offline, No Cloud"` | `"Real-time sync, Auth (Google/Email), RLS mandatory"` |
| `ARCHITECTURE.md` | `React → IPC → SQLite` | `React/Vite → Supabase SDK → PostgreSQL` |
| `SCHEMA.md` | SQLite tables + integer PKs | PostgreSQL + UUID + RLS policies |
| `TASKS.md` | Local DB setup, IPC wiring | Cloud init, Auth flow, RLS rules, Realtime subscriptions |
| `AGENTS.md` | ✅ 100% Same | ✅ 100% Same |
| `GEMINI.md` | ✅ Same | ✅ Same |
| `ERROR_LOGS.md` | ✅ Same | ✅ Same (CORS, token expiry, RLS deny errors) |

### Supabase ke Liye `TASKS.md` Phase 2:

```markdown
- Task 2.1: Init Supabase project → store env keys in .env
- Task 2.2: Run SCHEMA.md SQL → apply RLS policies
- Task 2.3: Setup Auth (Email/Google/Magic Link) + Protected Routes
- Task 2.4: Connect frontend SDK → test CRUD & realtime updates
- Task 2.5: Setup Vite env validation → Vercel/Netlify deployment
```

### Supabase `00_PRD.md` Constraints Example:

```markdown
## 🚫 Business Constraints
- Invoices soft-delete only (`deleted_at` timestamp), never hard delete
- Stock CANNOT go negative at DB level (CHECK constraint + trigger)
- Row Level Security (RLS) mandatory on ALL tables
- All timestamps must be `timestamptz` (UTC)
- Frontend kabhi `service_role` key access nahi karega. Sirf `anon` key.
```

### Firebase vs Supabase Quick Comparison:

| Aspect | Supabase | Firebase |
|:-------|:---------|:---------|
| `id` Type | `UUID` | Auto-generated `string` (Firestore doc ID) |
| `SCHEMA.md` Format | SQL + RLS | NoSQL Collections/Documents + `firestore.rules` |
| Security | `Row Level Security` policies | `match /{collection}/{doc} { allow read, write: if ... }` |
| Realtime | `supabase.channel().subscribe()` | `onSnapshot()` listeners |
| Timestamps | `timestamptz` | `FieldValue.serverTimestamp()` |

---

## 12. 🖥️ Multi-IDE Compatibility

> [!NOTE]
> Yeh workflow **Universal** hai. Koi bhi AI IDE use karo — `.ai/` files, `AGENTS.md` rules, aur `Halt & Ask` sab jagah kaam karta hai. Sirf `GEMINI.md` ka naam/location tool ke hisaab se adjust karo.

### IDE Adaptation Table:

| AI Tool / IDE | `GEMINI.md` Ko Kaise Adapt Karein? | Context Kaise Load Hoga? |
|:-------------|:----------------------------------|:------------------------|
| **Antigravity / Gemini** | ✅ `GEMINI.md` as-is use karein | `.antigravityrules` auto-load. `@.ai/` reference karein. |
| **Cursor** | 🔄 Content ko `.cursorrules` mein paste karein | `@GEMINI.md` ya `#folder:.ai` se reference |
| **GitHub Copilot (VS Code)** | 🔄 `.github/copilot-instructions.md` banayein | `@workspace` ya `#file:AGENTS.md` |
| **Windsurf (Codeium)** | 🔄 `SYSTEM.md` ya `AGENTS.md` use karein | Auto-indexes project files |
| **Claude Desktop / Chat** | 🔄 Files upload karein ya paste karein | Upload → Reference in chat |
| **Aider / Open Interpreter** | 🔄 `.aider.instructions` mein convert karein | CLI flags ya project root mein rakhein |

### Final Compatibility Verdict:

| Aspect | Antigravity | Cursor | GitHub Copilot | Others |
|:-------|:-----------:|:------:|:--------------:|:------:|
| `00_PRD.md` → `TASKS.md` Workflow | ✅ | ✅ | ✅ | ✅ |
| `AGENTS.md` Rules | ✅ | ✅ | ✅ | ✅ |
| Halt & Ask Control | ✅ | ✅ | ✅ | ✅ |
| Git Safety Rules | ✅ | ✅ | ✅ | ✅ |
| `GEMINI.md` (Env Config) | Native | `.cursorrules` | `.github/copilot-instructions.md` | Tool-specific |
| Context Loading | Auto | `@file` | `@workspace` | Upload / Ref |

**Bottom Line:** Aap yeh process **kisi bhi AI coding assistant** mein use kar sakte hain. Sirf `GEMINI.md` ko adjust karo — baaki sab **plug-and-play** hai. 🔌

---

## 13. 🧭 Tech Stack Decision Matrix

| Project Type | Language/Framework | Database | Auth | Connectivity | AI Workflow |
|:------------|:------------------|:---------|:-----|:-------------|:-----------:|
| 🖥️ **Offline Desktop** | Electron + React/Vite + TS | SQLite / Better-SQLite3 | Local PIN / OS Auth | ❌ Offline | ✅ 100% |
| 🌐 **Web SaaS** | Next.js / React + TS | Supabase (PostgreSQL) | Supabase Auth / Google | ✅ Online | ✅ 100% |
| 📱 **Mobile (Cross-platform)** | React Native + TS | SQLite + Supabase | Supabase Auth + Token Cache | 🔄 Hybrid | ✅ 100% |
| 🤖 **AI / ML Tools** | Python (Flask / FastAPI) | PostgreSQL + pgvector | JWT / Session | ✅ Online | ✅ Excellent |
| 📊 **Admin Dashboard** | Flask + Jinja2 / HTMX | PostgreSQL | Flask-Login | ✅ Online | ✅ Great |
| ⚡ **High-Concurrency API** | Go / Node.js / FastAPI | PostgreSQL / Redis | JWT + API Keys | ✅ Online | 🟡 Good |

### Online vs Offline vs Hybrid:

| Nature | Best DB | Best Stack | Key Point |
|:-------|:--------|:-----------|:----------|
| ❌ Strictly Offline | SQLite, Better-SQLite3 | Electron + React, Tauri + TS | No network calls, local file, auto-backup |
| ✅ Strictly Online | Supabase, Firebase, MongoDB Atlas | Next.js, FastAPI, Django | Auth, RLS, rate limiting, CORS |
| 🔄 Hybrid | SQLite (local) + PostgreSQL (cloud) | React Native, PWA, Flutter | Conflict resolution, queue, sync triggers |

---

## 14. 📊 Project Type → Language & DB Guide

| 📂 Project | 💡 Examples | 🛠️ Best Stack | 🗄️ Best DB | Connectivity |
|:---------|:-----------|:------------|:---------|:------------|
| 🖥️ Desktop Offline App | Medical Billing, POS, Kiosk, Inventory | Electron + React + TS | SQLite | ❌ Offline |
| 🌐 Web SaaS | CRM, Booking, Analytics, Subscription | Next.js + TS | Supabase (PostgreSQL) | ✅ Online |
| 📱 Mobile App | Field Service, Retail POS, Attendance | React Native + TS | SQLite + Firebase | 🔄 Hybrid |
| 🤖 AI / ML Tool | Doc Parser, Automation, AI Wrappers | Flask / FastAPI + Python | PostgreSQL + pgvector | ✅ Online |
| 📊 Admin Dashboard | Internal tools, Reporting | Flask + Jinja2 / HTMX | PostgreSQL | ✅ Online |
| 🔄 Real-time App | Chat, Collab, Live Dashboard | Next.js + Supabase | Supabase Realtime | ✅ Online |
| 📱 Native Android | POS, Attendance, Field App | React Native / Kotlin | Room + SQLite | 🔄 Hybrid |
| 🌍 PWA / Hybrid Web | Offline-capable web tools | React/Vite + Service Workers | IndexedDB + Cloud | 🔄 Hybrid |

---

## 15. ⚖️ React Native vs Flask vs Android

### Comparison:

| Layer | React Native | Flask (Python) | Native Android (Kotlin) |
|:-----|:-------------|:---------------|:------------------------|
| 🎯 Role | Mobile App UI | Backend API / Web Server | Native Android UI |
| 🌐 Language | JavaScript / TypeScript | Python | Kotlin |
| 📱 Output | `.apk` / `.ipa` | REST API / HTML Pages | `.apk` / `.aab` |
| 🔌 Offline | ✅ Excellent (SQLite, AsyncStorage) | ❌ Server-side only | ✅ Excellent (Room DB) |
| 🤖 AI Ecosystem | 🟡 JS ecosystem | ✅ Python = AI native | 🟡 JVM ecosystem |
| 🚀 Dev Speed | ✅ Fast (single codebase) | ✅ Fast (MVPs) | 🔴 Slow (verbose) |
| 🎨 UI Richness | ✅ React paradigm, Tailwind-like | 🟡 Jinja2/HTMX (limited reactive) | ✅ Jetpack Compose |

### Kaunsa Chunu?

| Aapka Goal | Best Choice | Kyun? |
|:-----------|:------------|:------|
| 📱 Mobile App (Android + iOS) | **React Native** | Single codebase, offline-ready, component-driven |
| 🌐 Web Dashboard / Admin | **Flask + Jinja2** | Quick, Python backend, server-rendered, no heavy JS |
| 🤖 AI/ML Heavy Processing | **Flask / FastAPI** | Python native — transformers, langchain, pandas direct |
| 📱 Mobile + Backend Sync | **React Native + Flask** | RN → UI/offline, Flask → logic/DB |
| 🖥️ Strict Offline Desktop | **Electron + React + SQLite** | Zero internet, local DB, EXE packaging |
| ⚡ High-Performance API | **FastAPI** | Async ASGI, type-safe, modern Python |

### React Native + Flask Combined Architecture:

```
📱 React Native App  →  UI + Offline Cache (SQLite/AsyncStorage)
         ↓ HTTP / REST API
🌐 Flask Backend     →  Auth + Business Logic + DB Queries
         ↓ SQLAlchemy / ORM
🗄️ Database          →  SQLite (local) / PostgreSQL (cloud)
```

**AI Workflow Compatibility (Dono ke saath):**

| File | React Native Version | Flask Version |
|:-----|:---------------------|:--------------|
| `00_PRD.md` | RN + TS + SQLite + Offline rules | Flask + Python + SQLAlchemy + API rules |
| `SCHEMA.md` | SQLite tables / Room entities | SQLAlchemy models, Alembic migrations |
| `AGENTS.md` | Compose-like rules, offline fallback | PEP 8, Type hints, Blueprint modularity |
| `TASKS.md` | Screen-by-screen, API hooks | Route/Model-by-model, endpoints |
| `Halt & Ask` | ✅ Exactly same | ✅ Exactly same |
| `Git rules` | ✅ Exactly same | ✅ Exactly same |

---

## 16. 🗓️ Daily Workflow Routine

| Time | Action |
|:-----|:-------|
| ☕ **Start of Day** | `.ai/TASKS.md` kholo → next task dekho → AI ko **Master Prompt #2** do |
| 🛠️ **Work** | AI code generate karega → Aap review karo → Approve/Reject + feedback do |
| 🛑 **End of Task** | AI "Halt & Ask" report dega → Aap `"Proceed"` ya `"Fix first"` bolo |
| 🐛 **Bug Aaye** | AI ko bolo: `"Log in ERROR_LOGS.md with date, root cause, fix. Test again."` |
| 🔄 **Context Lost?** | **Context Refresh Prompt** use karo |
| 🌙 **End of Day** | `ERROR_LOGS.md` updated hai? → Kal ke liye 1-2 tasks pre-plan karo |

> 🎁 **Weekly Tip:** Har Friday `00_PRD.md` + `TASKS.md` review karo. Koi requirement change hui? AI se baaki files auto-update karwao.

---

## 17. ✅ Final Pre-Flight Checklist

Start karne se pehle yeh sab verify karein:

- [ ] 🚫 Project path **NO SPACES** — `D:\dev\my-app` ✅ | `C:\My Projects\App` ❌
- [ ] 📂 `.ai/` folder + 8 files present (7 filled + `ERROR_LOGS.md` khali)
- [ ] 📜 `.antigravityrules` root mein present (ya `.cursorrules`)
- [ ] 📖 `README.md` mein `.ai/` folder ka mention hai
- [ ] 🔒 GitHub `main` branch protection **ON** — Require PR, No force push
- [ ] 🌿 AI sirf `feat/*` / `fix/*` branches use karta hai
- [ ] 🛑 AI har task ke baad **RUKTA** hai — Halt & Ask
- [ ] 🧪 Har task ke baad `TASKS.md` Test Condition manually verify
- [ ] 🐛 Har bug `ERROR_LOGS.md` mein log hota hai
- [ ] 📦 Commits conventional — `feat:`, `fix:`, `docs:`, `chore:`
- [ ] 🔄 `main` sirf approved PRs ke through update hota hai
- [ ] ✅ AI context verify: `"List .ai/ files and show current task"` → AI sahi answer de?

---

## 18. 💡 Smart Workflow Benefits

### Aapko Personally Kya Milega?

| Benefit | Detail |
|:--------|:-------|
| ⏱️ **50–70% Time Saving** | AI ko baar-baar explain nahi karna padega |
| 🧠 **Zero Context Loss** | `.ai/` folder = AI ki permanent memory |
| 🔒 **Predictable Output** | Code style, structure — sab session-to-session consistent |
| 🛡️ **Fewer Bugs** | `ERROR_LOGS.md` se AI past mistakes repeat nahi karta |
| 🤝 **Team-Ready** | Sabko same context milega — onboarding fast |
| 🔄 **Stack Flexibility** | SQLite se Supabase? Bas `00_PRD.md` update karo |
| 🎯 **Full Control** | AI code likhta hai — aap architect aur reviewer ho |
| 🌐 **Universal** | Koi bhi IDE — Antigravity, Cursor, Copilot, Claude — sab compatible |

### Real Example — Bina Workflow vs Workflow Se:

```
❌ Without Workflow:
  → AI: "Chalo Firebase use karte hain!"
  → Aap: "Nahi, offline chahiye tha!"
  → AI: "Sorry, ab code rewrite karna padega..."
  → 😤 3 ghante waste

✅ With Workflow:
  → 00_PRD.md: "No Firebase. Strictly SQLite offline."
  → AI automatically SQLite + Electron setup karega
  → ✅ First time right. Zero rework.
```

---

## 🗂️ Quick Reference Card

```
AAPKA KAAM (Manual):
  ✏️  00_PRD.md fill karo
  📂  git init + .gitignore + .ai/ folder + .antigravityrules
  🔒  GitHub main branch protect karo
  ✅  AI ka output review karo + approve/reject karo

AI KA KAAM (Assisted):
  🏗️  6 foundation files generate
  💻  Feature-by-feature code likhega
  🛑  Har task ke baad Halt & Ask karega
  📊  Diff + commit msg suggest karega (execute nahi)

DAILY EXECUTION LOOP:
  📋  TASKS.md → Master Prompt #2 → Code Review → Approve → Git → Repeat

EMERGENCY PROMPTS:
  Context Lost  → "Context Refresh" prompt
  AI ne rules toda → "STOP. Halt & Ask rule violated. Report and wait."
  AI ne commit kiya → Level 1+2+3 Git Safety apply karo

STACK CHOISE LOGIC:
  Offline Desktop  → Electron + SQLite
  Web SaaS         → Next.js + Supabase
  Mobile           → React Native + SQLite/Firebase
  AI/ML Backend    → Flask/FastAPI + PostgreSQL
  Admin Dashboard  → Flask + Jinja2
```

---

> [!NOTE]
> Har naye project mein `00_PRD.md` ek baar clearly likhein — baaki sab AI sambhaalta hai.
> Jab tak aap `"✅ Approved"` nahi bolte — AI kuch bhi commit, push, ya merge nahi karega.

---

*🤖 AI-First Development Workflow • Complete Bible • GitHub Optimized*
*Covers: Offline, Cloud (Supabase/Firebase), Mobile, Flask, Android, React Native*
*Compatible: Antigravity, Cursor, GitHub Copilot, Windsurf, Claude, Gemini*
