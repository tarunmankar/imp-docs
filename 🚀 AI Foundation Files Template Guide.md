# 🚀 AI Foundation Files: Master Template Guide

> [!NOTE]
> 📖 **Purpose:** Yeh guide batati hai ki jab aap AI se `00_PRD.md` padh kar baaki foundation files banane ko kahenge, toh un sabhi files ke andar **exactly kya-kya details aur sections** hone chahiye. AI inhi formats ko follow karega.

---

## 📑 Table of Contents
- [0. `00_PRD.md`](#0-00_prdmd-product-requirements-document---the-master-seed)
- [1. `ARCHITECTURE_MASTER.md`](#1-architecture_mastermd-single-source-of-truth)
- [2. `SCHEMA.md`](#2-schemamd-database-blueprint)
- [3. `AGENTS.md`](#3-agentsmd-the-general-laws)
- [4. `GEMINI.md`](#4-geminimd-environmentantigravity-overrides)
- [5. `PROJECT_BLUEPRINT.md`](#5-project_blueprintmd-the-mapfolder-structure)
- [6. `TASKS.md`](#6-tasksmd-the-execution-checklist)
- [7. `ERROR_LOGS.md`](#7-error_logsmd-the-ais-memory-bank)

---

## 0. `00_PRD.md` (Product Requirements Document - The Master Seed)
> [!IMPORTANT]
> 🧠 Yeh sabse pehli file hai jo aap (Human) likhenge. Baaki saari files AI is file ko base maan kar khud generate karega. Yeh aapke idea ka **brain** hai.

### ✅ Mandatory Sections:
| Section | Description & Example |
|:---|:---|
| 🏷️ **App ka Naam & Vision** | Project ka naam aur ek line mein description <br>*(e.g., Shree Ram Medical Billing - Fast offline desktop app for Tier-2 pharmacies)* |
| 👥 **Target Audience & Environment** | Kaun use karega aur kahan? <br>*(e.g., Non-tech users, strictly Windows PC offline environment, no internet required)* |
| ⚙️ **Strict Tech Stack** | Technologies strictly define karein <br>*(e.g., Electron JS, React+Vite, SQLite, Tailwind v4, Zustand)* |
| 📦 **Core Features (Must-Haves)** | Point-wise list: Inventory Management, POS (Barcode/GST), PDF Generation (`jsPDF`), Low Stock Alerts |
| 🚫 **Business Logic & Constraints** | Rules jo AI tod nahi sakta <br>*(e.g., Invoice delete nahi, sirf cancel. Stock never negative. No Firebase/Cloud.)* |
| 🤖 **Agentic Preferences** | Coding style notes <br>*(e.g., Code comments Hinglish mein, Antigravity IDE + Windows OS environment)* |

</br>

## 🔮 The Magic Prompt (Is file ke end mein paste karein)
```text
AI Instruction: Read this 00_PRD.md very carefully and generate ARCHITECTURE_MASTER.md, SCHEMA.md, AGENTS.md, GEMINI.md, PROJECT_BLUEPRINT.md, and TASKS.md based on these exact requirements.
```

---

</br>

## 1. `ARCHITECTURE_MASTER.md` (Single Source of Truth)
⚙️ Is file ka kaam hai project ka **engine aur wiring** define karna. AI code likhte waqt isko base manega.

### ✅ Kya-kya hona chahiye:
- 📚 **Tech Stack Summary:** Frontend, Backend, DB, aur Styling libraries ke exact versions.
- 🔄 **Data Flow Diagram (Text):** `React Component → IPC Renderer → IPC Main → SQLite`
- 🧠 **State Management Strategy:** `useState` (local) vs `Zustand/Redux` (global) kab use karna hai.
- 🔒 **Security & Auth Rules:** Offline PIN login? Data encryption? Session timeout?
- 📝 **File Naming Conventions:** 
  - `Components` → `PascalCase.jsx`
  - `Utils/Hooks` → `camelCase.js`
  - `CSS/Tailwind` → `kebab-case.css`

---

## 2. `SCHEMA.md` (Database Blueprint)
🗃️ Isme sirf aur sirf **Database ka naksha (design)** hoga. No extra fluff.

### ✅ Kya-kya hona chahiye:
- 📋 **Table List:** `users`, `products`, `invoices`, `invoice_items`
- 🏗️ **Table Structure (SQL Format):**
  ```sql
  CREATE TABLE products (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    barcode TEXT UNIQUE,
    price REAL DEFAULT 0,
    stock_qty INTEGER DEFAULT 0
  );
  ```
- ⚠️ **Strict Rule:** `NO UUIDs`. Standard `INTEGER AUTOINCREMENT` use karna hai (SQLite compatible).
- 🔗 **Relationships:** Foreign keys clearly defined <br>`(e.g., invoice_items.invoice_id REFERENCES invoices(id))`
- 🚀 **Indexes:** Performance optimization <br>`CREATE INDEX idx_products_barcode ON products(barcode);`

---

## 3. `AGENTS.md` (The General Laws)
📜 Yeh project ka **samvidhan (Constitution)** hai. Chahe koi bhi AI ho, yeh rules tod nahi sakta.

### 🛡️ Mandatory Rules:
> [!IMPORTANT]
> **🛑 The "Halt & Ask" Rule (Top Priority)**  
> `"Never proceed to the next task automatically. Always stop, report test status, and ask for permission."`

- ⚛️ **Component Rules:** `"Always use functional components. No class components. Keep functions pure."`
- 🎨 **UI/Styling Strictness:** `"Only use Tailwind v4 utility classes. Zero inline CSS (style={{}})."`
- 🗣️ **Language/Comments:** `"Code in English, explain complex logic using Hinglish comments."`
- 🧩 **Modularity Rule:** `"Never write spaghetti code. One component = One file. Max 150 lines per file."`

---

## 4. `GEMINI.md` (Environment/Antigravity Overrides)
💻 Yeh file **Antigravity (Gemini IDE)** ke tools aur local environment ke liye hai.

### ✅ Kya-kya hona chahiye:
- 📦 **Artifacts Usage:** `"Always create an Implementation Plan Artifact before writing/modifying code."`
- 🖥️ **Terminal Rules:** `"Use standard Windows PowerShell commands for running servers/builds."`
- 🔌 **Server Ports:** `"Ensure Vite runs on port 5173. If busy, auto-switch to 5174."`
- 🤖 **Agent Manager:** `"Spawn sub-agents for parallel DB/UI tasks. Main agent handles integration."`

---

## 5. `PROJECT_BLUEPRINT.md` (The Map/Folder Structure)
🗺️ Isme project ke **folders aur screens** ki list hogi taaki AI galat jagah file na banaye.

### 📂 Folder Tree Structure:
```text
/src
├── /features          # Isolated modules (billing, inventory, auth)
│   ├── /billing
│   └── /inventory
├── /shared            # Common reusable code
│   ├── /components    # Buttons, Inputs, Modals
│   ├── /utils         # Formatters, Validators, Loggers
│   └── /hooks         # Custom React hooks
├── /main              # Electron backend (IPC, DB, App logic)
└── App.jsx            # Root routing & layout
```

- 🗺️ **Routing Map:** `/ → Dashboard.jsx`, `/billing → BillingMain.jsx`, `/inventory → InventoryPage.jsx`
- 🧱 **Core Components List:** `Sidebar`, `TopNav`, `LayoutWrapper`, `DataTable`, `ModalDialog`

---

## 6. `TASKS.md` (The Execution Checklist)
📋 Yeh AI aur aapka **daily to-do list** hai. Ise phases mein divide karna hai.

### 📅 Phase Breakdown:
| Phase | Focus Area | Example Tasks |
|:---|:---|:---|
| `Phase 1` | 🏗️ Foundation Setup | Init React, Tailwind config, Electron boilerplate, IPC setup |
| `Phase 2` | 🗄️ Database Init | SQLite connection, Run `SCHEMA.md`, Seed test data |
| `Phase 3` | 🧩 Module Dev | Inventory UI, Billing UI, GST logic, PDF export |
| `Phase 4` | 🧪 Testing & Polish | Edge case handling, Offline sync test, Performance tuning |

### 📌 Every Task MUST Follow This Structure:
- `Task ID`: `2.1`
- `Goal`: `Create SQLite connection & run schema`
- `Target File`: `src/main/db.js`
- `Test Condition`: `Run app → Check terminal for 'DB Connected' → Verify `database.sqlite` file created in root.`

---

## 7. `ERROR_LOGS.md` (The AI's Memory Bank)
🐛 Yeh shuru mein **khali (empty)** rahegi, lekin iska structure pre-defined hona chahiye. AI har bug fix ke baad ise update karega.

### 📝 Format for Logging:
```markdown
### 🐛 Bug: [YYYY-MM-DD HH:MM]
* **Module:** Billing PDF Generator
* **Error Message:** `Uncaught TypeError: Cannot read properties of undefined (reading 'map')`
* **Root Cause:** API response delay se `items` array undefined aa raha tha jab render hota tha.
* **The Fix:** Added optional chaining `items?.map(...)` aur `useEffect` mein loading state add kiya.
* **Status:** ✅ Resolved
```

> [!TIP]
> 💡 **Pro Tip:** AI ko har phase complete hone ke baad `ERROR_LOGS.md` update karne ka prompt dein. Isse AI past mistakes repeat nahi karega aur project stable rahega.

---
*📄 Generated for GitHub • Optimized for AI Agent Workflows • 🤖 Follow Strictly*
```

### 🛠️ Kaise Use Karein:
1. GitHub par apne project repository mein jayein.
2. **Add file > Create new file** par click karein.
3. File ka naam `AI_FOUNDATION_GUIDE.md` rakhein.
4. Upar diya gaya **pura content paste** kar dein aur **Commit** kar dein.
5. GitHub automatically ise ek clean, structured aur professional documentation ki tarah render kar dega. ✅
