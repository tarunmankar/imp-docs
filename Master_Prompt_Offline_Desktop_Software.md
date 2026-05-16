# 🖥️ Master Prompt — AI se Offline Desktop Software ka Development Document Banwao

> **Internet ke bina chale — local machine pe kaam kare — yahi hai offline software**

---

## Offline Software ke liye Tech Stack Kya Hoga?

Online aur offline software ka fark samjho pehle:

| Cheez | Online Software | Offline Software |
|-------|----------------|-----------------|
| Database | Supabase (cloud) | SQLite (local file) |
| Deployment | Vercel (internet) | User ke computer pe install |
| Internet | Zaroori | Bilkul nahi chahiye |
| Data | Server pe | User ke computer pe |
| Updates | Auto | Manual install |
| Framework | Next.js | Electron + React |

**Offline Desktop ke liye Best Stack:**
- **Electron** — Web technologies se desktop app banana
- **React + Vite** — Fast UI development
- **Tailwind CSS + Shadcn UI** — Same styling
- **SQLite (better-sqlite3)** — Local database, internet nahi chahiye
- **Electron Builder** — .exe / .dmg installer banana

---

## How to Use This Prompt

1. Neeche ka prompt copy karo
2. `[PROJECT NAME]` aur `[ONE LINE DESCRIPTION]` replace karo
3. Claude / ChatGPT / Gemini mein paste karo
4. Jo document mile usse `README.md` ke naam se save karo

---

## The Master Prompt (Offline Desktop Software)

```
You are an expert Electron.js + React developer specializing in offline
desktop applications for small businesses in India.

I want to build: [PROJECT NAME & ONE LINE DESCRIPTION]
Example: "Medical Store Billing System — offline stock tracking,
GST invoicing, daily reports — runs without internet"

My tech stack (STRICT — do not change):
- Desktop Framework: Electron (latest stable)
- UI Framework: React + Vite
- Styling: Tailwind CSS + Shadcn UI
- Local Database: SQLite via better-sqlite3
- ORM: Drizzle ORM (for SQLite schema management)
- PDF Generation: jsPDF + jsPDF-autotable
- Excel Export: SheetJS (xlsx)
- Build/Installer: Electron Builder (.exe for Windows)
- Package Manager: npm

My level: Non-technical / Beginner — I use AI editors
(Cursor / Windsurf) to write all code.

Target OS: Windows 10/11 (primary), optional Mac support
Target User: Small business owner in Tier 2/3 Indian city
Internet Required: ZERO — must work 100% offline

---

Create a COMPLETE PROJECT DEVELOPMENT DOCUMENT in Markdown
with these exact sections:

## 1. PROJECT OVERVIEW
- What this app does (2-3 lines, simple Hinglish)
- Who uses it (roles: Admin, Staff, etc.)
- Why offline — what problem does local data solve
- Core user flows (numbered, plain text — no diagrams)

## 2. REQUIREMENTS DOCUMENT
- Must-have features (numbered list)
- Nice-to-have features (later phase)
- Out of scope (what we are NOT building)
- Number of users per role
- Offline-specific requirements (backup, data export, etc.)

## 3. DATABASE SCHEMA (SQLite)
- List all tables needed
- For each table: all columns with SQLite types and constraints
- Write complete CREATE TABLE SQL for every table
  (SQLite syntax — no uuid, use INTEGER PRIMARY KEY AUTOINCREMENT)
- Write all indexes for performance
- Note: No RLS needed — local database, single machine
- Include a db-setup.sql file content that creates all tables at once

## 4. ELECTRON PROJECT STRUCTURE
- Complete folder/file tree for this specific project
- Main process files (main/, preload/)
- Renderer process files (src/ — React components)
- IPC channels list (how UI talks to database)
- All React routes/pages listed
- All components listed by feature

## 5. AGENTS.md CONTENT
- Complete ready-to-use AGENTS.md file for this project
- Electron-specific rules (main vs renderer process)
- IPC communication rules
- SQLite query rules
- File naming conventions
- Security rules (contextIsolation, nodeIntegration)

## 6. PROJECT_BLUEPRINT.md CONTENT
- Complete ready-to-use blueprint
- Electron architecture explanation (main/renderer/preload)
- IPC channels map (channel name → what it does)
- Database file location on user's computer
- All pages with their purpose
- Module build order

## 7. TASKS.md CONTENT
- Complete checklist, phase by phase
- Every single task numbered (1.1, 1.2, 2.1...)
- Phase 1: Electron + SQLite setup
- Phase 2: Database + IPC layer
- Phase 3: Auth / Login (local password, no internet)
- Phase 4: Core features (one module at a time)
- Phase 5: Reports + PDF + Excel
- Phase 6: Backup / Restore feature
- Phase 7: Installer build (.exe)
- Every task small enough for ONE AI prompt

## 8. AI PROMPTS — ONE PER TASK
- For every major task in TASKS.md, write the exact prompt
- Format: Task number → Prompt (copy-paste ready)
- Prompts must be Electron/SQLite specific — not web/Supabase
- Each prompt structure:
  "Read AGENTS.md. Task [X.X]: [name].
   Build: [exact file path].
   This is [main process / renderer / preload].
   Requirements: [specific details].
   IPC channels needed: [list if any].
   Do NOT touch: [files to leave alone].
   After done: list files changed."

## 9. IPC CHANNELS REFERENCE
- Every IPC channel this project needs
- Format: channel name, direction, input, output, which db query
- Example:
  - Channel: 'products:getAll'
  - Direction: renderer → main → renderer
  - Input: { search?: string }
  - Output: Product[]
  - Query: SELECT * FROM products

## 10. ENVIRONMENT / CONFIG
- electron-builder config (package.json section)
- App name, version, icon setup
- Windows installer settings (.exe, NSIS)
- Database file path (where SQLite file saves on user PC)
- Auto-backup config

## 11. COMMON ERRORS FOR THIS PROJECT
- 5-8 errors specific to Electron + SQLite + this project's features
- For each: error message, why it happens in Electron context, exact fix

## 12. TESTING CHECKLIST
- Module-by-module testing for THIS project
- Test on actual Windows machine
- SQLite data persistence test
- PDF generation test
- Installer test (install → use → uninstall)
- Backup/restore test

## 13. BUILD & DISTRIBUTION CHECKLIST
- npm run build steps
- Electron Builder setup
- .exe installer generation
- How to give the .exe file to client
- How client installs it
- How to update (manual update process)

## 14. BACKUP STRATEGY
- How user's data will be backed up
- Export to USB / Google Drive option
- Restore from backup process
- Data migration between computers

---

RULES FOR YOUR RESPONSE:
- Write everything in Hinglish (Hindi + English mix) — simple language
- All code must be Electron + SQLite specific — NO Supabase, NO Vercel
- IPC pattern must be used for all DB operations (never direct DB in renderer)
- contextIsolation: true and nodeIntegration: false (security mandatory)
- All code blocks complete and copy-paste ready
- SQL must be SQLite syntax (not PostgreSQL)
- AI prompts must be specific to Electron architecture
- Do NOT write generic web advice — everything for OFFLINE DESKTOP
- Output must be one single Markdown document I can save as README.md
```

---

## Example — Kaise Fill Karna Hai

```
I want to build: Medical Store Billing System — offline stock tracking,
GST invoicing, purchase records — runs without internet on Windows PC
```

Ya:

```
I want to build: Coaching Center Management — offline student records,
fee collection, attendance, monthly reports — no internet needed
```

---

## Offline vs Online — Kab Kya Choose Karo

| Situation | Choice |
|-----------|--------|
| Client ke paas reliable internet nahi | **Offline** |
| Data security concern — data local chahiye | **Offline** |
| Single computer pe use hoga | **Offline** |
| Multiple branches, remote access chahiye | Online |
| Mobile se bhi access karna hai | Online |
| Multiple users, different locations | Online |

---

## Offline Stack Quick Reference

```
Electron App Structure:
│
├── main/              ← Node.js process (database, files)
│   ├── index.ts       ← App entry point
│   ├── database.ts    ← SQLite connection
│   └── ipc/           ← All IPC handlers (DB queries)
│
├── preload/
│   └── index.ts       ← Safe bridge between main & UI
│
├── src/               ← React UI (no direct DB access)
│   ├── pages/         ← All screens
│   └── components/    ← Reusable UI components
│
└── resources/
    └── app.db         ← SQLite database file (user's data)
```

**Golden Rule for Electron:**
> UI (React) kabhi directly database touch nahi karega.
> Sirf IPC ke through — renderer → preload → main → SQLite.

---

## Kisi Bhi Project ke Saath Use Karo

| Project | Description Example |
|---------|-------------------|
| Medical Store | stock, GST billing, purchase, expiry alerts |
| Coaching Center | students, fees, attendance, batches |
| Kirana / Grocery | inventory, billing, supplier, daily summary |
| Car Workshop | job cards, parts, service history, billing |
| Gym | members, fees, attendance, trainer |
| Hotel / Lodge | rooms, bookings, check-in/out, billing |
| School | students, fees, marks, attendance |
| Dairy / Milk | daily entries, party ledger, monthly bill |

---

*Save this file → use karo jab bhi offline desktop project shuru karo*
