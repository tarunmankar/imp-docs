<div align="center">

# 🤖 AI-First Project Structure

### *Manual Banayen → AI Banayega Baaki Sab*

<br/>

![Version](https://img.shields.io/badge/Version-2026-6366f1?style=for-the-badge&logo=sparkles&logoColor=white)
![Status](https://img.shields.io/badge/Status-Production%20Ready-22c55e?style=for-the-badge&logo=checkmarx&logoColor=white)
![AI Powered](https://img.shields.io/badge/AI-Powered-f59e0b?style=for-the-badge&logo=openai&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-3b82f6?style=for-the-badge)

<br/>

> *Ek smart, reusable, aur AI-friendly project structure —*
> *jisse planning clear rahe, development fast ho, aur files ka role kabhi confuse na ho.*

<br/>

</div>

---

## 🧭 Table of Contents

- [💡 Core Philosophy](#-core-philosophy)
- [📁 Folder Overview](#-folder-overview)
- [🧠 Layer 1 — Manual Planning Files](#-layer-1--manual-planning-files)
  - [📄 AGENTS.md — AI ka Rulebook](#-a-agentsmd--ai-ka-rulebook)
  - [📄 PROJECT\_BLUEPRINT.md — Project ka Map](#-b-project_blueprintmd--project-ka-map)
  - [📄 TASKS.md — Development Checklist](#-c-tasksmd--development-checklist)
  - [🔧 Tool-Specific Rules File](#-d-tool-specific-rules-file)
- [🏗️ Layer 2 — Project Files](#%EF%B8%8F-layer-2--project-files-ai-yahin-kaam-karega)
- [🧪 Real Example — Expense Tracker](#-real-example--expense-tracker)
- [📌 Best Practices](#-best-practice-rules)
- [🗣️ AI Prompting Tips](#%EF%B8%8F-ai-se-kaam-karwate-waqt-ye-bolo)
- [⚡ TL;DR](#-tldr--super-short-version)

---

## 💡 Core Philosophy

Ye structure **3 simple layers** mein kaam karta hai:

<br/>

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│   📋  Layer 1  ──  Manual Planning Files                        │
│                    Pehle INSAN banata hai                       │
│                                                                 │
│   🔧  Layer 2  ──  Tool-Specific Rules                          │
│                    AI editor ke liye SIRF EK file               │
│                                                                 │
│   🏗️   Layer 3  ──  Project Files                               │
│                    AI khud generate karta hai                   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

<br/>

> [!TIP]
> **Golden Rule:** `Plan → Guide → Build`
>
> Pehle **3–4 manual files** banao → Consistency milegi → AI baaki saara project structure aur code generate karega.

---

## 📁 Folder Overview

```
project-root/
│
├── 📋  AGENTS.md                      ← 🔴 AI ka rulebook  [MUST HAVE]
├── 📋  PROJECT_BLUEPRINT.md           ← 🟠 Project ka master plan
├── 📋  TASKS.md                       ← 🟡 Development checklist
│
├── 🔧  .cursor/rules/main.mdc         ← Pick ONE ──┐
│       OR                                           │ Tool-specific
│   .github/copilot-instructions.md                 │ rules file
│       OR                                           │
│   GEMINI.md                          ← ───────────┘
│
└── 🏗️   app/                           ← AI generate karega
    ├── components/
    ├── lib/
    ├── public/
    ├── .env.local
    └── config files
```

> [!WARNING]
> Tool-specific rules mein se **SIRF EK** file rakho apne project mein. Saath mein teen rakhoge to instructions **conflict** karenge aur AI confuse ho jayega.

---

## 🧠 Layer 1 — Manual Planning Files

> Ye files project ka **brain** hoti hain. Inhe **pehle** banao, baaki sab **baad** mein.

<br/>

### 📄 A) `AGENTS.md` — AI ka Rulebook

![Must Have](https://img.shields.io/badge/Priority-MUST%20HAVE-ef4444?style=flat-square)
![Reads By](https://img.shields.io/badge/Read%20By-All%20AI%20Tools-6366f1?style=flat-square)

**Kaam:** AI tools ko project ke andar ka behavior samjhana.

Ye file AI ke liye ek complete **discipline guide** hai — kaise sochna hai, kaise code likhna hai, aur kya bilkul avoid karna hai.

<br/>

| 🏷️ Section | 📝 Kya Likho |
|:---|:---|
| **Project Identity** | Naam, purpose, app type, target user |
| **AI Working Style** | Small safe changes, no duplicate logic, reusable code prefer karo |
| **File-Handling Rules** | New file sirf zarurat par, minimal edits, one task = one change |
| **Coding Conventions** | Naming style, component structure, folder predictability |
| **Architecture Rules** | UI alag, logic alag, secrets env mein |
| **Quality Rules** | Errors handle karo, loading/empty states socho, edge cases mat bhulo |
| **Safety Rules** | No secrets in code, no unnecessary dependencies |

<br/>

<details>
<summary>📋 <strong>AGENTS.md — Full Template</strong> &nbsp;(click to expand ▼)</summary>

<br/>

```markdown
# [Project Name]

## Purpose
One-line goal of the project.

## AI Behavior Rules
- Do small, safe, focused changes only.
- Prefer reusable code over duplication.
- Ask no unnecessary questions — just implement.
- Keep structure consistent throughout the project.

## Coding Standards
- Functions → camelCase
- Components → PascalCase
- Files → kebab-case or PascalCase (match existing)
- One component per file, single responsibility
- Always handle errors and edge cases

## Architecture Rules
- UI logic      → components/
- Business logic → lib/
- Secrets        → .env.local  (NEVER hardcode)
- Shared hooks   → hooks/
- Types          → types/

## Safety Rules
- No API keys or secrets in source code
- No duplicate logic across files
- No unnecessary file creation
- No breaking changes without explanation

## Output Expectations
- Clean, readable, well-named code
- Maintainable and self-documenting
- Reusable where possible
- Production-friendly from day one
```

</details>

<br/>

---

### 📄 B) `PROJECT_BLUEPRINT.md` — Project ka Map

![Priority](https://img.shields.io/badge/Priority-HIGH-f97316?style=flat-square)
![Type](https://img.shields.io/badge/Type-Roadmap-3b82f6?style=flat-square)

**Kaam:** Project *kya hai* — ye batana. Agar `AGENTS.md` AI ka **behavior** hai, to `PROJECT_BLUEPRINT.md` project ka **roadmap** hai.

<br/>

```
 1.  🎯  Project Overview      →  Naam, summary, problem statement
 2.  👥  Target Users          →  Kaun use karega, unka pain point
 3.  ✅  Core Features         →  Must-have (MVP list)
 4.  💫  Optional Features     →  Nice-to-have, future scope
 5.  🗺️   Pages & Routes        →  /home /login /dashboard /settings
 6.  🔁  User Flow             →  Step-by-step: pehle kya → phir kya
 7.  🗃️   Data Model            →  Entities, fields, relations
 8.  🧩  Component Plan        →  Kaunse reusable components chahiye
 9.  🔌  Backend / API Plan    →  Endpoints aur unka purpose
10.  🖼️   UI States             →  Loading · Error · Empty · Success
11.  🔐  Environment Variables →  Kaunse secrets/keys chahiye
12.  ⚠️   Risks & Edge Cases    →  Kya galat ho sakta hai
13.  🚀  Future Expansion      →  Aage kya add ho sakta hai
```

<br/>

<details>
<summary>📋 <strong>PROJECT_BLUEPRINT.md — Full Template</strong> &nbsp;(click to expand ▼)</summary>

<br/>

```markdown
# Project Blueprint — [Project Name]

## 1. Overview
What the project does in 2–3 sentences.

## 2. Problem Statement
What problem it solves and why it matters.

## 3. Target Users
Who will use it and what they need most.

## 4. Core Features (MVP)
- [ ] Feature 1
- [ ] Feature 2
- [ ] Feature 3

## 5. Optional Features
- [ ] Nice-to-have 1
- [ ] Nice-to-have 2

## 6. Pages & Routes
| Route           | Purpose              |
|-----------------|----------------------|
| `/`             | Landing / Home       |
| `/login`        | Authentication       |
| `/dashboard`    | Main app view        |
| `/settings`     | User preferences     |

## 7. User Journey
1. User visits homepage
2. User signs up / logs in
3. User reaches dashboard
4. User performs main action
5. Success or error feedback shown

## 8. Data Model

### User
| Field      | Type      |
|------------|-----------|
| id         | string    |
| name       | string    |
| email      | string    |
| createdAt  | timestamp |

### [Main Entity]
| Field      | Type      |
|------------|-----------|
| id         | string    |
| title      | string    |
| amount     | number    |
| category   | string    |
| userId     | string    |
| createdAt  | timestamp |

## 9. Component Plan
| Component    | Used On Pages          |
|--------------|------------------------|
| Sidebar      | All dashboard pages    |
| DataForm     | Add / Edit page        |
| DataTable    | List page              |
| EmptyState   | Any page with no data  |

## 10. API Plan
| Endpoint         | Method | Purpose         |
|------------------|--------|-----------------|
| `/api/items`     | GET    | Fetch all items |
| `/api/items`     | POST   | Create new item |
| `/api/items/:id` | PUT    | Update item     |
| `/api/items/:id` | DELETE | Delete item     |

## 11. UI States
- **Loading** → skeleton cards / spinner
- **Empty**   → illustration + CTA button
- **Error**   → toast notification + retry
- **Success** → confirmation message / redirect

## 12. Env Variables
DATABASE_URL=
NEXTAUTH_SECRET=
FIREBASE_API_KEY=

## 13. Risks & Edge Cases
- What if user loses internet during form submit?
- What if API rate limit is hit?
- What if two users edit same record simultaneously?

## 14. Future Expansion
- Mobile app
- Export to CSV / PDF
- Multi-user team workspace
- Analytics dashboard
```

</details>

<br/>

---

### 📄 C) `TASKS.md` — Development Checklist

![Priority](https://img.shields.io/badge/Priority-HIGH-f97316?style=flat-square)
![Type](https://img.shields.io/badge/Type-Checklist-22c55e?style=flat-square)

**Kaam:** Implementation order control karna. AI aur human dono ko pata rahega **next step kya hai**.

Project ko **phases** mein divide karo — confusion kam hoga, progress crystal clear dikhega.

<br/>

<details>
<summary>📋 <strong>TASKS.md — Full Template</strong> &nbsp;(click to expand ▼)</summary>

<br/>

```markdown
# Tasks — [Project Name]

## ⚙️ Phase 1: Setup
- [ ] Initialize project (Next.js / Vite / etc.)
- [ ] Configure folder structure per blueprint
- [ ] Add `.env.local` and `.env.example`
- [ ] Setup Tailwind CSS / UI component library

## 🏗️ Phase 2: Core Structure
- [ ] Create root layout (header, sidebar, footer shell)
- [ ] Create shared Navbar and Sidebar components
- [ ] Add routing structure and protected routes

## 🔐 Phase 3: Authentication
- [ ] Login page UI
- [ ] Register page UI
- [ ] Auth logic (Firebase / NextAuth / Clerk)
- [ ] Protected route wrapper setup

## ✨ Phase 4: Core Features
- [ ] Main data form (add / edit)
- [ ] Data list / table view
- [ ] Delete with confirmation dialog
- [ ] Filters / search functionality

## 🎨 Phase 5: UI Polish
- [ ] Loading skeleton states
- [ ] Empty states with illustration + CTA
- [ ] Error toast notifications
- [ ] Mobile responsiveness check

## 🧪 Phase 6: Testing & Cleanup
- [ ] Validate all main user flows
- [ ] Fix edge cases and error paths
- [ ] Remove all console.log statements
- [ ] Final code review

## 🚀 Phase 7: Deployment
- [ ] Final .env variable check
- [ ] Production build test locally
- [ ] Deploy to Vercel / Railway / platform of choice
- [ ] Post-deploy smoke test
```

</details>

<br/>

---

### 🔧 D) Tool-Specific Rules File

> **Apne tool ke hisaab se SIRF EK file banao:**

<br/>

| 🛠️ Agar Ye Tool Use Kar Rahe Ho | 📁 To Ye File Banao |
|:---|:---|
| **Cursor IDE** | `.cursor/rules/main.mdc` |
| **VS Code + GitHub Copilot** | `.github/copilot-instructions.md` |
| **Google Antigravity / Gemini** | `GEMINI.md` |

<br/>

Is file mein likho:

- AI ka response style aur tone
- Code generation ke rules
- Preferred tech stack
- Do-not-touch areas
- Naming conventions
- Explanation depth (verbose vs concise)

> [!IMPORTANT]
> Ek project mein teen mein se **sirf ek** rakho. Saath mein sab mat rakho — warna instructions **conflict** karenge.

---

## 🏗️ Layer 2 — Project Files *(AI Yahin Kaam Karega)*

> Ye actual app files hain. AI inhe generate aur expand karega — tum bas **guide** karoge.

<br/>

| 📁 Folder / File | 🎯 Kaam | 💡 Golden Rule |
|:---|:---|:---|
| `app/` or `src/` | Pages, layouts, routes | Page files **slim** rakho |
| `components/` | Reusable UI blocks | Same UI 2x use → **component banao** |
| `lib/` | Business logic, DB init, utilities | UI aur logic **mix mat karo** |
| `hooks/` | Custom React hooks | Data fetch, auth state, loading |
| `types/` | TypeScript interfaces | Har entity ka type define karo |
| `public/` | Images, icons, fonts | File names **simple and meaningful** rakho |
| `.env.local` | 🔒 API keys, secrets | **GitHub par KABHI nahi** |
| `package.json` | Dependencies and scripts | — |
| `tailwind.config.*` | Styling config | Blueprint ke according hi change karo |
| `tsconfig.*` | TypeScript config | Minimal changes, no duplication |

<br/>

---

## 🧪 Real Example — Expense Tracker

<div align="center">

**Tech Stack:**
![Next.js](https://img.shields.io/badge/Next.js_14-black?style=flat-square&logo=next.js)
![Firebase](https://img.shields.io/badge/Firebase-FF6F00?style=flat-square&logo=firebase&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)

</div>

<br/>

```
expense-tracker/
│
├── 📋 AGENTS.md                          ← AI ko project rules deta hai
├── 📋 PROJECT_BLUEPRINT.md               ← App ka full roadmap
├── 📋 TASKS.md                           ← Step-by-step development order
├── 🔧 GEMINI.md                          ← Tool rule (sirf ek)
│
├── 🔒 .env.local                         ← Secrets — GitHub par NAHI
├── package.json
├── tsconfig.json
├── tailwind.config.ts
├── next.config.ts
│
├── 📱 app/
│   ├── layout.tsx                        ← Root shell (header + sidebar)
│   ├── page.tsx                          ← Landing page
│   ├── globals.css
│   ├── login/
│   │   └── page.tsx                      ← Login screen
│   ├── register/
│   │   └── page.tsx                      ← Signup screen
│   ├── dashboard/
│   │   ├── layout.tsx                    ← Dashboard shell
│   │   └── page.tsx                      ← Summary + charts
│   ├── expenses/
│   │   ├── page.tsx                      ← Expense list
│   │   ├── new/page.tsx                  ← Add new expense
│   │   └── [id]/page.tsx                 ← Edit expense
│   └── api/
│       └── expenses/route.ts             ← REST API endpoint
│
├── 🧩 components/
│   ├── Sidebar.tsx                       ← Navigation links
│   ├── Navbar.tsx                        ← Top bar
│   ├── SummaryCards.tsx                  ← Total / monthly stats
│   ├── ExpenseForm.tsx                   ← Add / Edit form
│   ├── ExpenseTable.tsx                  ← Data table with actions
│   ├── ExpenseFilters.tsx                ← Category / date filters
│   ├── EmptyState.tsx                    ← No data illustration
│   └── LoadingSkeleton.tsx               ← Loading placeholder
│
├── ⚙️  lib/
│   ├── db.ts                             ← Firebase / DB init
│   ├── auth.ts                           ← Auth helpers
│   ├── expenses.ts                       ← CRUD logic
│   ├── validations.ts                    ← Input validation rules
│   └── utils.ts                          ← Format helpers
│
├── 🪝 hooks/
│   ├── useExpenses.ts                    ← Fetch + refresh expenses
│   └── useAuth.ts                        ← Auth state management
│
├── 📐 types/
│   └── expense.ts                        ← TypeScript interfaces
│
├── 🖼️  public/
│   ├── logo.png
│   └── icons/
│       ├── wallet.svg
│       └── chart.svg
│
└── .gitignore
```

<br/>

### 🔗 Feature → File Mapping

| ✨ Feature | 📁 File |
|:---|:---|
| Monthly summary + charts | `app/dashboard/page.tsx` |
| Add / Edit expense form | `components/ExpenseForm.tsx` |
| Expense list with filters | `components/ExpenseTable.tsx` |
| All CRUD operations | `lib/expenses.ts` |
| Form validation rules | `lib/validations.ts` |
| Data fetching + refresh | `hooks/useExpenses.ts` |
| TypeScript data shapes | `types/expense.ts` |

---

## 📌 Best-Practice Rules

> *Kisi bhi project ke liye — ye 8 rules hamesha yaad rakho.*

<br/>

```
╔══════════════════════════════════════════════════════════════╗
║                                                              ║
║   1.  📋  Pehle manual files, phir code.                     ║
║                                                              ║
║   2.  🔧  One tool, one rule file — conflict se bachao.      ║
║                                                              ║
║   3.  🧩  Reused UI ke liye component banao.                 ║
║                                                              ║
║   4.  🔒  Secrets → .env.local   |   Code mein? KABHI NAHI. ║
║                                                              ║
║   5.  ⚙️   Logic → lib/          |   UI → components/        ║
║                                                              ║
║   6.  📄  Page files ko lightweight rakho.                   ║
║                                                              ║
║   7.  ✅  Tasks ko phases mein divide karo.                  ║
║                                                              ║
║   8.  🗺️   PROJECT_BLUEPRINT.md = single source of truth.    ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

---

## 🗣️ AI Se Kaam Karwate Waqt Ye Bolo

> Har AI prompt mein ye **instructions copy-paste** karo:

<br/>

```
✅ PROJECT_BLUEPRINT.md follow karo
✅ Existing folder structure ko respect karo
✅ Unnecessary files mat banao
✅ Reusable components prefer karo
✅ Clean naming conventions follow karo
✅ Secret values kabhi expose mat karo
✅ Same logic duplicate mat karo
✅ Ek prompt mein ek hi focused task karo
```

---

## ⚡ TL;DR — Super Short Version

<br/>

| 🏷️ Layer | 📦 Kya Hai | 👤 Kaun Banata Hai |
|:---:|:---|:---:|
| 📋 Manual Files | Planning + Rules + Blueprint | **Tum** |
| 🔧 Tool File | AI editor behavior control | **Tum** |
| 🏗️ Project Files | Actual app code | **AI** *(guided by you)* |

<br/>

<div align="center">

### `Plan` &nbsp;→&nbsp; `Guide` &nbsp;→&nbsp; `Build` 🚀

*Structure strong hoga → AI fast kaam karega → Galtiyan kam hongi.*

<br/>

---

*Made with ❤️ for the AI-first development era &nbsp;·&nbsp; 2026*

</div>
