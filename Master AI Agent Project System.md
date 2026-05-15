# 🚀 Master AI Agent Project System

> **The Ultimate Playbook for AI Agents (Claude, Gemini, Cursor, Copilot) & Human Developers.** > Never repeat yourself. Never lose context. Always ship production-ready code.

---

## 📑 Table of Contents
1. [📁 PART 1: Project Overview (README.md)](#-part-1-project-overview-readmemd)
2. [🤖 PART 2: AI Rulebook (AGENTS.md)](#-part-2-ai-rulebook-agentsmd)
3. [🏗️ PART 3: Master Architecture (PROJECT_BLUEPRINT.md)](#️-part-3-master-architecture-project_blueprintmd)
4. [📋 PART 4: Development Checklist (TASKS.md)](#-part-4-development-checklist-tasksmd)
5. [🤝 PART 5: Contributing Guide (CONTRIBUTING.md)](#-part-5-contributing-guide-contributingmd)
6. [⚡ PART 6: AI Quick Reference (GEMINI.md)](#-part-6-ai-quick-reference-geminimd)

---

## 📁 PART 1: Project Overview (README.md)

### 📚 What's Inside

This system contains essential files that work together to guide AI agents through your project development:

| File | Purpose | Size | Update Frequency |
|------|---------|------|------------------|
| **AGENTS.md** | 🤖 AI rulebook (code style, do's & don'ts) | ~3KB | When rules change |
| **PROJECT_BLUEPRINT.md** | 🏗️ Architecture, tech stack, schema, APIs | ~8KB | When design changes |
| **TASKS.md** | 📋 Development checklist, progress tracker | ~5KB | After every task |
| **GEMINI.md** | ⚡ Quick reference (simplified AGENTS.md) | ~2KB | Rarely |

**Total: ~18KB of pure project guidance.**

### 🎯 How It Works

#### Scenario 1: Starting a New Feature
1. **Open your AI chat** (Claude, Gemini, Cursor, etc.)
2. **Paste this prompt:**
   ```text
   Read AGENTS.md, PROJECT_BLUEPRINT.md, and TASKS.md.
   
   Tell me:
   1. What is the current project status?
   2. What is the next pending task?
   3. Do you understand all rules?
   ```
3. **AI reads all files and responds** with status & next task
4. **Tell AI:** "Start working on [task name]"
5. **AI implements the feature** with full context
6. **AI updates TASKS.md:** changes `[ ]` to `[x]`

#### Scenario 2: Continuing After a Break
1. **Open AI chat** (fresh session, AI has no memory)
2. **Paste:** "Read AGENTS.md, PROJECT_BLUEPRINT.md, TASKS.md. Acknowledge."
3. **AI remembers everything** because it reads the files
4. **Continue where you left off**

#### Scenario 3: Multiple Developers
1. **Developer A** works on authentication (Phase 2)
2. **Developer B** works on products module (Phase 3)
3. **Both read the same files**, understand the architecture
4. **No conflicts**, everyone follows the same rules
5. **TASKS.md prevents duplicate work** (only one person per task)

### 🎨 Best Practices

#### ✅ Do This
- ✅ **Update TASKS.md after every task** (mark `[x]`)
- ✅ **Read all files before starting** (not just when blocked)
- ✅ **Keep rules consistent** (same coding style, commit format)
- ✅ **Document decisions** (why PostgreSQL? why Next.js?)
- ✅ **Update AGENTS.md when rules change** (new linting rules, etc.)
- ✅ **Use blockers in TASKS.md** (when waiting for something)

#### ❌ Don't Do This
- ❌ **Skip reading the files** ("I'll just ask AI" = context loss)
- ❌ **Update AGENTS.md mid-task** (finish task first, then update)
- ❌ **Leave TASKS.md stale** (AI won't know progress)
- ❌ **Copy rules from another project** (customize to YOUR project)
- ❌ **Hardcode anything** (secrets, URLs, IDs)

---

## 🤖 PART 2: AI Rulebook (AGENTS.md)

> **Universal rulebook for AI agents.** Every AI session starts by adhering to these rules.

### 🎯 Project Configuration

#### Project Type
- [ ] Web App (React/Next.js/Vue)
- [ ] Desktop App (Electron/Tauri)
- [ ] Backend API (Node/Python/Go)
- [ ] Full-Stack SaaS
- [ ] Mobile App (React Native/Flutter)

#### Tech Stack (Fixed – Do Not Change Without Approval)

| Component | Choice | Version |
|-----------|--------|---------|
| **Frontend** | React / Next.js / Vue / Angular | 18+ / latest |
| **Backend** | Node.js / Python / Go / None | 18+ / 3.10+ / 1.21+ |
| **Database** | PostgreSQL / MySQL / MongoDB | 14+ / 8+ / 5.0+ |
| **ORM/Query** | Prisma / Knex / SQLAlchemy / Raw | latest |
| **Auth** | JWT / NextAuth / Firebase Auth | - |
| **Styling** | Tailwind CSS / Bootstrap / CSS Modules | 3.x / 5.x |
| **Build Tool** | Vite / Webpack / Next.js / Create React App | latest |
| **Deployment** | Vercel / Netlify / Railway / Docker | - |

### ✅ Core Development Rules (ALWAYS FOLLOW THESE)

#### 1. Code Quality & Structure
- ✨ Write clean, readable, production-ready code
- 🔒 **NEVER hardcode secrets** → Use `.env` for ALL API keys, DB URLs, JWT secrets
- 📦 Keep components small and reusable (single responsibility)
- 🎨 One component = one file (unless it's a tiny sub-component)
- 🧠 Use meaningful names (no `tmp`, `data1`, `x`)
- 📝 Comment complex logic, not obvious code

#### 2. Responsive Design & UX
- 📱 **Mobile-first approach** – Design for small screens first, then scale up
- ♿ Ensure keyboard navigation works (for accessibility)
- ⚡ Keep animations smooth (60fps)

#### 3. Error Handling
- 🛡️ Every async operation must have try/catch or .catch()
- 📢 Show user-friendly error messages (not technical stack traces)
- 🔄 Implement retry logic for failed API calls
- 🚨 Log errors properly (not with console.log in production)

#### 4. Git & Version Control
- 🌿 **Branch naming:** `feature/feature-name` or `fix/bug-name` (from `develop`)
- 💬 **Commit format:** `type: short description`
  - `feat:` new feature
  - `fix:` bug fix
  - `refactor:` code restructure (no behavior change)
  - `docs:` documentation
  - `style:` formatting/prettier
  - `test:` test additions
  - `chore:` deps, config, tooling

#### 5. Code Style (Consistent Formatting)
```javascript
// ✅ DO THIS
const userName = "John Doe";        // camelCase for variables
function getUserName() { }          // camelCase for functions
const UserProfile = () => { }       // PascalCase for components
const API_BASE_URL = "...";         // CONSTANT_CASE for constants

// FORMATTING
// - Indentation: 2 spaces
// - Quotes: double quotes "string"
// - Semicolons: yes
// - Max line length: 100 chars
```

#### 6. Do Nots (STRICT – Violations = Restart Task)
- ❌ Do not delete existing code/comments without asking
- ❌ Do not change unrelated files in one commit
- ❌ Do not introduce new npm/pip dependencies without asking first
- ❌ Do not bypass TypeScript type checking
- ❌ Do not hardcode IDs, API URLs, or secrets
- ❌ Do not leave console.log() in production code
- ❌ Do not commit with `git push -f` (force push)
- ❌ Do not ignore or suppress linter warnings

### 🔐 Environment Variables Template

**Create `.env.local` (never commit to Git):**
```env
DATABASE_URL=postgresql://user:password@localhost:5432/dbname
JWT_SECRET=your_super_secret_key_min_32_chars_long
NEXT_PUBLIC_API_URL=http://localhost:3000
STRIPE_API_KEY=sk_test_xxxxx
NODE_ENV=development
```

**Create `.env.example` (commit to Git, no secrets):**
```env
DATABASE_URL=postgresql://user:password@localhost:5432/dbname
JWT_SECRET=change_me_in_production
NEXT_PUBLIC_API_URL=http://localhost:3000
STRIPE_API_KEY=sk_test_xxxxx
NODE_ENV=development
```

---

## 🏗️ PART 3: Master Architecture (PROJECT_BLUEPRINT.md)

### 1️⃣ High-Level Goal
**One-liner:** [INSERT YOUR PROJECT GOAL HERE]

### 2️⃣ Tech Stack (Detailed)
*(Refer to AGENTS.md Tech Stack section for primary choices. Add specific libraries like React Hook Form, Recharts, Zod, Swagger here if needed).*

### 3️⃣ Module Map – Build Order
**Build modules in this EXACT order. Do not skip or reorder without approval.**

```text
Phase 1: Foundation & Infrastructure
Phase 2: Database & Authentication
Phase 3: Core Business Module 1 – [Specify Your Module]
Phase 4: Core Business Module 2 – [Specify Your Module]
Phase 5: Integration & Advanced Features
Phase 6: Dashboard & Analytics
Phase 7: Settings & User Experience
Phase 8: Optimization & Deployment
```

### 4️⃣ Database Schema
```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  email VARCHAR(255) UNIQUE NOT NULL,
  password_hash VARCHAR(255) NOT NULL,
  first_name VARCHAR(100),
  last_name VARCHAR(100),
  role VARCHAR(50) DEFAULT 'user',
  is_active BOOLEAN DEFAULT true,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
CREATE INDEX idx_users_email ON users(email);
```

### 5️⃣ API Endpoints (REST)
| Method | Endpoint | Authentication | Description | Response |
|--------|----------|-----------------|-------------|----------|
| POST | `/api/auth/register` | None | Register new user | `{ token, user }` |
| POST | `/api/auth/login` | None | Login user | `{ token, user }` |
| GET | `/api/[resource]` | Bearer | List all | `{ data[], total, page }` |

---

## 📋 PART 4: Development Checklist (TASKS.md)

> **Living document. Update `[ ]` to `[x]` after each completion.**

### 🎯 Current Project Status
- **Project Name:** [Your Project Name]
- **Overall Progress:** [XX%]
- **Next Milestone:** [Phase Name]

### 📊 Progress Dashboard
| Phase | Tasks | Done | In Progress | Pending | Status |
|-------|-------|------|-------------|---------|--------|
| 1 – Foundation | 5 | 0 | 0 | 5 | 🔴 Not Started |
| 2 – Database & Auth | 6 | 0 | 0 | 6 | 🔴 Not Started |
| 3 – Core Module | 5 | 0 | 0 | 5 | 🔴 Not Started |

### Phase 1: 🏗️ Foundation & Infrastructure
- [ ] **1.1 Repository Setup** (GitHub, branches, .gitignore)
- [ ] **1.2 Project Scaffolding** (Folder structure, frontend/backend init)
- [ ] **1.3 Install Dependencies** (React, Express, Prisma, etc.)
- [ ] **1.4 CI/CD Pipeline Setup** (GitHub actions for lint/build)
- [ ] **1.5 Environment & Configuration** (.env setup)

### Phase 2: 🔐 Database & Authentication
- [ ] **2.1 Database Schema & Migrations**
- [ ] **2.2 User Registration API**
- [ ] **2.3 User Login API**
- [ ] **2.4 Protected Route Middleware**
- [ ] **2.5 Login/Register Frontend Pages**

### 🎓 Testing Checklist (Before Marking Task `[x]`)
- [ ] Code compiles/runs without errors
- [ ] Linter passes (ESLint, Prettier)
- [ ] No hardcoded secrets
- [ ] Error handling implemented
- [ ] Mobile responsive (if UI task)
- [ ] All acceptance criteria met
- [ ] Git commit with clear message

---

## 🤝 PART 5: Contributing Guide (CONTRIBUTING.md)

### 🔄 Development Workflow
1. **Find Your Task:** Open `TASKS.md` and find the first `[ ]` (pending) task.
2. **Create a Feature Branch:** `git checkout -b feature/[short-task-description]`
3. **Make Changes:** Follow `AGENTS.md` rules.
4. **Test Your Work:** Run local linters and tests.
5. **Update TASKS.md:** Mark your task `[x]`.
6. **Commit Your Changes:** Use conventional commits (`feat:`, `fix:`, `chore:`).
7. **Push & Create Pull Request.**

### 🚫 Absolute No-Nos
❌ **Never hardcode secrets**
❌ **Never force push** (`git push -f`)
❌ **Never commit .env**
❌ **Never leave console.log() in code**
❌ **Never change unrelated files**

---

## ⚡ PART 6: AI Quick Reference (GEMINI.md)

> **Lightweight rules file for quick context loading.**

### ⚡ Quick Start Prompt for AI Chat
```text
Read AGENTS.md, PROJECT_BLUEPRINT.md, and TASKS.md from this repository.
Acknowledge:
1. Tech stack understood? ✓
2. Next pending task identified? ✓
3. All rules from AGENTS.md accepted? ✓
Start working on the first pending [ ] task.
```

### 🚀 Quick Commands
```bash
npm install         # Install dependencies
npm run dev         # Start dev server
npm run lint        # Lint & format
npm run build       # Build for production
npm test            # Run tests
git commit -m "feat: description" # Commit work
```

### 📝 Template for AI Acknowledgment
```text
✅ Context Loaded Successfully
📋 Files Read: AGENTS.md, PROJECT_BLUEPRINT.md, TASKS.md
🛠️ Tech Stack Confirmed: [Frontend], [Backend], [DB]
📊 Current Status: Phase [X], Task [Y]
✅ Ready to work. Should I proceed?
```