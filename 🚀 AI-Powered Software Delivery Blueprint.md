<div align="center">

# 🤖 AI-First Complete Project Blueprint

### *Manual Banayen → AI Banayega Baaki Sab*

<br/>

![Version](https://img.shields.io/badge/Version-2026-6366f1?style=for-the-badge&logo=sparkles&logoColor=white)
![Status](https://img.shields.io/badge/Status-Production%20Ready-22c55e?style=for-the-badge&logo=checkmarx&logoColor=white)
![AI Powered](https://img.shields.io/badge/AI-Powered-f59e0b?style=for-the-badge&logo=openai&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js_14-black?style=for-the-badge&logo=next.js)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)

<br/>

> *Ek complete, step-by-step system — jisme AI pehle documents banata hai,*
> *phir usi documents ke basis par poora project build karta hai.*

<br/>

</div>

---

## 🧭 Table of Contents

- [🧠 The Big Idea](#-the-big-idea)
- [🗺️ Complete Workflow](#%EF%B8%8F-complete-workflow--ek-nazar-mein)
- [🤖 Step 0 — AI Se Documents Generate Karo](#-step-0--ai-se-documents-generate-karo-sabse-pehle)
- [📂 Step 1 — Brain Structure Banao](#-step-1--brain-structure-banao)
- [🛠️ Step 2 — Foundation & DB Design](#%EF%B8%8F-step-2-foundation--db-design)
- [🌱 Step 3 — Seed Module](#-step-3-the-seed-module--pehla-feature)
- [🔄 Step 4 — Scaling Loop](#-step-4-the-repetitive-scaling-loop)
- [🧩 Step 5 — Advanced Orchestration](#-step-5-advanced-agent-orchestration)
- [🛡️ Safety Tips](#%EF%B8%8F-safety--optimization-tips)
- [⚡ TL;DR](#-tldr)

---

## 🧠 The Big Idea

Socho ek **naye employee** ko project diya — bina kisi documentation ke.

Woh confuse hoga. Galtiyan karega. Baar baar same cheez poochega.

**AI bhi exactly aisa hi karta hai** — jab tak usse proper context nahi dete.

```
┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│   WITHOUT BLUEPRINT              WITH BLUEPRINT                  │
│   ─────────────────              ──────────────                  │
│   ❌ AI forgets context          ✅ AI always knows the plan     │
│   ❌ Inconsistent code           ✅ Every module looks same      │
│   ❌ Repeating yourself          ✅ One prompt = one feature     │
│   ❌ AI breaks old code          ✅ Safe, atomic changes         │
│   ❌ No structure                ✅ Clear folder + file roles    │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **Golden Formula:** `Documents Generate Karo → Brain Setup Karo → Seed Banao → Loop Se Scale Karo`
>
> Sirf **ek baar** properly setup karo — phir har module copy-paste prompt se build hoga. 🚀

---

## 🗺️ Complete Workflow — Ek Nazar Mein

```
┌─────────────────────────────────────────────────────────────────────┐
│                                                                     │
│  🤖 STEP 0        AI se saare .md documents generate karo           │
│     ↓             (AGENTS + BLUEPRINT + TASKS — ek prompt mein)     │
│                                                                     │
│  📂 STEP 1        Brain files project root mein rakho               │
│     ↓             (AGENTS.md, PROJECT_BLUEPRINT.md, TASKS.md)       │
│                                                                     │
│  🛠️  STEP 2        Foundation setup karo                            │
│     ↓             (Supabase client, .env.local, DB schema)          │
│                                                                     │
│  🌱 STEP 3        Seed module banao (Auth)                           │
│     ↓             (Pattern establish karo — poore project ka DNA)   │
│                                                                     │
│  🔄 STEP 4        Har naye module ke liye loop repeat karo           │
│     ↓             (Same prompt, same pattern, naam badlo)           │
│                                                                     │
│  🔍 STEP 5        Har 30 min — Context Refresh + Audit               │
│                   (AI drift nahi karega, standards intact rahenge)  │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 🤖 Step 0 — AI Se Documents Generate Karo *(Sabse Pehle)*

> [!IMPORTANT]
> **Ye step logo skip kar dete hain — aur yahi sabse badi galti hai.**
>
> Brain files **manually likhne ki zarurat nahi.** AI khud banayega — tum bas project idea batao.

<br/>

Ye ek **Master Prompt** hai. Isko copy karo, apna project idea fill karo, aur AI ko do:

```
Act as a Senior Software Architect.

I want to build: [APNA PROJECT IDEA YAHAN LIKHO]

Example ideas:
  - "An Invoice Management App for freelancers"
  - "An Expense Tracker for small teams"
  - "A Task Management tool like Trello"

Tech Stack: [APNA STACK LIKHO]
  Example: Next.js 14 + Supabase + Tailwind CSS + TypeScript

Core Features I want:
  - [Feature 1]
  - [Feature 2]
  - [Feature 3]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Generate these 3 complete files for me:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. AGENTS.md
   Include: tech stack, coding rules, naming conventions,
   architecture rules (what goes in lib/ vs components/),
   safety rules, output expectations

2. PROJECT_BLUEPRINT.md
   Include: full DB schema with SQL, all tables & columns
   with types, foreign keys, RLS policies, pages & routes,
   component plan, API endpoints, user flow, env variables,
   risks, future expansion

3. TASKS.md
   Include: phase-wise checklist (Setup → Auth → Features
   → Polish → Deploy), every feature broken into small
   atomic tasks with checkboxes

Be as detailed as possible.
These 3 files are the single source of truth for the
entire project — AI will read them before every task.
```

<br/>

### 📋 Example — Invoice App ke liye AI ka Output

**`AGENTS.md` kaisa dikhega:**

```markdown
# AGENTS.md — Invoice Management App

## Tech Stack
- Framework:  Next.js 14 (App Router)
- Styling:    Tailwind CSS + Shadcn UI
- Database:   Supabase (PostgreSQL)
- Language:   TypeScript (strict mode)
- Auth:       Supabase Auth

## Coding Rules
- Har page mein loading skeleton aur error boundary hona chahiye
- Early returns use karo — nested if-else se bachao
- Business logic sirf lib/ mein — pages mein nahi
- Secrets kabhi hardcode mat karo — .env.local use karo

## Naming Conventions
- Components → PascalCase    (InvoiceCard.tsx)
- Functions  → camelCase     (fetchInvoices)
- DB tables  → snake_case    (invoice_items)
- Hooks      → use prefix    (useInvoices.ts)

## Architecture Rules
- UI logic        → components/
- DB calls        → lib/
- Custom hooks    → hooks/
- TypeScript types → types/

## Safety Rules
- No API keys in source code
- No duplicate logic across files
- No breaking changes without explanation
- Har module ke baad TASKS.md update karo
```

<br/>

**`PROJECT_BLUEPRINT.md` kaisa dikhega:**

```markdown
# Project Blueprint — Invoice Management App

## Database Schema

### users
| Column     | Type      | Notes              |
|------------|-----------|--------------------|
| id         | uuid      | Primary Key (auto) |
| name       | text      | Full name          |
| email      | text      | Unique             |
| created_at | timestamp | Default: now()     |

### invoices
| Column      | Type      | Notes                      |
|-------------|-----------|----------------------------|
| id          | uuid      | Primary Key                |
| user_id     | uuid      | FK → users.id              |
| client_name | text      | Client company             |
| amount      | numeric   | Total invoice amount       |
| status      | text      | draft / sent / paid        |
| due_date    | date      | Payment deadline           |
| created_at  | timestamp | Default: now()             |

## RLS Policies
-- Users can only see their own invoices
CREATE POLICY "own invoices only"
ON invoices FOR ALL
USING (auth.uid() = user_id);

## Pages & Routes
| Route              | Purpose                    |
|--------------------|----------------------------|
| /                  | Landing page               |
| /login             | Authentication             |
| /dashboard         | Summary + stats            |
| /invoices          | Invoice list               |
| /invoices/new      | Create invoice             |
| /invoices/[id]     | Edit invoice               |
| /clients           | Client management          |

## Env Variables
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=
SUPABASE_SERVICE_ROLE_KEY=
```

<br/>

**`TASKS.md` kaisa dikhega:**

```markdown
# Tasks — Invoice Management App

## ⚙️ Phase 1: Setup
- [ ] Initialize Next.js 14 project with TypeScript
- [ ] Configure Tailwind CSS + Shadcn UI
- [ ] Setup Supabase project and get API keys
- [ ] Add .env.local with required variables
- [ ] Initialize folder structure per blueprint

## 🔐 Phase 2: Authentication
- [ ] Create login page UI
- [ ] Create signup page UI
- [ ] Connect Supabase Auth
- [ ] Setup middleware for protected routes
- [ ] Test login/logout flow

## 🧾 Phase 3: Invoices Module
- [ ] Create invoice list page with loading state
- [ ] Create add invoice form
- [ ] Create edit invoice page
- [ ] Add delete with confirmation
- [ ] Add status filter (draft/sent/paid)

## 👥 Phase 4: Clients Module
- [ ] Client list page
- [ ] Add/Edit client form
- [ ] Link clients to invoices

## 🎨 Phase 5: Polish
- [ ] Loading skeletons on all pages
- [ ] Empty states with CTA
- [ ] Error toast notifications
- [ ] Mobile responsiveness

## 🚀 Phase 6: Deploy
- [ ] Final env variable check
- [ ] Production build test
- [ ] Deploy to Vercel
- [ ] Post-deploy smoke test
```

> [!NOTE]
> **Ab in teeno files ko apne project root mein paste karo** — aur Step 1 pe jao.

---

## 📂 Step 1 — Brain Structure Banao

> In generated files ko project mein sahi jagah rakho. Ye structure **non-negotiable** hai.

<br/>

```
project-root/
│
├── 📋 AGENTS.md                  ← 🔴 AI ka rulebook (Step 0 mein generate hua)
├── 📋 PROJECT_BLUEPRINT.md       ← 🟠 DB + architecture ka master plan
├── 📋 TASKS.md                   ← 🟡 Phase-wise development checklist
│
├── 🔧 .cursor/rules/main.mdc     ← 🔵 Sirf EK tool file — apna tool choose karo
│       OR                                          │
│   .github/copilot-instructions.md                │
│       OR                                          │
│   GEMINI.md                      ← ──────────────┘
│
└── 🏗️ app/                        ← 🟢 Actual codebase — AI banayega
    ├── components/
    ├── lib/
    ├── hooks/
    └── types/
```

### 🗂️ Har File Ka Role

| 📁 File | 🎯 Kaam | 🤖 AI Kaise Use Karta Hai | 👤 Tum Kab Update Karte Ho |
|:---|:---|:---|:---|
| `AGENTS.md` | Coding rules + standards | Har prompt pe padhta hai | Jab style change karni ho |
| `PROJECT_BLUEPRINT.md` | DB schema + routes + plan | DB relationships samajhne ke liye | Jab naya feature add ho |
| `TASKS.md` | Progress checklist | Har commit ke baad update karta hai | Status check karne ke liye |
| Tool file | Editor behavior | Har response mein follow karta hai | Ek baar setup, hamesha kaam aata hai |

> [!WARNING]
> Tool-specific rules mein se **SIRF EK** file rakho. Cursor + Copilot + Gemini — teeno simultaneously mat rakho. Conflict hoga, AI confuse ho jaayega.

---

## 🛠️ Step 2: Foundation & DB Design

> Ab AI ko pehla kaam do — **infrastructure setup.**

<br/>

### 🔌 Supabase Setup Prompt

```
Read PROJECT_BLUEPRINT.md carefully.

Then do the following:
1. Initialize Supabase client in app/lib/supabase.ts
   with TypeScript types matching our DB schema
2. Create .env.local with all required variable names
   (show me what to fill in)
3. Run the SQL from PROJECT_BLUEPRINT.md in Supabase
   dashboard to create all tables and RLS policies

Confirm when done.
```

**✅ Expected files after this step:**

```
app/lib/supabase.ts     ← Typed Supabase client
.env.local              ← All API keys (empty, for you to fill)
.env.example            ← Committed to git (without values)
```

---

## 🌱 Step 3: The Seed Module — Pehla Feature

> **Seed Module = Poore Project ka DNA.**
>
> Ye pehla feature define karta hai ki baaki saare features kaisa dikhenge aur kaise kaam karenge. Isliye **Auth se shuru karo** — simple hai aur foundation ban jaata hai.

<br/>

```
┌─────────────────────────────────────────────────────────────┐
│  WHY "SEED" MODULE?                                         │
│                                                             │
│  Seed Module establish karta hai:                           │
│  ✅ Folder structure ka pattern                             │
│  ✅ Supabase calls kaise bante hain                         │
│  ✅ Error handling ka style                                 │
│  ✅ Loading state ka pattern                                │
│  ✅ Component naming ka style                               │
│                                                             │
│  Baad ke SAARE modules yahi pattern copy karenge.           │
└─────────────────────────────────────────────────────────────┘
```

<br/>

### 🔐 Auth Seed Module Prompt

```
Read AGENTS.md and PROJECT_BLUEPRINT.md completely.

Build the Authentication Module — this is our SEED module.
Every future module will follow this exact pattern.

Build:
- Login page UI  → app/(auth)/login/page.tsx
- Signup page UI → app/(auth)/signup/page.tsx
- Auth service   → app/lib/auth.ts
- Middleware     → middleware.ts (protect all /dashboard routes)

Follow ALL rules from AGENTS.md:
  ✅ Loading state on every button
  ✅ Error messages displayed cleanly
  ✅ Early returns — no nested if-else
  ✅ Business logic in lib/, not in page components

After completing:
  1. Update TASKS.md — mark Auth tasks as ✅ done
  2. Confirm: "Seed module complete. Pattern is ready to reuse."
```

**📁 Auth Module ke baad file structure:**

```
app/
├── (auth)/
│   ├── login/
│   │   └── page.tsx          ← Login form UI
│   └── signup/
│       └── page.tsx          ← Signup form UI
├── lib/
│   ├── supabase.ts           ← DB client
│   └── auth.ts               ← login / logout / session helpers
└── middleware.ts             ← Route protection
```

> [!IMPORTANT]
> Jab tak AI **"Seed module complete. Pattern is ready to reuse."** confirm nahi karta — agle step pe mat jao. Yahi pattern template banega.

---

## 🔄 Step 4: The Repetitive Scaling Loop

> Yahan asli magic hota hai. 🪄
>
> Seed ban gaya — ab har naya feature **ek copy-paste prompt** se banta hai.

<br/>

```
┌────────────────────────────────────────────────────────────┐
│                                                            │
│  🌱 Seed      →   📦 Module 2   →   📦 Module 3   →  ...  │
│    Auth            Invoices          Clients               │
│                                                            │
│  Pattern           Same              Same                  │
│  establish         pattern           pattern               │
│  karo              follow            follow                │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

<br/>

### 🔁 New Module Prompt — Sirf Naam Badlo

```
I am now starting the [MODULE NAME] module.
(e.g., Invoices)

1. Read the '[module_table]' table in PROJECT_BLUEPRINT.md
2. Read the Auth module we built — use the EXACT same architecture

Build full CRUD for [MODULE NAME]:
   - List page with loading skeleton → app/[module]/page.tsx
   - Create form with validation    → app/[module]/new/page.tsx
   - Edit page                      → app/[module]/[id]/page.tsx
   - Service layer (DB calls)       → lib/[module].ts
   - TypeScript types               → types/[module].ts

Rules:
   ✅ Same folder structure as Auth module
   ✅ Same error handling style
   ✅ Same loading state pattern
   ✅ Same naming conventions from AGENTS.md
   ✅ 100% consistent — do NOT invent new patterns

After completing:
   Update TASKS.md and confirm done.
```

<br/>

### 🧾 Real Example — 3 Modules ke Baad Project

```
app/
│
├── (auth)/login/page.tsx          ← 🌱 Module 1: Auth (Seed)
├── (auth)/signup/page.tsx
│
├── invoices/                      ← 📦 Module 2: Invoices
│   ├── page.tsx                       (same pattern as auth)
│   ├── new/page.tsx
│   └── [id]/page.tsx
│
├── clients/                       ← 📦 Module 3: Clients
│   ├── page.tsx                       (same pattern as auth)
│   ├── new/page.tsx
│   └── [id]/page.tsx
│
├── lib/
│   ├── supabase.ts
│   ├── auth.ts                    ← Seed pattern
│   ├── invoices.ts                ← Same pattern as auth.ts
│   └── clients.ts                 ← Same pattern as auth.ts
│
├── components/
│   ├── InvoiceCard.tsx
│   ├── ClientCard.tsx
│   └── shared/
│       ├── LoadingSkeleton.tsx    ← Shared across ALL modules
│       ├── EmptyState.tsx
│       └── ConfirmDialog.tsx
│
└── types/
    ├── invoice.ts
    └── client.ts
```

> [!TIP]
> Notice karo — har module ki `lib/`, `page`, aur `types` file ka structure bilkul same hai. Ye consistency AI ki wajah se possible hai kyunki usse Seed pattern pata hai.

---

## 🧩 Step 5: Advanced Agent Orchestration

### 🔄 Context Refresh — Har 30 Min Chalaao

> AI ka ek weakness hai — **long conversations mein context drift karta hai.** Ye prompt regularly use karo:

```
🔄 CONTEXT REFRESH

Before continuing, please:
1. Re-read AGENTS.md — confirm you remember our coding standards
2. Re-read PROJECT_BLUEPRINT.md — confirm you know the DB schema
3. Tell me: have we drifted from standards in the last few tasks?
4. If yes, flag it now. We will fix before moving on.
```

<br/>

### 🔍 AI Audit Prompt — Har Module Ke Baad

```
AUDIT REQUEST — [Module Name]

Compare the [Module Name] we just built against:
  - The Seed (Auth) module code quality
  - Rules defined in AGENTS.md

Answer these questions:
  1. Is folder structure consistent with Seed?
  2. Are loading states present on every async action?
  3. Is all business logic in lib/ (not pages)?
  4. Any deeply nested if-else that should be early returns?
  5. Any duplicate logic that should be a shared component?

If anything is off — refactor it NOW before next module.
```

<br/>

### 📊 Document Usage Table

| 📄 Document | 🤖 AI Kab Padhta Hai | 👤 Tum Kab Update Karte Ho |
|:---|:---|:---|
| **AGENTS.md** | Har prompt se pehle — coding style enforce karne ke liye | Jab coding style ya rules change karni ho |
| **PROJECT_BLUEPRINT.md** | Naya module shuru karne se pehle — DB schema samajhne ke liye | Jab naya feature ya table add ho |
| **TASKS.md** | Har commit ke baad — progress update karne ke liye | Kabhi bhi status dekhne ke liye |

---

## 🛡️ Safety & Optimization Tips

<br/>

### ✅ Atomic Commits — Har Kaam Alag Commit

```bash
# ❌ Galat — sab ek commit mein
git commit -m "added invoices, clients, auth, fixed bugs"

# ✅ Sahi — ek kaam, ek commit
git commit -m "feat: add invoice list page with loading state"
git commit -m "feat: add create invoice form with validation"
git commit -m "fix: handle empty state in invoice list"
```

> Atomic commits se rollback easy hota hai — agar ek cheez toot jaaye to sirf wahi revert karo.

<br/>

### 🚨 Common Mistakes — Aur Unse Bachne Ka Tarika

| ❌ Mistake | ✅ Fix |
|:---|:---|
| Step 0 skip karke seedha code likhna | Pehle Master Prompt se teeno .md files generate karo |
| AGENTS.md padhne ka instruction bhoolna | Har prompt mein "Read AGENTS.md" likhna mat bhulo |
| Seed confirm hone se pehle aage badhna | "Pattern established" confirm hone ka wait karo |
| `.env.local` GitHub pe push karna | `.gitignore` mein Day 1 pe add karo |
| Teeno tool files ek saath rakhna | Sirf ek choose karo — Cursor ya Copilot ya Gemini |
| Context drift hone dena | Har 30 min pe Context Refresh prompt chalaao |

---

## ⚡ TL;DR

```
╔═════════════════════════════════════════════════════════════════════╗
║                                                                     ║
║  🤖 STEP 0   Master Prompt se teeno .md files generate karo         ║
║              (AGENTS + BLUEPRINT + TASKS — ek prompt mein sab)      ║
║                                                                     ║
║  📂 STEP 1   Brain files project root mein rakho                    ║
║              Tool-specific file bhi choose karo (sirf ek)           ║
║                                                                     ║
║  🛠️  STEP 2   Foundation setup karo                                 ║
║              Supabase client + .env.local + DB tables               ║
║                                                                     ║
║  🌱 STEP 3   Seed module banao (Auth)                                ║
║              Poore project ka pattern yahan establish hoga           ║
║                                                                     ║
║  🔄 STEP 4   Har naye module ke liye loop repeat karo               ║
║              Same prompt — sirf module ka naam badlo                 ║
║                                                                     ║
║  🔍 STEP 5   Har 30 min — Context Refresh + Audit                   ║
║              AI drift nahi karega, standards intact rahenge          ║
║                                                                     ║
╚═════════════════════════════════════════════════════════════════════╝
```

<br/>

<div align="center">

| 🔢 Step | 📦 Kya Karo | ⏱️ Kitna Time |
|:---:|:---|:---:|
| 🤖 Step 0 | Master Prompt → teeno .md files generate karo | ~5 min |
| 📂 Step 1 | Files project mein rakho, structure banao | ~10 min |
| 🛠️ Step 2 | Supabase + env setup | ~20 min |
| 🌱 Step 3 | Seed (Auth) module | ~1–2 hrs |
| 🔄 Step 4 | Har module (loop) | ~30–60 min |
| 🔍 Step 5 | Context Refresh har 30 min | ~2 min |

<br/>

---

### `Generate` &nbsp;→&nbsp; `Setup` &nbsp;→&nbsp; `Seed` &nbsp;→&nbsp; `Loop` &nbsp;→&nbsp; `Ship` 🚀

*High-Speed · Consistent · Professional · Error-Free AI Development*

<br/>

*Made with ❤️ for the AI-first development era &nbsp;·&nbsp; 2026*

</div>
