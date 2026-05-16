# 🧠 Master Prompt — AI se Kisi Bhi Project ka Development Document Banwao

> **Yeh prompt use karo → AI tumhare project ka poora A-to-Z development document bana dega**

---

## How to Use

1. Neeche diya hua prompt copy karo
2. `[PROJECT NAME & ONE LINE DESCRIPTION]` replace karo apne project ke saath
3. Claude / ChatGPT / Gemini mein paste karo
4. Jo document mile usse `README.md` ke naam se save karo

---

## The Master Prompt

```
You are an expert Next.js developer and technical architect.

I want to build: [PROJECT NAME & ONE LINE DESCRIPTION]
Example: "Medical Store Billing System — stock tracking, GST invoicing, daily reports"

My tech stack (STRICT — don't change):
- Framework: Next.js 14 App Router + TypeScript
- Styling: Tailwind CSS + Shadcn UI
- Database + Auth: Supabase (PostgreSQL)
- Deployment: Vercel

My level: Non-technical / Beginner — I use AI editors (Cursor/Windsurf) to build.

---

Create a COMPLETE PROJECT DEVELOPMENT DOCUMENT in Markdown format
with these exact sections:

## 1. PROJECT OVERVIEW
- What this app does (2-3 lines)
- Who uses it (roles: Admin, Staff, etc.)
- Core user flows (numbered, plain text — no diagrams)

## 2. REQUIREMENTS DOCUMENT
- Must-have features (numbered list)
- Nice-to-have features (later phase)
- Out of scope (what we are NOT building)
- Number of users per role

## 3. DATABASE SCHEMA
- List all tables needed
- For each table: all columns with type, constraints, and a comment explaining why
- Every table MUST have: id (uuid), user_id (uuid → auth.users), created_at (timestamp)
- Write complete CREATE TABLE SQL for every table
- Write all RLS policies SQL (SELECT, INSERT, UPDATE, DELETE for every table)
- If multi-user/role: write org-based or role-based policy SQL

## 4. FOLDER STRUCTURE
- Complete folder/file tree for this specific project
- All app routes listed
- All components listed by feature

## 5. AGENTS.md CONTENT
- Complete ready-to-use AGENTS.md file for this project
- Include tech stack rules, file naming rules, coding rules, response format

## 6. PROJECT_BLUEPRINT.md CONTENT
- Complete ready-to-use blueprint
- Include: overview, roles, schema summary, all routes with access levels,
  module build order

## 7. TASKS.md CONTENT
- Complete checklist, phase by phase
- Every single task numbered (e.g. 1.1, 1.2, 2.1...)
- Ordered from foundation to polish
- Every task should be small enough for ONE AI prompt

## 8. AI PROMPTS — ONE PER TASK
- For every major task in TASKS.md, write the exact AI prompt I should use
- Format: Task number → Prompt (copy-paste ready)
- Each prompt must follow this structure:
  "Read AGENTS.md. Task: [X.X] [name]. Build: [exact file].
   Requirements: [specific]. Do NOT touch: [other files].
   After done: list files changed."

## 9. ENVIRONMENT VARIABLES
- Every .env.local variable this project needs
- Mark which are NEXT_PUBLIC and which are server-only
- Explain what each one is for

## 10. COMMON ERRORS FOR THIS PROJECT
- List 5-8 errors specific to this project's features
- For each: error message, why it happens, exact fix

## 11. TESTING CHECKLIST
- Module-by-module testing checklist specific to THIS project
- Browser tests, API tests, mobile tests

## 12. DEPLOYMENT CHECKLIST
- Pre-deploy, deploy, post-deploy steps
- Supabase redirect URL setup
- Custom domain steps

---

RULES FOR YOUR RESPONSE:
- Write everything in Hinglish (Hindi + English mix) — simple language
- All code blocks must be complete and copy-paste ready
- SQL must be production-ready with RLS
- AI prompts must be specific — no vague instructions
- Do NOT write generic advice — everything specific to [PROJECT NAME]
- Output must be one single Markdown document I can save as README.md
```

---

## Example — Prompt Fill Karke Kaisa Dikhega

```
I want to build: Gym Management System — member registration,
fee tracking, attendance, and monthly reports
```

Bas yahi ek line badlo — baaki sab AI khud likhega:
- Gym ke specific tables (members, fees, attendance)
- Gym ke specific AI prompts
- Gym ke specific error list
- Gym ke specific testing checklist

---

## Kisi Bhi Project ke Saath Use Karo

| Project Type | Ek Line Description Example |
|---|---|
| Medical Store | stock tracking, GST billing, purchase records |
| Coaching Center | students, fees, attendance, batches |
| Restaurant | menu, orders, KOT, daily sales |
| Real Estate | properties, leads, site visits, commission |
| Car Workshop | job cards, parts, service history, billing |
| Gym | members, fees, attendance, trainer assign |
| Hotel | rooms, bookings, check-in/out, billing |
| Kirana Store | inventory, billing, supplier, GST reports |

---

*Save this file → use karo jab bhi naya project shuru karo*
