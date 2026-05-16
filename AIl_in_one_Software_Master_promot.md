# 🚀 AI se Software Banao — Complete Master Prompt Guide
### *Freelancer & Startup ke liye — Cursor / Windsurf / Claude Code / ChatGPT*

![Version](https://img.shields.io/badge/version-3.0-blue) ![License](https://img.shields.io/badge/license-MIT-green) ![Stacks](https://img.shields.io/badge/stacks-5-orange) ![Tools](https://img.shields.io/badge/tools-Antigravity%20%7C%20Cursor%20%7C%20Claude%20Code-red) ![Language](https://img.shields.io/badge/language-Hinglish-purple)

> **Ye guide tumhare liye hai agar tum:**
> - AI tools se software banana chahte ho
> - Non-technical ho lekin business software sell karna chahte ho
> - Indian small businesses ke liye offline/online software banana chahte ho
> - Ek freelancer ya solo founder ho jis ke paas sirf AI tools hain

---

> ⚡ **TL;DR:** Sahi prompt copy karo → `[PROJECT NAME]` replace karo → AI editor mein paste karo → poora blueprint mile ga → task by task code banao → client ko becho.

---

## 📌 Table of Contents

1. [Ye Guide Kya Hai?](#-ye-guide-kya-hai)
2. [Pehle Decide Karo — Kaunsa Software?](#-pehle-decide-karo--kaunsa-software)
3. [Quick Decision Tree](#-quick-decision-tree)
4. [Part 1 — Online Web App (Next.js)](#-part-1--online-web-app-nextjs--browser-based)
5. [Part 2 — Offline Desktop App (Electron)](#-part-2--offline-desktop-app-electron--windows-exe)
6. [Part 2B — Offline Desktop App (Tauri)](#-part-2b--offline-desktop-app-tauri--lightweight-exe)
7. [Part 3A — Android App (React Native + Expo)](#-part-3a--android-app-react-native--expo)
8. [Part 3B — Android App (Flutter)](#-part-3b--android-app-flutter--dart)
9. [Bonus — Offline Desktop Multi-Stack Guide](#-bonus--offline-desktop-multi-stack-guide-electron--tauri--flutter)
10. [Kab Kaunsa Stack — Full Comparison](#-kab-kaunsa-stack--full-comparison-table)
11. [Combination Projects](#-combination-projects--jab-teen-teeno-chahiye)
12. [Best Business Ideas](#-best-business-ideas-for-these-prompts)
13. [Tool-Specific Rules Files — AGENTS.md, GEMINI.md, .cursorrules](#-tool-specific-rules-files)
14. [Google Antigravity — Agent-First IDE](#-google-antigravity--agent-first-ide)
15. [How to Use — Step by Step](#-how-to-use--step-by-step)
16. [Recommended Path for Beginners](#-recommended-path-for-beginners)

---

## 🎯 Ye Guide Kya Hai?

Ye guide **ready-made master prompts** ka collection hai jo tum seedha **Google Antigravity, Cursor, Windsurf, Claude Code ya ChatGPT** mein paste kar sakte ho.

Har prompt se ek **complete development document** generate hota hai jisme:
- Database schema
- Folder structure
- Step-by-step tasks
- AI prompts har task ke liye
- Build + installer config
- Testing checklist

**Ek baar prompt run karo → poora project blueprint taiyaar.**

---

## 📋 Pehle Decide Karo — Kaunsa Software?

```
ONLINE WEB APP           → Part 1 use karo
(Browser mein chale,
internet zaroori,
koi bhi device se access)

OFFLINE DESKTOP (Easy)   → Part 2 use karo  [Electron]
(Windows PC pe install,
internet nahi chahiye,
.exe file, beginner friendly)

OFFLINE DESKTOP (Pro)    → Part 2B use karo [Tauri]
(Windows PC pe install,
5-15MB chhota installer,
fast + secure, Rust backend)

ANDROID MOBILE APP       → Part 3A (React Native) ya 3B (Flutter)
(Phone pe install,
Play Store ya direct APK,
offline bhi kaam kare)
```

---

## 🌳 Quick Decision Tree

```
Q1: Client ke paas reliable internet hai?
    ├── NAHI → Q2
    └── HAAN → Part 1 (Web App — Next.js)

Q2: PC pe use hoga ya phone pe?
    ├── PC pe → Q2a
    └── Phone pe → Q3

Q2a: Beginner ho ya installer size matter karta hai?
    ├── Beginner / jaldi banana hai → Part 2 (Electron) ✅ Recommended
    ├── Chhota installer + fast startup → Part 2B (Tauri) ⚡
    └── Desktop + Android dono → Part 3B (Flutter)

Q3: Sirf Android ya Desktop bhi chahiye?
    ├── Sirf Android (JS prefer) → Part 3A (React Native/Expo)
    ├── Sirf Android (native feel) → Part 3B (Flutter)
    └── Desktop + Android dono → Part 3B (Flutter)

Q4: Multiple branches / locations se access chahiye?
    ├── HAAN → Part 1 (Web — cloud data)
    └── NAHI → Part 2 ya 2B (Desktop)

Q5: Field workers / delivery / collection agents hain?
    └── HAAN → Part 3A ya 3B (Android)

QUICK ANSWER:
  Pehli app banana hai?           → Electron (Part 2)
  Professional premium client?    → Tauri (Part 2B)
  Phone + PC dono?               → Flutter (Part 3B)
  Multiple locations?             → Next.js (Part 1)
```

---

## 🌐 Part 1 — Online Web App (Next.js) — Browser Based

### Kab Use Karo

| ✅ Use Karo Jab | ❌ Mat Use Karo Jab |
|---|---|
| Multiple branches hain | Internet reliable nahi hai |
| Owner remotely reports dekhna chahta hai | Single PC only |
| Multiple users ek saath kaam karein | Data sirf local chahiye |
| Cloud backup chahiye | Client non-technical aur computer se dar-ta hai |
| Mobile browser se bhi access ho | Low budget client hai |

### Tech Stack

```
Framework    → Next.js 14 App Router + TypeScript
Styling      → Tailwind CSS + Shadcn UI
Database     → Supabase (PostgreSQL + Auth)
Deployment   → Vercel
```

### Best Business Apps for Web

- GST Billing (multi-branch)
- Inventory with remote access
- HR/Payroll system
- School ERP
- Hospital management (multi-doctor)
- Distributor order management

---

### 📋 THE PROMPT — Part 1 (Web App)

```
You are an expert Next.js developer and technical architect.

I want to build: [PROJECT NAME & ONE LINE DESCRIPTION]
Example: "Medical Store Billing System — stock tracking,
GST invoicing, daily reports"

My tech stack (STRICT — don't change):
- Framework: Next.js 14 App Router + TypeScript
- Styling: Tailwind CSS + Shadcn UI
- Database + Auth: Supabase (PostgreSQL)
- Deployment: Vercel

My level: Non-technical / Beginner — I use AI editors
(Cursor / Windsurf) to build.

---

Create a COMPLETE PROJECT DEVELOPMENT DOCUMENT in Markdown
with these exact sections:

## 1. PROJECT OVERVIEW
- What this app does (2-3 lines)
- Who uses it (roles: Admin, Staff, etc.)
- Core user flows (numbered, plain text)

## 2. REQUIREMENTS DOCUMENT
- Must-have features (numbered list)
- Nice-to-have features (later phase)
- Out of scope (what we are NOT building)
- Number of users per role

## 3. DATABASE SCHEMA
- List all tables needed
- For each table: all columns with type, constraints, comment
- Every table MUST have: id (uuid), user_id (uuid → auth.users),
  created_at (timestamp)
- Write complete CREATE TABLE SQL for every table
- Write all RLS policies SQL (SELECT, INSERT, UPDATE, DELETE)
- If multi-role: write role-based policy SQL

## 4. FOLDER STRUCTURE
- Complete folder/file tree for this specific project
- All app routes listed
- All components listed by feature

## 5. AGENTS.md CONTENT
- Complete ready-to-use AGENTS.md for this project
- Tech stack rules, file naming, coding rules, response format

## 6. PROJECT_BLUEPRINT.md CONTENT
- Complete ready-to-use blueprint
- Overview, roles, schema summary, all routes with access levels,
  module build order

## 7. TASKS.md CONTENT
- Complete checklist phase by phase
- Every task numbered (1.1, 1.2, 2.1...)
- Ordered foundation to polish
- Every task small enough for ONE AI prompt

## 8. AI PROMPTS — ONE PER TASK
- Exact prompt for every major task in TASKS.md
- Format: Task number → copy-paste ready prompt
- Structure: "Read AGENTS.md. Task [X.X]: [name].
  Build: [exact file]. Requirements: [specific].
  Do NOT touch: [other files]. After done: list files changed."

## 9. ENVIRONMENT VARIABLES
- Every .env.local variable needed
- Mark NEXT_PUBLIC vs server-only
- Explain what each one is for

## 10. COMMON ERRORS FOR THIS PROJECT
- 5-8 errors specific to this project's features
- Each: error message, why it happens, exact fix

## 11. TESTING CHECKLIST
- Module-by-module testing specific to THIS project
- Browser tests, API tests, mobile responsive tests

## 12. DEPLOYMENT CHECKLIST
- Pre-deploy, deploy, post-deploy steps
- Supabase redirect URL setup
- Custom domain connect steps

---

RULES:
- Hinglish mein likho (Hindi + English mix) — simple language
- All code complete and copy-paste ready
- SQL production-ready with RLS
- AI prompts specific — no vague instructions
- Everything specific to [PROJECT NAME] — no generic advice
- One single Markdown document output
```

---

## 💻 Part 2 — Offline Desktop App (Electron) — Windows .exe

### Kab Use Karo

| ✅ Use Karo Jab | ❌ Mat Use Karo Jab |
|---|---|
| Internet nahi hai client ke paas | Multiple branches access chahiye |
| Data sirf ek PC pe chahiye | Mobile use bhi hoga |
| Client ko .exe dena hai | Real-time sync chahiye |
| Fast billing chahiye bina internet | Play Store pe dena hai |
| Beginner ho aur jaldi MVP banana hai | |

### Tech Stack

```
Framework    → Electron (latest stable)
UI           → React + Vite + TypeScript
Styling      → Tailwind CSS + Shadcn UI
Database     → SQLite via better-sqlite3
ORM          → Drizzle ORM
PDF          → jsPDF + jsPDF-autotable
Excel        → SheetJS (xlsx)
Installer    → Electron Builder (.exe)
```

### Best Business Apps for Electron

- Medical Store Billing
- GST Billing Software
- Kirana Store POS
- Hardware Shop Management
- Jewellery Billing
- Restaurant POS (single outlet)
- Pathology Lab Software

---

### 📋 THE PROMPT — Part 2 (Electron Desktop)

```
You are an expert Electron.js + React developer specializing
in offline desktop applications for small businesses in India.

I want to build: [PROJECT NAME & ONE LINE DESCRIPTION]
Example: "Medical Store Billing System — offline stock tracking,
GST invoicing, daily reports — runs without internet on Windows"

My tech stack (STRICT — don't change):
- Desktop Framework: Electron (latest stable)
- UI Framework: React + Vite + TypeScript
- Styling: Tailwind CSS + Shadcn UI
- Local Database: SQLite via better-sqlite3
- ORM: Drizzle ORM
- PDF: jsPDF + jsPDF-autotable
- Excel: SheetJS (xlsx)
- Installer: Electron Builder (.exe for Windows)
- Package Manager: npm

My level: Non-technical / Beginner — I use AI editors
(Cursor / Windsurf) to build.

Target OS: Windows 10/11
Internet Required: ZERO — 100% offline
Target User: Small business owner, Tier 2/3 Indian city

---

Create a COMPLETE PROJECT DEVELOPMENT DOCUMENT in Markdown
with these exact sections:

## 1. PROJECT OVERVIEW
- What this app does (2-3 lines, Hinglish)
- Who uses it (roles: Admin, Staff, etc.)
- Why offline — what problem does local data solve
- Core user flows (numbered, plain text)

## 2. REQUIREMENTS DOCUMENT
- Must-have features (numbered list)
- Nice-to-have features (later phase)
- Out of scope
- Number of users per role
- Offline-specific requirements (backup, export, etc.)

## 3. DATABASE SCHEMA (SQLite)
- List all tables needed
- All columns with SQLite types and constraints
  (SQLite syntax: INTEGER PRIMARY KEY AUTOINCREMENT,
   TEXT, REAL, INTEGER, BLOB)
- NO uuid — use INTEGER autoincrement IDs
- Complete CREATE TABLE SQL for every table
- All indexes for performance
- db-setup.sql file content (creates all tables at first launch)

## 4. ELECTRON PROJECT STRUCTURE
- Complete folder/file tree
- main/ — Node.js process files
- preload/ — bridge files
- src/ — React UI files
- IPC channels list (how UI talks to database)
- All React pages listed
- All components listed by feature

## 5. AGENTS.md CONTENT
- Complete ready-to-use AGENTS.md for this project
- Electron-specific rules:
  * main process vs renderer process — kya kahan hoga
  * IPC rules — renderer database directly NEVER touch karega
  * contextIsolation: true, nodeIntegration: false (mandatory)
  * SQLite queries only in main process
- File naming rules, Coding rules

## 6. PROJECT_BLUEPRINT.md CONTENT
- Electron architecture (main / preload / renderer)
- IPC channels map: channel name → what it does → DB query
- SQLite file location on user's Windows PC
- All pages with purpose
- Module build order

## 7. TASKS.md CONTENT
- Complete checklist phase by phase:
  * Phase 1: Electron + Vite + React setup
  * Phase 2: SQLite + Drizzle ORM setup
  * Phase 3: IPC layer (all channels)
  * Phase 4: Local login (no internet — stored in SQLite)
  * Phase 5: Core modules (one by one)
  * Phase 6: PDF + Excel export
  * Phase 7: Backup / Restore feature
  * Phase 8: Windows .exe installer build
- Every task numbered, small enough for ONE AI prompt

## 8. AI PROMPTS — ONE PER TASK
- Exact copy-paste prompt for every major task
- Structure: "Read AGENTS.md. Task [X.X]: [name].
  This is [main process / renderer / preload].
  Build: [exact file]. IPC channels needed: [list].
  Requirements: [specific]. Do NOT touch: [files].
  After done: list files changed."
- All prompts Electron/SQLite specific

## 9. IPC CHANNELS REFERENCE
- Every IPC channel this project needs
- For each channel:
  * Name: 'feature:action' (e.g. 'products:getAll')
  * Direction: renderer → main → renderer
  * Input: what data goes in
  * Output: what data comes back
  * SQLite query it runs

## 10. BUILD & INSTALLER CONFIG
- electron-builder config (package.json section)
- App name, version, icon setup (.ico file)
- Windows NSIS installer settings
- SQLite file path on user's PC (AppData/Roaming/[AppName]/database.db)
- How to give .exe to client
- How client installs it
- Manual update process (new .exe dena)

## 11. BACKUP STRATEGY
- SQLite file location — user ko kahan milega
- USB backup process
- Folder copy backup
- Restore process on new PC
- In-app backup button workflow

## 12. COMMON ERRORS — ELECTRON SPECIFIC
- 5-8 errors:
  * "require is not defined" in renderer
  * IPC not responding
  * better-sqlite3 build error
  * SQLite file not found
- Each: error message, why it happens, exact fix

## 13. TESTING CHECKLIST
- Offline test (disconnect internet → sab kaam kare)
- SQLite data save/load test
- PDF generation test
- Excel export test
- Installer test on clean Windows
- Backup restore test

---

RULES:
- Hinglish mein likho — simple language
- NO Supabase, NO Firebase, NO cloud
- SQLite ONLY in main process
- IPC mandatory for all DB operations
- contextIsolation: true, nodeIntegration: false
- AI prompts Electron-architecture aware
- One single Markdown document output
```

---

## ⚡ Part 2B — Offline Desktop App (Tauri) — Lightweight .exe

### Kab Use Karo

| ✅ Use Karo Jab | ❌ Mat Use Karo Jab |
|---|---|
| Chhota installer size chahiye (5-15MB vs Electron ka 150MB+) | Bilkul beginner ho, Rust uncomfortable hai |
| Fast startup + low RAM usage chahiye | npm ecosystem heavily use karna hai |
| Professional / premium client hai | Jaldi MVP banana hai |
| Better security + performance chahiye | AI tools se Rust code likhwana mushkil lagta hai |
| Electron seekh liya, ab optimize karna hai | |

### Electron vs Tauri — Key Difference

```
Electron  → Node.js backend  → Heavy (150MB+) → Easy  → Beginner ✅
Tauri     → Rust backend     → Light (5-15MB)  → Hard  → Intermediate ⚡
```

### Tech Stack

```
Framework    → Tauri v2
Frontend     → React + Vite + TypeScript
Styling      → Tailwind CSS + Shadcn UI
Backend      → Rust
Database     → SQLite via rusqlite / SQLx
PDF          → jsPDF + jsPDF-autotable (frontend)
Excel        → SheetJS (xlsx) (frontend)
Installer    → Tauri Bundle (.msi / .exe)
```

### Best Business Apps for Tauri

- Fast POS systems (instant billing, <1s startup)
- Lightweight inventory management tools
- Admin dashboards (office use)
- Internal CRM / salesman tools
- Premium version of Electron apps (same features, smaller size)
- Cyber cafe / kiosk software
- Billing software for laptop users (low RAM)

> 💡 **Tip:** Agar client pehle se Electron app use kar raha hai aur complain karta hai ki "heavy hai" ya "slow start hota hai" — Tauri mein rewrite karo aur premium price lo.

---

### 📋 THE PROMPT — Part 2B (Tauri)

```
You are an expert Tauri v2 + Rust developer specializing in
lightweight offline desktop applications for small businesses in India.

I want to build: [PROJECT NAME & ONE LINE DESCRIPTION]
Example: "Medical Store Billing System — offline stock tracking,
GST invoicing, daily reports — fast lightweight .exe for Windows"

My tech stack (STRICT — don't change):
- Desktop Framework: Tauri v2
- Frontend: React + Vite + TypeScript
- Styling: Tailwind CSS + Shadcn UI
- Backend Language: Rust
- Local Database: SQLite via rusqlite (in Rust backend)
- PDF: jsPDF + jsPDF-autotable (frontend)
- Excel: SheetJS (xlsx) (frontend)
- Installer: Tauri Bundle (.msi / .exe for Windows)
- Package Manager: npm (frontend) + Cargo (Rust)

My level: Intermediate — I use AI editors (Cursor / Windsurf).
I understand basics of Electron. Now trying Tauri.

Target OS: Windows 10/11
Internet Required: ZERO — 100% offline
Target User: Small business owner, Tier 2/3 Indian city

---

Create a COMPLETE PROJECT DEVELOPMENT DOCUMENT in Markdown
with these exact sections:

## 1. PROJECT OVERVIEW
- What this app does (2-3 lines, Hinglish)
- Why Tauri — Electron se better kaise (size, speed, security)
- Who uses it (roles: Admin, Staff, etc.)
- Core user flows (numbered, plain text)

## 2. REQUIREMENTS DOCUMENT
- Must-have features (numbered)
- Nice-to-have features
- Out of scope
- Offline-specific requirements (backup, export)

## 3. DATABASE SCHEMA (SQLite via Rust)
- All tables with columns
- SQLite data types (INTEGER, TEXT, REAL, BLOB)
- INTEGER PRIMARY KEY AUTOINCREMENT only — NO uuid
- Complete CREATE TABLE SQL for every table
- All indexes for performance
- db-setup.sql content
- Rust struct for each table (for rusqlite mapping)

## 4. TAURI PROJECT STRUCTURE
- Complete folder/file tree:
  * src-tauri/ — Rust backend
    - src/main.rs
    - src/commands/ (each feature = one file)
    - src/db/ (database layer)
    - Cargo.toml
  * src/ — React frontend
    - pages/
    - components/
    - hooks/
    - lib/tauri-bridge.ts (invoke wrappers)
- All React pages listed
- All Rust command files listed

## 5. AGENTS.md CONTENT
- Tauri-specific architecture rules:
  * Rust handles ALL SQLite — frontend never touches DB
  * invoke() mandatory for all backend calls
  * NO direct filesystem access from frontend
  * Rust commands in src-tauri/src/commands/ only
  * Frontend ONLY calls tauri-bridge.ts functions
  * No remote URLs, no cloud, offline-only
- File naming rules
- Rust coding rules (safe unwrap handling)
- Frontend coding rules

## 6. PROJECT_BLUEPRINT.md CONTENT
- Tauri architecture: Frontend → invoke() → Rust Command → SQLite
- All Rust commands list (name, input, output, SQL query)
- All React pages with purpose
- Tauri invoke() bridge map
- Module build order

## 7. TASKS.md CONTENT
- Complete checklist phase by phase:
  * Phase 1: Tauri v2 + React + Vite project setup
  * Phase 2: SQLite + rusqlite setup in Rust
  * Phase 3: Rust commands layer (all features)
  * Phase 4: Frontend invoke() bridge (tauri-bridge.ts)
  * Phase 5: Local login (PIN stored in SQLite via Rust)
  * Phase 6: Core modules (one by one)
  * Phase 7: PDF + Excel export (jsPDF + SheetJS in frontend)
  * Phase 8: Backup / Restore (Rust filesystem command)
  * Phase 9: Windows installer (.msi) build
- Every task numbered, small enough for ONE AI prompt

## 8. AI PROMPTS — ONE PER TASK
- Exact copy-paste prompt for every major task
- Structure: "Read AGENTS.md. Task [X.X]: [name].
  This is [Rust backend / React frontend / tauri-bridge].
  Build: [exact file path].
  Rust commands needed: [list] OR invoke() calls needed: [list].
  Requirements: [specific]. Do NOT touch: [files].
  After done: list files changed."
- All prompts Tauri v2 + Rust specific

## 9. TAURI COMMANDS REFERENCE
- Every Rust command this project needs
- For each command:
  * Function name: #[tauri::command] fn name()
  * Input params (Rust types)
  * Output type (Result<T, String>)
  * SQLite query it runs
  * Frontend invoke() call: await invoke('name', { params })
  * tauri-bridge.ts wrapper function

## 10. BUILD & INSTALLER CONFIG
- tauri.conf.json complete config
- Cargo.toml dependencies
- App name, version, icon setup (.ico)
- tauri bundle --target x86_64-pc-windows-msvc
- SQLite file path on user's PC (AppData)
- How to give installer to client
- Manual update process
- App size comparison: Electron vs Tauri

## 11. BACKUP STRATEGY
- SQLite file location (Rust: app_data_dir())
- In-app backup button (Rust command: copy file to USB)
- Restore process
- Moving to new PC

## 12. COMMON ERRORS — TAURI SPECIFIC
- 8-10 errors:
  * "command not found" — tauri command not registered
  * Rust build failed — Cargo dependency issue
  * invoke() returns undefined — wrong command name
  * SQLite file not created on first launch
  * WebView2 not installed on client Windows
  * rusqlite compile error on Windows
  * "tauri::command" macro error — wrong return type
- Each: error message, why it happens, exact fix

## 13. TESTING CHECKLIST
- cargo build first (Rust errors check)
- npm run tauri dev (dev mode test)
- invoke() call test (each command)
- SQLite data persistence test
- PDF + Excel export test
- tauri build (release .msi test)
- Install on clean Windows (WebView2 check)
- Offline test (no internet)

---

RULES:
- Hinglish mein likho — simple language
- NO Supabase, Firebase, cloud
- Rust handles ALL SQLite — never in frontend
- invoke() mandatory for ALL backend calls
- tauri-bridge.ts wrappers for all invoke calls
- AI prompts clearly mention: Rust file ya frontend file
- One single Markdown document output
```

---

## 📱 Part 3A — Android App (React Native + Expo)

### Kab Use Karo

| ✅ Use Karo Jab | ❌ Mat Use Karo Jab |
|---|---|
| Sirf Android phone chahiye | Desktop app bhi chahiye |
| JS/React already jaante ho | Dart seekhna nahi | 
| Fast MVP banana hai phone ke liye | Complex native hardware access |
| Field workers ke liye app | iOS bhi chahiye (paid Apple dev account) |
| WhatsApp se APK share karna | |

### Tech Stack

```
Framework    → React Native + Expo SDK (latest)
Language     → TypeScript
Navigation   → Expo Router (file-based)
Database     → expo-sqlite (offline local)
State        → Zustand ya Jotai
Styling      → NativeWind (Tailwind for RN)
PDF          → expo-print + expo-sharing
Build        → EAS Build (APK)
```

---

### 📋 THE PROMPT — Part 3A (React Native + Expo)

```
You are an expert React Native + Expo developer specializing
in Android business apps for small businesses in India.

I want to build: [PROJECT NAME & ONE LINE DESCRIPTION]
Example: "Medical Store Billing App — scan barcode, create bills,
view stock — works on Android phone without laptop"

My tech stack (STRICT — don't change):
- Framework: React Native + Expo SDK (latest stable)
- Language: TypeScript
- Navigation: Expo Router (file-based routing)
- Local Database (offline): expo-sqlite
- State Management: Zustand
- Styling: NativeWind (Tailwind for React Native)
- PDF: expo-print + expo-sharing
- Build: EAS Build → APK
- Distribution: WhatsApp / Direct install / Play Store

My level: Non-technical / Beginner — I use AI editors
(Cursor / Windsurf) to build.

Target: Android phones (Android 7+)
Offline Support: YES — must work in airplane mode
Internet: Optional (only for sync if needed)

---

Create a COMPLETE PROJECT DEVELOPMENT DOCUMENT in Markdown
with these exact sections:

## 1. PROJECT OVERVIEW
- What this app does (2-3 lines, Hinglish)
- Who uses it on phone
- Why mobile — what problem phone solves
- Core user flows (numbered, plain text)

## 2. REQUIREMENTS DOCUMENT
- Must-have features
- Nice-to-have features
- Out of scope
- All screens list
- Offline requirements

## 3. DATABASE SCHEMA (expo-sqlite)
- All tables with columns
- SQLite data types (TEXT, INTEGER, REAL, BLOB)
- INTEGER PRIMARY KEY AUTOINCREMENT only — NO uuid
- Complete CREATE TABLE SQL
- Database initialization code (TypeScript)

## 4. REACT NATIVE PROJECT STRUCTURE
- Complete folder/file tree
- app/ (Expo Router screens)
- components/ (reusable)
- hooks/
- services/ (database layer)
- utils/
- All screens listed by feature

## 5. AGENTS.md CONTENT
- React Native specific rules:
  * NO HTML elements (div/p/span) — use View/Text/TouchableOpacity
  * NO browser APIs — Expo APIs only
  * NativeWind classes only (no inline StyleSheet unless needed)
  * expo-sqlite only in service layer — not in screens
  * Offline-first mindset
- File naming rules (snake_case files, PascalCase components)
- Coding rules

## 6. PROJECT_BLUEPRINT.md CONTENT
- App architecture (Screen → Hook → Service → SQLite)
- All screens map with Expo Router paths
- Database services list
- Module build order

## 7. TASKS.md CONTENT
- Complete checklist:
  * Phase 1: Expo project setup + NativeWind config
  * Phase 2: Expo Router navigation (all blank screens)
  * Phase 3: expo-sqlite setup + all tables
  * Phase 4: Local PIN login screen
  * Phase 5: Core features (one by one)
  * Phase 6: PDF generation + share
  * Phase 7: APK build via EAS
- Every task numbered, ONE AI prompt size

## 8. AI PROMPTS — ONE PER TASK
- Exact copy-paste prompt for every major task
- Structure: "Read AGENTS.md. Task [X.X]: [name].
  Build: [exact file path]. This is a React Native screen.
  Use: [specific Expo APIs / components].
  Requirements: [specific]. DO NOT use HTML elements.
  Do NOT touch: [files]. After done: list files changed."

## 9. EXPO CONFIG & DEPENDENCIES
- app.json / app.config.js complete config
- Every package needed with install command
- expo-sqlite setup code
- EAS build profile config (eas.json)
- Android permissions (CAMERA, WRITE_EXTERNAL, etc.)

## 10. APK BUILD & DISTRIBUTION
- EAS account setup steps
- eas build --platform android command
- APK vs AAB — kab kya
- WhatsApp se APK share karna
- Play Store publish (optional)
- App update process

## 11. COMMON ERRORS — REACT NATIVE SPECIFIC
- 5-8 errors:
  * "Text strings must be rendered within Text component"
  * expo-sqlite not working
  * NativeWind classes not applying
  * EAS build failing
  * Android permission denied
- Each: error, why, exact fix

## 12. TESTING CHECKLIST
- Real Android phone test (not just simulator)
- SQLite persistence test (close app → reopen)
- Offline test (airplane mode)
- APK install test
- All screens on small screen (5 inch)

---

RULES:
- Hinglish mein likho
- NO HTML (div, p, span) — React Native only
- NO browser APIs — Expo APIs only
- Offline-first mindset
- NativeWind for styling
- One single Markdown document output
```

---

## 🦋 Part 3B — Android App (Flutter) — Dart

### Kab Use Karo

| ✅ Use Karo Jab | ❌ Mat Use Karo Jab |
|---|---|
| Desktop (Windows) + Android dono chahiye | Sirf phone, JS prefer karte ho |
| Native UI feeling chahiye | npm ecosystem use karna hai |
| Long-term stable codebase | Quick MVP in days |
| Tablet support chahiye | AI tools kabhi kabhi Flutter code galat dete hain |
| Performance critical hai | |

### Tech Stack

```
Framework    → Flutter (latest stable)
Language     → Dart
Navigation   → GoRouter
Database     → SQLite via sqflite + drift ORM
State        → Riverpod (flutter_riverpod)
PDF          → pdf package (dart)
Build        → flutter build apk
Output       → APK for Android + Windows .exe
```

---

### 📋 THE PROMPT — Part 3B (Flutter)

```
You are an expert Flutter developer specializing in
Android + Windows apps for small businesses in India.

I want to build: [PROJECT NAME & ONE LINE DESCRIPTION]
Example: "Medical Store Billing App — scan barcode, create bills,
view stock — works on Android phone without laptop"

My tech stack (STRICT — don't change):
- Framework: Flutter (latest stable)
- Language: Dart
- Navigation: GoRouter
- Local Database (offline): SQLite via sqflite + drift ORM
- State Management: Riverpod (flutter_riverpod)
- PDF: pdf package (dart)
- Build: flutter build apk (Android) + flutter build windows
- Output: APK for Android, .exe for Windows

My level: Non-technical / Beginner — I use AI editors
(Cursor / Windsurf) to build.

Target: Android phones (Android 6+) + Windows 10/11
Offline Support: YES — 100% offline
No Firebase. No Supabase. No cloud.

---

Create a COMPLETE PROJECT DEVELOPMENT DOCUMENT in Markdown
with these exact sections:

## 1. PROJECT OVERVIEW
- What this app does (2-3 lines, Hinglish)
- Who uses it on phone / PC
- Why mobile+desktop — what problems both solve
- Core user flows (numbered)

## 2. REQUIREMENTS DOCUMENT
- Must-have features
- Nice-to-have features
- Out of scope
- All screens list
- Offline requirements

## 3. DATA STORAGE PLAN (Drift + SQLite)
- All Drift table classes (Dart code)
- DAO (Data Access Object) for each table
- Database initialization code
- No cloud sync

## 4. FLUTTER PROJECT STRUCTURE
- Complete folder/file tree
- lib/
  * main.dart
  * app/router.dart
  * features/ (feature-first structure)
  * shared/widgets/
  * shared/utils/
  * data/local/ (drift databases)
- All screens listed by feature

## 5. AGENTS.md CONTENT
- Flutter-specific rules:
  * StatelessWidget vs ConsumerWidget (Riverpod)
  * Riverpod provider rules
  * Drift database only in repository layer
  * No business logic in UI widgets
  * Feature-first folder strictly
- File naming (snake_case files, PascalCase classes)

## 6. PROJECT_BLUEPRINT.md CONTENT
- Flutter architecture: UI → Provider → Repository → Database
- All screens map
- Riverpod providers list
- Drift tables + DAOs
- GoRouter routes map
- Module build order

## 7. TASKS.md CONTENT
- Complete checklist:
  * Phase 1: Flutter project + pubspec.yaml
  * Phase 2: GoRouter navigation (blank screens)
  * Phase 3: Drift database + all tables
  * Phase 4: Local PIN login
  * Phase 5: Core features (one by one)
  * Phase 6: PDF generation
  * Phase 7: APK + Windows build
- Every task numbered, ONE AI prompt size

## 8. AI PROMPTS — ONE PER TASK
- Exact copy-paste prompts
- Structure: "Read AGENTS.md. Task [X.X]: [name].
  Build: [exact file path]. This is a Flutter widget/screen.
  Use Riverpod for state. Use Drift for database.
  Requirements: [specific]. Do NOT touch: [files].
  After done: list files changed."

## 9. PUBSPEC.YAML & CONFIG
- Complete pubspec.yaml with all dependencies + versions
- Android permissions in AndroidManifest.xml
- Drift build_runner setup
- APK build command
- Windows build command

## 10. APK & WINDOWS BUILD + DISTRIBUTION
- flutter build apk --release steps
- flutter build windows steps
- APK signing keystore setup
- WhatsApp se APK share karna
- .exe client ko dene ka process

## 11. COMMON ERRORS — FLUTTER SPECIFIC
- 5-8 errors:
  * "A build method returned null"
  * Drift build_runner errors
  * Riverpod provider not found
  * APK release signing error
  * Windows runner not found
- Each: error, why, exact fix

## 12. TESTING CHECKLIST
- Real Android device test
- Drift database persistence test
- Offline mode test (airplane mode)
- Release APK test (not debug)
- Windows .exe test

---

RULES:
- Hinglish mein likho
- NO JavaScript/TypeScript references
- Riverpod for ALL state
- Drift for ALL local database
- Feature-first folder strictly
- No Firebase, No Supabase, No cloud
- One single Markdown document output
```

---

## 🔧 Bonus — Offline Desktop Multi-Stack Guide (Electron + Tauri + Flutter)

Agar tum ek hi project ke liye **teeno desktop stacks compare** karna chahte ho ya client ko choice dena chahte ho — ye master prompt use karo.

### Kab Use Karo

- Professional client hai jo premium software chahta hai
- Tum Electron se shuru karke baad mein Tauri/Flutter try karna chahte ho
- Ek hi codebase se Windows + Android banana chahte ho (Flutter)
- Architecture comparison + blueprint ek saath chahiye

---

### 📋 THE PROMPT — Multi-Stack Offline Desktop

```
You are an expert offline software architect and full-stack
desktop/mobile app developer specializing in Indian small business software.

I want to build:
[PROJECT NAME & ONE LINE DESCRIPTION]
Example: "Medical Store Billing System — offline stock tracking,
GST invoicing, daily reports — runs without internet on Windows"

---

Build a COMPLETE OFFLINE BUSINESS SOFTWARE DEVELOPMENT DOCUMENT.

This software MUST:
- Work 100% offline
- Store all data locally (SQLite)
- Run fast on low-end PCs
- Work for Indian small businesses
- Support Windows 10/11
- Be beginner-friendly for AI-assisted coding
- Be sellable to multiple clients

---

Create the document for ALL THREE stacks separately:

1. Electron Stack (React + Vite + TypeScript + better-sqlite3)
2. Tauri Stack (React + Vite + TypeScript + Rust backend)
3. Flutter Stack (Dart + Riverpod + sqflite + Windows + Android)

---

# FOR EACH STACK, CREATE ALL SECTIONS:

## 1. PROJECT OVERVIEW
## 2. REQUIREMENTS DOCUMENT
## 3. DATABASE SCHEMA (SQLite)
   - INTEGER PRIMARY KEY AUTOINCREMENT only
   - NO UUID, NO PostgreSQL syntax
## 4. PROJECT STRUCTURE (stack-specific folders)
## 5. AGENTS.md CONTENT (stack-specific rules)
## 6. PROJECT_BLUEPRINT.md CONTENT
## 7. TASKS.md CONTENT (phase by phase)
## 8. AI PROMPTS — ONE PER TASK
   Format: "Read AGENTS.md. Task [X.X]: [name].
   This is [frontend/backend/main/preload/Rust/Dart].
   Build: [exact file]. Requirements: [details].
   Do NOT touch: [files]. After done: list changed files."
## 9. IPC / BRIDGE CHANNELS REFERENCE
   - Electron: ipcMain/ipcRenderer/preload
   - Tauri: invoke() + Rust commands
   - Flutter: Repository/service pattern
## 10. BUILD & INSTALLER CONFIG
## 11. BACKUP STRATEGY
## 12. COMMON ERRORS (stack-specific)
## 13. TESTING CHECKLIST

---

TARGET USER:
- Small business owner, Tier 2/3 Indian cities
- Non-technical users, Hindi-speaking staff
- Offline environments

INTERNET REQUIREMENT: ZERO

STRICT RULES:
- NO Supabase, Firebase, Vercel, cloud
- SQLite ONLY, Offline-first ONLY
- Security + Architecture separation mandatory

OUTPUT: One single detailed Markdown document

WRITING STYLE: Hinglish, Beginner-friendly, Practical
```

---

## 📊 Kab Kaunsa Stack — Full Comparison Table

| Feature | Web (Next.js) | Electron | Tauri | React Native | Flutter |
|---|---|---|---|---|---|
| **Runs on** | Browser (any) | Windows PC | Windows PC | Android | Android + Windows |
| **Internet** | Required | Zero | Zero | Optional | Zero |
| **Install** | None | .exe (150MB+) | .exe (5-15MB) | APK | APK + .exe |
| **Database** | Supabase Cloud | SQLite local | SQLite local | SQLite local | SQLite local |
| **App Size** | N/A | 100-200MB | 5-20MB | 30-60MB | 20-50MB |
| **RAM Usage** | N/A | High (300MB+) | Low (30-80MB) | Medium | Low-Medium |
| **Startup Speed** | N/A | Slow (3-5s) | Fast (<1s) | Fast | Fast |
| **Backend Lang** | JS/TS | Node.js | **Rust** | JS/TS | Dart |
| **Beginner** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ |
| **AI Coding** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ |
| **Security** | Medium | Medium | **High** | Medium | Medium |
| **Multi-device** | Yes | No | No | Yes (phones) | Yes (phone+PC) |
| **Multi-branch** | Yes | No | No | Sync needed | Sync needed |
| **PDF/Print** | Easy | Easy | Easy | Medium | Medium |
| **Sell price** | ₹3k-15k/month | ₹5k-25k one-time | ₹10k-35k one-time | ₹10k-40k | ₹15k-50k |

---

## 🧩 Stack Choice — Ek Line Summary

```
Beginner + Fast MVP           → Electron
Professional + Small .exe     → Tauri  ← (Rust backend, 5-15MB installer)
Desktop + Android together    → Flutter
Multiple branches + Remote    → Next.js (Web)
Field workers + Phone         → React Native / Expo
```

---

## 🔗 Combination Projects — Jab Teen Teeno Chahiye

Kabhi kabhi ek business ke liye multiple apps chahiye:

### Example: Medical Store Complete Solution

```
Part 2 (Electron Desktop)
  → Owner/Cashier ke PC pe billing software
  → Fully offline, fast billing, GST invoice, PDF

Part 1 (Next.js Web)
  → Owner apne phone ke browser se reports dekhe
  → Supabase mein daily sync (USB se ya WiFi se)

Part 3A/3B (Android App)
  → Delivery boy ke phone pe order/delivery tracking
  → Offline + sync when online
```

**Strategy:** Pehle Part 2 (Electron) banao aur sell karo. Phir Part 1 (Web dashboard) add karo premium tier mein. Phir Part 3 (Android) field workers ke liye.

---

### Example: Restaurant Complete Solution

```
Part 2 (Electron)  → Counter billing + kitchen
Part 3A (React Native) → Waiter ke phone pe order entry
Part 1 (Next.js)   → Owner reports + multi-outlet dashboard
```

---

### Example: Distributor/Wholesaler System

```
Part 2 (Electron)  → Office mein stock + billing
Part 3A (React Native) → Salesman ke phone pe order booking
Part 1 (Next.js)   → Manager reports + analytics
```

---

### Example: Electron → Tauri Upgrade Path (Same Client, Premium Upsell)

```
Version 1.0 → Part 2 (Electron)
  Quickly build + sell karo → ₹8,000-12,000

Version 2.0 → Part 2B (Tauri)
  Same features, chhota installer, fast startup
  Upsell existing clients → ₹5,000-10,000 upgrade fee
  New clients ke liye higher price → ₹15,000-25,000
```

**Ye strategy kaam kyun karti hai:** Client ko value milti hai (fast app), tumhe dobara revenue milta hai, aur code reuse hota hai kyunki frontend same React rahta hai.

---

## 💡 Best Business Ideas for These Prompts

### Offline Desktop (Electron/Tauri) — Best ROI
- Medical Store Billing Software
- GST Billing Software
- Kirana Store POS
- Hardware Shop Management
- Garment Shop Billing
- Mobile Repair Shop CRM
- Restaurant POS
- School Management System
- Pathology Lab Software
- Jewellery Billing Software
- Warehouse Inventory
- Electronics Shop Billing
- Bike Service Center Software
- Gym Management Software
- Dairy Management System
- Wholesale Distribution Software
- Hotel Reception Software

### Web App (Next.js) — Best for Multi-Branch
- Hospital Chain Management
- Franchise POS
- Multi-branch Inventory
- Distributor Network Management
- Online Booking System

### Android App — Best for Field Workers
- Delivery Tracking App
- Salesman Order Booking
- Collection/Recovery App
- Attendance + Field Report
- Inspection/Audit App
- Retail van sales

---


## 🗂️ Tool-Specific Rules Files

Har AI coding tool ek special rules file padhta hai project start pe. Ye file AI ko batati hai — kaise kaam karna hai, kya touch karna hai, kya nahi.

### Complete File Priority Map

```
your-project/
├── AGENTS.md          ← 🌐 UNIVERSAL — Cursor, Claude Code, Antigravity, Windsurf sab padhte hain
├── GEMINI.md          ← 🔵 ANTIGRAVITY specific — AGENTS.md se zyada priority
├── .cursorrules       ← 🟣 CURSOR specific (legacy — ab AGENTS.md prefer karo)
└── .agent/
    └── rules/         ← 🔵 Antigravity workspace extra rules folder
```

### Kaunsa File Kab Banao

| Tool | Primary File | Notes |
|---|---|---|
| **Google Antigravity** | `GEMINI.md` + `AGENTS.md` | GEMINI.md > AGENTS.md priority mein |
| **Cursor** | `AGENTS.md` | `.cursorrules` bhi kaam karta hai (legacy) |
| **Claude Code** | `AGENTS.md` | Terminal se seedha padhta hai |
| **Windsurf** | `AGENTS.md` | Cascade mode mein use karta hai |
| **ChatGPT / AI Studio** | Manually paste karo | No auto-read, context mein dalo |

> **Rule:** Hamesha `AGENTS.md` banao (sabka common base). Agar Antigravity use karte ho toh `GEMINI.md` **bhi** banao — Antigravity-specific overrides ke liye.

---

## 🪐 Google Antigravity — Agent-First IDE

### Kya Hai Antigravity?

Google Antigravity ek AI-powered IDE hai jo November 2025 mein Gemini 3 ke saath announce kiya gaya. Ye VS Code ka heavily modified fork hai aur autonomous AI agents ke through coding karta hai.

AI Studio browser mein ek prompt se running app deta hai — prototype ke liye. Antigravity wahi kaam autonomous agents se desktop IDE mein karta hai — production build ke liye.

### Antigravity vs Doosre Tools

| Feature | Cursor | Windsurf | Claude Code | **Antigravity** |
|---|---|---|---|---|
| **Type** | IDE (VS Code fork) | IDE (VS Code fork) | Terminal CLI | **IDE (VS Code fork)** |
| **Model** | Claude mainly | Claude/GPT | Claude | **Gemini 3 Pro (default)** |
| **Multi-agent** | No | Cascade (single) | Subagents | **Agent Manager ✅** |
| **Browser control** | No | No | No | **Built-in Chrome ✅** |
| **Rules file** | `.cursorrules` / AGENTS.md | AGENTS.md | AGENTS.md | **GEMINI.md + AGENTS.md** |
| **Free tier** | Limited | Limited | Usage based | **Free (personal Gmail) ✅** |
| **Offline** | Yes | Yes | Yes | **Yes (local IDE)** |
| **Skills system** | No | No | No | **`.agent/skills/` ✅** |

### Antigravity ka Unique Feature — Agent Manager

Antigravity mein do views hain: Editor View (VS Code jaisa) aur Manager View jahan multiple agents simultaneously alag alag tasks pe kaam karte hain. Agents editor, terminal aur browser teeno control karte hain.

Matlab:
- Agent 1 → database schema likh raha hai
- Agent 2 → frontend component bana raha hai  
- Agent 3 → bugs fix kar raha hai
- Tum → review kar rahe ho bas ✅

### GEMINI.md — Kya Hota Hai?

Antigravity rules do jagah se padhta hai: Global rules `~/.gemini/GEMINI.md` se (har project ke liye), aur workspace rules project root ke `GEMINI.md` se. GEMINI.md ko AGENTS.md se zyada priority milti hai — conflicting rules mein GEMINI.md jeet-ti hai.

### Project Structure — Antigravity ke Saath

```
your-project/
├── AGENTS.md                  ← Universal rules (Cursor/Claude Code bhi padhein)
├── GEMINI.md                  ← Antigravity-specific overrides (highest priority)
├── PROJECT_BLUEPRINT.md       ← Architecture reference
├── TASKS.md                   ← Task checklist
│
├── .agent/                    ← Antigravity ka special folder
│   ├── rules/                 ← Extra workspace rules
│   │   └── offline-rules.md   ← Offline-specific rules
│   └── skills/                ← Reusable agent skills
│       ├── generate-schema.md ← SQLite schema generate karna
│       ├── create-ipc.md      ← IPC channel banana
│       └── build-installer.md ← .exe build karna
│
├── src/                       ← Frontend code
├── src-tauri/ ya main/        ← Backend code
└── ...
```

### GEMINI.md Template — Indian Business Software ke liye

Apne project root mein `GEMINI.md` banao aur ye paste karo:

```markdown
# GEMINI.md — Antigravity Rules
# [PROJECT NAME] — Offline Business Software

## Identity
You are an expert offline desktop/mobile app developer
specializing in Indian small business software.
Always plan before coding. Use Artifact mode for task lists.

## Language Rules
- Code: English only
- Comments: Hinglish (Hindi + English mix)
- Variable names: English, camelCase
- Error messages: English
- UI text: Hindi/Hinglish (user-facing)

## Architecture — STRICT
- This is an OFFLINE app — NO internet calls EVER
- SQLite is the ONLY database — no cloud DB
- [Electron]: SQLite ONLY in main process via IPC
- [Tauri]: SQLite ONLY in Rust backend via invoke()
- [Flutter]: SQLite ONLY in repository layer via Drift
- Frontend/UI NEVER directly touches database

## Agent Behavior Rules
- ALWAYS create a Plan artifact before writing any code
- Ask for approval on the plan before starting
- Work on ONE file at a time — complete it, then next
- After each file: list what was changed and why
- If stuck: ask, don't guess

## File Rules
- Read AGENTS.md first before any task
- Never delete existing working code without asking
- Never add cloud/internet dependencies
- Never use UUID in SQLite — use INTEGER AUTOINCREMENT

## Response Format
- Show plan as numbered checklist first
- Code in full — no "..." or "rest of code here"
- After code: "Files changed: [list]"
- Flag any assumptions made

## Skills Available
- /generate-schema → SQLite schema banao
- /create-ipc      → IPC channel banao (Electron)
- /build-installer → .exe build config banao
```

### GEMINI.md vs AGENTS.md — Kya Difference Hai?

```
AGENTS.md    → Sabka shared base
               "Offline app hai, SQLite use karo, IPC mandatory hai"
               Cursor, Claude Code, Windsurf, Antigravity sab padhte hain

GEMINI.md    → Antigravity-specific behavior
               "Plan pehle banao, Agent Manager use karo,
                ek baar mein ek file, approval lo"
               SIRF Antigravity padhta hai, AGENTS.md se override karta hai
```

> ⚠️ **Known Issue:** Agar tum Gemini CLI (terminal) aur Antigravity dono use karte ho — dono `~/.gemini/GEMINI.md` mein likhte hain. Fix: Global rules `~/.gemini/AGENTS.md` mein rakho, `GEMINI.md` mein sirf Antigravity-specific cheezein rakho.

### Antigravity Workflow — Step by Step

```
Step 1: Antigravity download karo → antigravity.google
        (Free for personal Gmail account)

Step 2: Project folder kholo → GEMINI.md + AGENTS.md dono banao

Step 3: Agent Manager kholo (Manager View)

Step 4: Master prompt paste karo → blueprint generate karo
        "Read GEMINI.md and AGENTS.md. 
         Generate PROJECT_BLUEPRINT.md and TASKS.md for:
         [PROJECT NAME & DESCRIPTION]"

Step 5: Plan artifact review karo → Approve karo

Step 6: Pehla task do:
        "Read GEMINI.md. Task 1.1: [task name].
         Build: [exact file]. Requirements: [details].
         Show plan first, wait for my approval."

Step 7: Agent kaam karega → Artifact (task list) dikhayega
        → Browser mein test karega → Code diff dikhayega
        → Tum approve karo → Next task

Step 8: Agent Manager mein multiple agents parallel chalao:
        Agent 1 → "Build products table IPC handlers"
        Agent 2 → "Build customers table IPC handlers"
        (Same time pe → double speed 🚀)
```

### AI Studio + Antigravity Combined Workflow

Google ne AI Studio (prototype/prompt testing) aur Antigravity (agent-based building) ko integrate kiya — ek "Open in Antigravity" button se browser prototype seedha Antigravity workspace mein aa jaata hai bina copy-paste ke.

```
Idea → AI Studio mein quick prototype banao (browser mein)
     → "Open in Antigravity" click karo
     → Antigravity mein agents production-ready code banate hain
     → Tum sirf review karte ho
```

**Indian freelancer ke liye kab useful:**
- Pehle client ko AI Studio mein quick demo dikhao (free, fast)
- Client approve kare toh Antigravity mein proper software banao
- Client ko lagega tum bahut fast ho — actually AI fast hai 😄

---

## 📝 Prompt Use Karne Se Pehle — Customization Tips

Prompt mein sirf **2 cheezein replace karo**, baaki mat chhedo:

```
1. [PROJECT NAME & ONE LINE DESCRIPTION]
   → Ye tumhara app ka naam aur ek line ka description hai
   → Example: "Shree Ram Medical Store — offline billing, 
     stock tracking, GST invoicing, Windows pe chalega"
   → Jitna specific likho utna better output aayega

2. Stack-specific details (optional — agar chahiye)
   → Target city/region add kar sakte ho
   → Business size add kar sakte ho (single shop / chain)
   → Special features mention kar sakte ho (barcode, WhatsApp, etc.)
```

**Mat karo:**
- Prompt ke sections mat hatao (AI confuse ho jayega)
- Tech stack mat badlo (prompt specifically usi ke liye tuned hai)
- Multiple prompts ek saath mat paste karo

**Agar output incomplete aaye:**
- "continue from where you left off" likh ke bhejo
- Ya specific section naam likh ke maango: "Section 8 AI Prompts generate karo"

---

## 🪜 How to Use — Step by Step

```
Step 1: Upar se decide karo — kaunsa software type chahiye
        (Decision Tree use karo agar confused ho)

Step 2: Sahi part ka prompt copy karo (raw markdown copy karo)

Step 3: Sirf YE cheezein replace karo prompt mein:
        → [PROJECT NAME & ONE LINE DESCRIPTION]
          Example: "Vijay Medical Store Billing System —
          offline stock + GST billing for Windows"
        → Baaki prompt bilkul mat chhedo — AI ko guide karta hai

Step 4: Apna AI editor kholo — new FRESH chat kholo
        (Purani chat mein paste mat karo — context mix hoga)

Step 5: Pura prompt paste karo → Enter dabaao → wait karo
        (Bada document hai, 2-5 minute lag sakte hain)

Step 6: AI ek bada markdown document dega (~500-2000 lines)
        Agar cut off ho jaye — "continue" likh ke bhejo

Step 7: Wo document 3 separate files mein save karo:
        → AGENTS.md        (AI ke rules)
        → PROJECT_BLUEPRINT.md  (architecture)
        → TASKS.md         (kya banana hai — checklist)

Step 8: Tasks.md kholo → Phase 1, Task 1.1 padho
        Us task ka AI prompt copy karo (Section 8 mein milega)
        NEW chat kholo → AGENTS.md ka content paste karo pehle
        Phir task prompt paste karo → code generate karo

Step 9: Code copy karo → apne project mein dalo → test karo
        Kaam kara? → Next task
        Error aaya? → Error message copy karo → AI se fix karwao

Step 10: Sab tasks complete → software ready
         Client ko .exe / APK / link dedo → paisa lo 💰
```

### 🛠️ AI Tool-Specific Tips

| Tool | Best Use | Tip |
|---|---|---|
| **Google Antigravity** | Production software banana — agent-first | GEMINI.md + AGENTS.md dono banao; Agent Manager mein parallel agents chalao |
| **Cursor** | Task-by-task code generation | AGENTS.md root mein rakho; `.cursorrules` legacy hai |
| **Windsurf** | Full project build | Cascade mode — multi-file tasks ke liye best |
| **Claude Code** | Terminal se autonomous build | `claude` command; AGENTS.md auto-read karta hai |
| **ChatGPT / AI Studio** | Blueprint + prototype | GPT-4o ya Gemini 3 Pro; manually AGENTS.md paste karo |
| **Gemini CLI** | Terminal tasks | `~/.gemini/AGENTS.md` mein global rules rakho (GEMINI.md se alag) |

---

## 🌱 Recommended Path for Beginners

### Agar Bilkul Naya Ho

```
Month 1: Electron se ek simple billing software banao
          (Medical store ya kirana store)
          → Locally test karo
          → 1-2 clients ko free mein do feedback ke liye

Month 2: Theek karo bugs → ₹3,000-5,000 mein sell karo
          → Same software 5-10 clients ko

Month 3: Ek dusra module add karo (reports, barcode, etc.)
          → Price badhao → ₹8,000-15,000

Month 4-6: Tauri try karo (smaller installer)
            → Premium version launch karo

Month 6+: Android app add karo (Flutter ya React Native)
           → Full solution → ₹25,000-50,000 per client
```

### Stack Learning Order

```
1st → Electron (easiest, huge ecosystem, AI tools best support)
2nd → Next.js (web version, remote access clients ke liye)
3rd → Tauri (smaller installer, Rust backend — professional clients ke liye)
4th → Flutter (desktop + Android, premium product ke liye)
```

---

## ⚠️ Important Rules (Har Stack ke liye)

```
✅ HAMESHA
- AGENTS.md pehle generate karo
- Ek task = ek AI chat
- SQLite sirf backend/main process mein
- PDF + Excel export hamesha dalo (clients demand karte hain)
- Backup feature mandatory (client ka data precious hai)

❌ KABHI NAHI (Offline apps ke liye)
- Supabase mat use karo
- Firebase mat use karo
- Cloud database mat use karo
- UUID mat use karo SQLite mein
- nodeIntegration: true mat karo (Electron)
```

---

## 📈 Freelancer Pricing Guide (India)

| Software Type | Basic | Standard | Premium |
|---|---|---|---|
| Single offline app | ₹5,000 | ₹12,000 | ₹25,000 |
| With Android app | ₹15,000 | ₹30,000 | ₹60,000 |
| Web + Desktop + Mobile | ₹30,000 | ₹60,000 | ₹1,20,000 |
| AMC (Annual Maintenance) | ₹2,000/yr | ₹5,000/yr | ₹12,000/yr |
| Customization per client | ₹2,000+ | ₹5,000+ | ₹15,000+ |

> **Pro tip:** Same software multiple clients ko sell karo — yahi real business model hai. Ek baar banao, baar baar becho.

---

## 📦 Client ko Software Dene ka Process

Software ban gaya — ab kya?

### Offline Desktop (.exe)

```
Step 1: electron-builder / tauri bundle se .exe banao
Step 2: VirusTotal pe upload karo check ke liye (client trust ke liye)
Step 3: Google Drive / Pen Drive mein dedo
Step 4: Client ke PC pe install karke dikhao (pehli baar tum karo)
Step 5: 15-30 min training do (ek simple video bana lo screen record se)
Step 6: WhatsApp group banao — client + tum — support ke liye
Step 7: AMC (Annual Maintenance) contract sign karo
```

### Android APK

```
Step 1: flutter build apk --release / eas build se APK banao
Step 2: WhatsApp pe directly bhej do
Step 3: "Unknown sources se install karne do" client ko dikhao
Step 4: Screen record tutorial bhejo
Step 5: Update process: naya APK WhatsApp pe bhej do
```

### Web App

```
Step 1: Vercel pe deploy karo
Step 2: Custom domain connect karo (namecheap.com se ~₹800/year)
Step 3: Login credentials dedo
Step 4: Browser bookmark karwa do
Step 5: Monthly subscription le lo (hosting + support)
```

### 💰 Payment Structure (Recommended)

```
Initial payment: 50% advance lelo (project start pe)
Delivery payment: 50% on delivery (client ke PC pe install karke)
AMC: Year ke baad annual maintenance charge karo
Customization: Per feature charge karo (scope creep rokta hai)
```

---

## 🤝 Contributing

Agar koi aur prompts ya business ideas add karne hain — PR bhejo ya issue kholo.

---

## 📄 License

MIT — Free to use, modify, and sell software built using these prompts.

---

---

## 📋 Changelog

| Version | Changes |
|---|---|
| v3.0 | Google Antigravity section added, GEMINI.md template, tool-specific rules file guide, Agent Manager workflow, AI Studio integration |
| v2.0 | Tauri (Part 2B) added, AI tool tips, client delivery guide, prompt customization tips, decision tree improved |
| v1.0 | Initial release — Web, Electron, React Native, Flutter prompts |

---

*Last updated: May 2025 | Made for Indian freelancers & solo founders building with AI*

*Star ⭐ karo agar helpful laga — aur apne developer dosto ke saath share karo!*
