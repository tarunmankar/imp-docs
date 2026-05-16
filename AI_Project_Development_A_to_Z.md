# 🛠️ AI se Project Development — A to Z Complete Guide
> **Ek bhi line code likhe bina — professional software kaise banate hain**

![Version](https://img.shields.io/badge/version-1.0-blue.svg)
![Stack](https://img.shields.io/badge/stack-Next.js%20%7C%20Supabase%20%7C%20Vercel-black)
![AI Tools](https://img.shields.io/badge/AI-Cursor%20%7C%20Windsurf%20%7C%20Claude-purple)
![Level](https://img.shields.io/badge/level-Beginner%20Friendly-green)

---

## 📋 Table of Contents

1. [Mindset — Manager vs Developer](#-step-0-mindset-tum-manager-ho-ai-developer-hai)
2. [Idea to Requirements](#-step-1-idea-ko-requirements-mein-convert-karo)
3. [Database Design First](#-step-2-database-design-pehle-code-baad-mein)
4. [AI Brain Setup](#-step-3-ai-brain-setup-agents-blueprint-tasks)
5. [GitHub Setup](#-step-4-safe-github-setup)
6. [Project Initialization](#-step-5-project-initialize-karo)
7. [Supabase Setup](#-step-6-supabase-setup-database--auth)
8. [Module-by-Module Build](#-step-7-module-by-module-build-karo)
9. [Authentication](#-step-8-authentication-login--roles)
10. [Core Features Build](#-step-9-core-features-build-karo)
11. [UI Polish](#-step-10-ui-polish-aur-responsive-design)
12. [Testing Karna](#-step-11-testing-karo-properly)
13. [Security Lockdown](#-step-12-security-lockdown)
14. [Deployment](#-step-13-vercel-deployment)
15. [Post-Launch Fixes](#-step-14-post-launch-bug-fix-protocol)
16. [Quick Reference](#-quick-reference-cheatsheet)

---

## 🧠 Step 0: Mindset — Tum Manager Ho, AI Developer Hai

Yeh guide padhne se pehle yeh baat pakki karo:

```
❌ GALAT SOCH:
"AI sab kuch khud kar lega"
"Mujhe kuch nahi karna"
"Ek prompt mein poora app ban jayega"

✅ SAHI SOCH:
"Main plan karunga, AI execute karega"
"Main test karunga, AI fix karega"
"Main ek kaam ek baar dunga"
```

### The 5 Golden Rules (Kabhi Mat Todna)

| # | Rule | Consequence Agar Toda |
|---|------|-----------------------|
| 1 | **Database First, Logic Second, UI Last** | App toot jayega baad mein |
| 2 | **Chunking** — AI ko ek kaam ek baar do | AI confuse hoga, code kharab hoga |
| 3 | **No API Keys in Code** — sirf `.env.local` | Security breach, account ban |
| 4 | **Refresh Chat** — 30-40 messages ke baad nayi chat | AI context kho deta hai, ulta code likhta hai |
| 5 | **Test Before Saving** — browser check kar ke hi commit | Broken code Git mein permanently save ho jaata hai |

---

## 📝 Step 1: Idea ko Requirements Mein Convert Karo

Seedha code mat karo. Pehle soch likho.

### 1.1 Requirements Document Banao

Ek simple notepad file mein yeh sab likho:

```markdown
# Project: [App ka Naam]
# Date: [Aaj ki Date]

## Business Problem
[Kya problem solve kar rahe ho? 2-3 lines mein]

## Target User
[Kaun use karega? Admin, Staff, Customer?]

## Core Features (Must Have)
1. [Feature 1]
2. [Feature 2]
3. [Feature 3]

## Nice to Have (Later)
1. [Feature A]
2. [Feature B]

## NOT Building (Scope Out)
1. [Cheez jo nahi banani]

## Number of Users
- Admins: [X]
- Staff: [X]
- Customers: [X] (if applicable)

## Reports Needed
- Daily: [what]
- Weekly: [what]
- Monthly: [what]

## Integrations Needed
- [ ] WhatsApp
- [ ] Email
- [ ] Payment (Razorpay/Instamojo)
- [ ] SMS
```

### 1.2 User Flows Likho (Diagrams Nahi, Simple Text)

```
FLOW 1: Admin Login karta hai
→ Login page pe jaata hai
→ Email + Password daalta hai
→ Dashboard pe aa jaata hai
→ Left sidebar mein menu dikhta hai

FLOW 2: Staff Product Add karta hai
→ Products section kholte hain
→ "Add Product" button dabate hain
→ Form fill karte hain (naam, price, stock)
→ Save karte hain
→ Product list mein dikhta hai

FLOW 3: Sale karte hain
→ Sales section kholte hain
→ Customer ka naam daalte hain
→ Products add karte hain cart mein
→ Total calculate hota hai
→ Invoice generate hoti hai
→ Stock automatically ghatta hai
```

> 💡 **Tip:** Yeh flows likhe bina project shuru karna = aankhein band karke gaadi chalana.

---

## 🗃️ Step 2: Database Design — Pehle Code, Baad Mein

> **Sabse important step. 80% projects ki failures ka reason: database baad mein socha.**

### 2.1 Tables Identify Karo

Apne features dekho aur nouns nikalo:

```
Features mein se nouns:
✔ "Product add karna"        → TABLE: products
✔ "Customer ka record"       → TABLE: customers
✔ "Sale record karna"        → TABLE: sales
✔ "Sale ke items"            → TABLE: sale_items
✔ "Staff login"              → TABLE: profiles (Supabase auth ke saath)
```

### 2.2 Schema Template (Standard)

Har table mein yeh 3 columns hamesha hone chahiye:

```sql
id          uuid    DEFAULT gen_random_uuid() PRIMARY KEY
user_id     uuid    REFERENCES auth.users(id)   -- RLS ke liye zaroori
created_at  timestamp DEFAULT now()
```

### 2.3 Common Project Schemas

#### 📦 Billing / Inventory App

```sql
-- Products Table
CREATE TABLE products (
  id          uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  user_id     uuid REFERENCES auth.users(id),
  name        text NOT NULL,
  sku         text UNIQUE,
  price       numeric(10,2) DEFAULT 0,
  stock       integer DEFAULT 0,
  category    text,
  created_at  timestamp DEFAULT now()
);

-- Customers Table
CREATE TABLE customers (
  id          uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  user_id     uuid REFERENCES auth.users(id),
  name        text NOT NULL,
  phone       text,
  email       text,
  address     text,
  created_at  timestamp DEFAULT now()
);

-- Sales Table
CREATE TABLE sales (
  id              uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  user_id         uuid REFERENCES auth.users(id),
  customer_id     uuid REFERENCES customers(id),
  total           numeric(10,2),
  discount        numeric(10,2) DEFAULT 0,
  status          text DEFAULT 'paid',  -- paid | pending | cancelled
  invoice_number  text UNIQUE,
  created_at      timestamp DEFAULT now()
);

-- Sale Items (har sale ke products)
CREATE TABLE sale_items (
  id          uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  sale_id     uuid REFERENCES sales(id) ON DELETE CASCADE,
  product_id  uuid REFERENCES products(id),
  quantity    integer NOT NULL,
  price       numeric(10,2) NOT NULL,
  created_at  timestamp DEFAULT now()
);
```

#### 🎓 Coaching / Student Management App

```sql
-- Students Table
CREATE TABLE students (
  id          uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  user_id     uuid REFERENCES auth.users(id),
  name        text NOT NULL,
  phone       text,
  parent_phone text,
  batch       text,
  fee_amount  numeric(10,2),
  created_at  timestamp DEFAULT now()
);

-- Fees Table
CREATE TABLE fees (
  id          uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  user_id     uuid REFERENCES auth.users(id),
  student_id  uuid REFERENCES students(id),
  amount      numeric(10,2),
  month       text,  -- "January 2025"
  status      text DEFAULT 'pending',  -- paid | pending
  paid_date   timestamp,
  created_at  timestamp DEFAULT now()
);

-- Attendance Table
CREATE TABLE attendance (
  id          uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  user_id     uuid REFERENCES auth.users(id),
  student_id  uuid REFERENCES students(id),
  date        date NOT NULL,
  status      text DEFAULT 'present',  -- present | absent | late
  created_at  timestamp DEFAULT now()
);
```

### 2.4 Schema Review Checklist

Schema banane ke baad yeh check karo:

- [ ] Har table mein `user_id` hai? (RLS ke liye)
- [ ] Foreign keys sahi hain? (sale_items → sales, sales → customers)
- [ ] `ON DELETE CASCADE` lagaya jahan zaroori tha?
- [ ] Status fields mein valid values sochi hain? (paid/pending/cancelled)
- [ ] Numeric fields `numeric(10,2)` hain for money?
- [ ] Har table mein `created_at` hai?

---

## 🧩 Step 3: AI Brain Setup — AGENTS, BLUEPRINT, TASKS

Yeh 3 files project ki neev hain. AI ko baar baar upload karoge inhe.

### 3.1 `AGENTS.md` — AI ke liye Rules

```markdown
# AI Rules — [Project Name]

## Tech Stack (STRICT — change mat karna)
- Framework: Next.js 14 App Router
- Language: TypeScript (strict mode)
- Styling: Tailwind CSS + Shadcn UI
- Database: Supabase (PostgreSQL)
- Auth: Supabase Auth
- Deployment: Vercel

## Coding Rules (NEVER violate)
1. TypeScript mein `any` type KABHI use mat karna
2. Server components default hain — zaroorat ho tabhi `use client` lagao
3. API keys KABHI hardcode mat karna — sirf `process.env.VARIABLE`
4. Har API route mein proper error handling hona chahiye
5. Supabase ke liye:
   - Server side: `createServerClient` from `@supabase/ssr`
   - Client side: `createBrowserClient` from `@supabase/ssr`
6. Sirf apne assigned file/folder ko touch karo
7. Kaam complete hone ke baad TASKS.md mein [x] lagao

## File Naming
- Components: PascalCase → `ProductCard.tsx`
- Utilities: camelCase → `formatCurrency.ts`
- Route folders: kebab-case → `/sale-history/`
- Types: PascalCase + `.types.ts` → `Product.types.ts`

## Folder Rules
- New components → `components/custom/`
- Shadcn components → `components/ui/` (touch mat karna)
- Supabase helpers → `lib/supabase/`
- Type definitions → `types/`
- Helper functions → `lib/utils/`

## Response Format
Kaam khatam hone ke baad batao:
1. Kaunsi files banayi/edit ki
2. Kya kiya ek line mein
3. Next step kya hona chahiye
```

### 3.2 `PROJECT_BLUEPRINT.md` — Architecture Document

```markdown
# Project Blueprint: [App Name]

## Overview
- **Project:** [Name]
- **Type:** [Billing App / SaaS / Management Tool]
- **Users:** [Admin: 1, Staff: 3]
- **Deadline:** [Date]

## User Roles
| Role | Access |
|------|--------|
| Admin | Full access |
| Staff | Limited — no delete, no reports |

## Database Schema
[Apna poora schema yahaan paste karo]

## Pages / Routes
| Route | Page | Who Can Access |
|-------|------|----------------|
| /login | Login | All |
| /dashboard | Main Dashboard | Admin, Staff |
| /products | Product List | Admin, Staff |
| /products/add | Add Product | Admin only |
| /sales | Sales List | Admin, Staff |
| /sales/new | New Sale | Admin, Staff |
| /reports | Reports | Admin only |
| /settings | Settings | Admin only |

## Module Priority (Build in this order)
1. Auth (Login + Middleware)
2. Dashboard (Basic stats)
3. [Main Module — e.g., Products]
4. [Transaction Module — e.g., Sales]
5. Reports
6. Settings

## Environment Variables Needed
- NEXT_PUBLIC_SUPABASE_URL
- NEXT_PUBLIC_SUPABASE_ANON_KEY
- [any others]
```

### 3.3 `TASKS.md` — Step-by-Step Checklist

```markdown
# Build Tasks — [Project Name]

## Phase 1: Foundation
- [ ] 0.1 Next.js project create (`npx create-next-app`)
- [ ] 0.2 Tailwind + Shadcn UI setup
- [ ] 0.3 Supabase project create (online)
- [ ] 0.4 Database tables + RLS setup (SQL run karo)
- [ ] 0.5 `.env.local` setup

## Phase 2: Auth
- [ ] 1.1 Login page UI (email + password form)
- [ ] 1.2 Supabase Auth connect
- [ ] 1.3 Middleware — protected routes
- [ ] 1.4 Logout functionality
- [ ] 1.5 Profiles table + role setup

## Phase 3: Layout & Navigation
- [ ] 2.1 Dashboard layout (sidebar + header)
- [ ] 2.2 Sidebar navigation links
- [ ] 2.3 Mobile responsive sidebar (hamburger menu)
- [ ] 2.4 User avatar + name in header

## Phase 4: [Main Module]
- [ ] 3.1 [Module] table created in Supabase
- [ ] 3.2 RLS policies for [module]
- [ ] 3.3 [Module] list page — fetch + display
- [ ] 3.4 Add [module] form + API route
- [ ] 3.5 Edit [module] functionality
- [ ] 3.6 Delete [module] with confirmation
- [ ] 3.7 Search + filter

## Phase 5: [Transaction Module]
- [ ] 4.1 [Transaction] form UI
- [ ] 4.2 [Transaction] creation API
- [ ] 4.3 Related data update (e.g., stock deduction)
- [ ] 4.4 [Transaction] list with filters

## Phase 6: Dashboard
- [ ] 5.1 Today's summary stats
- [ ] 5.2 Recent transactions table
- [ ] 5.3 Alert widgets (low stock, pending dues)

## Phase 7: Reports
- [ ] 6.1 Date range filter component
- [ ] 6.2 Data table with totals
- [ ] 6.3 PDF export (jsPDF)
- [ ] 6.4 Excel export (xlsx)

## Phase 8: Settings
- [ ] 7.1 Business profile form
- [ ] 7.2 Logo upload (Supabase Storage)
- [ ] 7.3 Change password
- [ ] 7.4 Invoice template settings

## Phase 9: Polish & Deploy
- [ ] 8.1 Error boundaries add karo
- [ ] 8.2 Loading states har jagah
- [ ] 8.3 Empty states har page pe
- [ ] 8.4 Mobile responsive test
- [ ] 8.5 Vercel deployment
- [ ] 8.6 Custom domain connect
```

---

## 🐙 Step 4: Safe GitHub Setup

Kabhi bhi bina Git ke code mat karo. Galti hogi to wapas aa sako.

```bash
# 1. GitHub pe nayi PRIVATE repo banao (browser mein)

# 2. Clone karo apne computer pe
git clone https://github.com/tumhara-username/project-name.git
cd project-name

# 3. KABHI main branch pe code mat karo
git checkout -b develop

# 4. Pehla commit karo (brain files ke saath)
touch AGENTS.md PROJECT_BLUEPRINT.md TASKS.md
git add .
git commit -m "docs: project brain files initialized"
git push origin develop
```

### Branch Strategy (Simple)

```
main
 └── develop          ← Yahan se sab kaam hoga
      ├── feature/auth
      ├── feature/products
      ├── feature/sales
      └── feature/reports
```

```bash
# Nayi module shuru karte waqt:
git checkout -b feature/module-name

# Module complete hone ke baad develop mein merge karo:
git checkout develop
git merge feature/module-name
git push origin develop
```

### Commit Message Format

```bash
git commit -m "feat: login page UI complete"      # nayi cheez
git commit -m "fix: sales form submit error"      # bug fix
git commit -m "style: dashboard card redesign"    # UI change
git commit -m "refactor: moved api to lib"        # restructure
git commit -m "docs: updated TASKS.md"            # documentation
```

---

## ⚡ Step 5: Project Initialize Karo

```bash
# Next.js project create karo
npx create-next-app@latest . --typescript --tailwind --eslint --app --src-dir=false

# Prompts ke jawab:
# ✔ Would you like to use TypeScript? → Yes
# ✔ Would you like to use ESLint? → Yes
# ✔ Would you like to use Tailwind CSS? → Yes
# ✔ Would you like to use `src/` directory? → No
# ✔ Would you like to use App Router? → Yes
# ✔ Would you like to customize the import alias? → No
```

### Shadcn UI Install

```bash
npx shadcn@latest init

# Prompts:
# ✔ Which style would you like to use? → Default
# ✔ Which color would you like to use as base color? → Slate
# ✔ Would you like to use CSS variables for colors? → Yes
```

### Common Shadcn Components Install

```bash
npx shadcn@latest add button input label card table badge
npx shadcn@latest add dialog sheet dropdown-menu avatar
npx shadcn@latest add form select textarea toast skeleton
```

### Required Packages

```bash
# Supabase
npm install @supabase/supabase-js @supabase/ssr

# Forms
npm install react-hook-form @hookform/resolvers zod

# Date handling
npm install date-fns

# PDF Generation
npm install jspdf jspdf-autotable

# Excel Export
npm install xlsx

# Icons (Lucide already comes with Shadcn)
# npm install lucide-react (already installed)
```

### Folder Structure Create Karo

```bash
mkdir -p app/(auth)/login
mkdir -p app/(dashboard)/dashboard
mkdir -p app/(dashboard)/products
mkdir -p app/(dashboard)/sales
mkdir -p app/(dashboard)/reports
mkdir -p app/(dashboard)/settings
mkdir -p app/api/products
mkdir -p app/api/sales
mkdir -p components/custom
mkdir -p lib/supabase
mkdir -p lib/utils
mkdir -p types
```

---

## 🗄️ Step 6: Supabase Setup — Database & Auth

### 6.1 Supabase Project Banao

```
1. supabase.com pe jao → New Project
2. Project name, password note karo
3. Region: Southeast Asia (Singapore) — India ke liye best
4. Plan: Free tier (development ke liye enough)
```

### 6.2 `.env.local` File

Project root mein banao:

```env
# Supabase — Settings → API se copy karo
NEXT_PUBLIC_SUPABASE_URL=https://xxxxxxxxxx.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...

# App URL
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

> ⚠️ **`.gitignore` mein add karo** — `.env.local` kabhi commit mat karna!

### 6.3 Supabase Client Files

**`lib/supabase/client.ts`** (Browser ke liye):
```typescript
import { createBrowserClient } from '@supabase/ssr'

export function createClient() {
  return createBrowserClient(
    process.env.NEXT_PUBLIC_SUPABASE_URL!,
    process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY!
  )
}
```

**`lib/supabase/server.ts`** (Server Components ke liye):
```typescript
import { createServerClient } from '@supabase/ssr'
import { cookies } from 'next/headers'

export async function createClient() {
  const cookieStore = await cookies()
  return createServerClient(
    process.env.NEXT_PUBLIC_SUPABASE_URL!,
    process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY!,
    {
      cookies: {
        getAll() { return cookieStore.getAll() },
        setAll(cookiesToSet) {
          try {
            cookiesToSet.forEach(({ name, value, options }) =>
              cookieStore.set(name, value, options)
            )
          } catch {}
        },
      },
    }
  )
}
```

### 6.4 SQL Run Karo (Supabase Dashboard → SQL Editor)

```sql
-- Step 1: Tables banao (apna schema yahaan paste karo)
CREATE TABLE products (
  id         uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  user_id    uuid REFERENCES auth.users(id),
  name       text NOT NULL,
  price      numeric(10,2) DEFAULT 0,
  stock      integer DEFAULT 0,
  created_at timestamp DEFAULT now()
);

-- Step 2: RLS Enable karo (HAR TABLE PE)
ALTER TABLE products ENABLE ROW LEVEL SECURITY;

-- Step 3: Policies banao (HAR TABLE PE)
CREATE POLICY "Select own" ON products FOR SELECT USING (auth.uid() = user_id);
CREATE POLICY "Insert own" ON products FOR INSERT WITH CHECK (auth.uid() = user_id);
CREATE POLICY "Update own" ON products FOR UPDATE USING (auth.uid() = user_id);
CREATE POLICY "Delete own" ON products FOR DELETE USING (auth.uid() = user_id);
```

---

## 🔄 Step 7: Module-by-Module Build Karo

**The Build Loop — Har module ke liye yahi process:**

```
┌──────────────────────────────────────────────┐
│                THE BUILD LOOP                │
│                                              │
│   TASKS.md → ek task uthao                  │
│         │                                    │
│         ▼                                    │
│   AI ko SPECIFIC prompt do                  │
│         │                                    │
│         ▼                                    │
│   npm run dev → browser mein dekho          │
│         │                                    │
│         ├── ✅ Kaam kiya?                    │
│         │        └→ git commit               │
│         │           TASKS.md mein [x]        │
│         │           Next task                │
│         │                                    │
│         └── ❌ Error aaya?                   │
│                  └→ Error copy karo          │
│                     AI ko do                 │
│                     Fix test karo            │
└──────────────────────────────────────────────┘
```

---

## 🔐 Step 8: Authentication — Login & Roles

### 8.1 Middleware Setup

**`middleware.ts`** (project root mein):

```typescript
import { createServerClient } from '@supabase/ssr'
import { NextResponse, type NextRequest } from 'next/server'

export async function middleware(request: NextRequest) {
  let supabaseResponse = NextResponse.next({ request })

  const supabase = createServerClient(
    process.env.NEXT_PUBLIC_SUPABASE_URL!,
    process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY!,
    {
      cookies: {
        getAll() { return request.cookies.getAll() },
        setAll(cookiesToSet) {
          cookiesToSet.forEach(({ name, value }) => request.cookies.set(name, value))
          supabaseResponse = NextResponse.next({ request })
          cookiesToSet.forEach(({ name, value, options }) =>
            supabaseResponse.cookies.set(name, value, options)
          )
        },
      },
    }
  )

  const { data: { user } } = await supabase.auth.getUser()

  // Protected routes — login nahi hai to redirect
  if (!user && request.nextUrl.pathname.startsWith('/dashboard')) {
    return NextResponse.redirect(new URL('/login', request.url))
  }

  // Already logged in → login page pe mat jaao
  if (user && request.nextUrl.pathname === '/login') {
    return NextResponse.redirect(new URL('/dashboard', request.url))
  }

  return supabaseResponse
}

export const config = {
  matcher: ['/((?!_next/static|_next/image|favicon.ico).*)'],
}
```

### 8.2 AI Prompt for Login Page

```
Read AGENTS.md and PROJECT_BLUEPRINT.md.

Task: TASKS.md → 1.1 Login page UI

Create app/(auth)/login/page.tsx

Requirements:
- Email aur password input fields
- "Login" button with loading state
- Error message display if wrong credentials
- Use Shadcn UI: Card, Input, Button, Label
- Tailwind styling — clean, professional look
- Form validation: email format check, password required
- After successful login: redirect to /dashboard
- Use createBrowserClient from lib/supabase/client.ts

Do NOT create any other files.
After done, tell me exactly what you created.
```

### 8.3 Role-Based Access (Admin vs Staff)

**Profiles table banao:**

```sql
CREATE TABLE profiles (
  id         uuid REFERENCES auth.users(id) PRIMARY KEY,
  role       text DEFAULT 'staff',  -- admin | staff
  full_name  text,
  created_at timestamp DEFAULT now()
);

ALTER TABLE profiles ENABLE ROW LEVEL SECURITY;
CREATE POLICY "View own profile" ON profiles FOR SELECT USING (auth.uid() = id);
CREATE POLICY "Update own profile" ON profiles FOR UPDATE USING (auth.uid() = id);

-- Auto-create profile on signup
CREATE OR REPLACE FUNCTION handle_new_user()
RETURNS trigger AS $$
BEGIN
  INSERT INTO profiles (id, role, full_name)
  VALUES (new.id, 'staff', new.raw_user_meta_data->>'full_name');
  RETURN new;
END;
$$ LANGUAGE plpgsql SECURITY DEFINER;

CREATE TRIGGER on_auth_user_created
  AFTER INSERT ON auth.users
  FOR EACH ROW EXECUTE FUNCTION handle_new_user();
```

---

## 🏗️ Step 9: Core Features Build Karo

### 9.1 Data Fetch Pattern (Server Component)

```typescript
// app/(dashboard)/products/page.tsx
import { createClient } from '@/lib/supabase/server'

export default async function ProductsPage() {
  const supabase = await createClient()
  
  const { data: products, error } = await supabase
    .from('products')
    .select('*')
    .order('created_at', { ascending: false })

  if (error) {
    return <div>Error loading products</div>
  }

  return (
    <div>
      {/* Products list render karo */}
      {products.map(product => (
        <div key={product.id}>{product.name}</div>
      ))}
    </div>
  )
}
```

### 9.2 API Route Pattern (POST)

```typescript
// app/api/products/route.ts
import { createClient } from '@/lib/supabase/server'
import { NextRequest, NextResponse } from 'next/server'

export async function POST(request: NextRequest) {
  try {
    const supabase = await createClient()
    
    // Auth check
    const { data: { user }, error: authError } = await supabase.auth.getUser()
    if (authError || !user) {
      return NextResponse.json({ error: 'Unauthorized' }, { status: 401 })
    }
    
    // Request body parse karo
    const body = await request.json()
    const { name, price, stock } = body
    
    // Validation
    if (!name || !price) {
      return NextResponse.json({ error: 'Name and price required' }, { status: 400 })
    }
    
    // Database mein insert karo
    const { data, error } = await supabase
      .from('products')
      .insert({
        name,
        price: Number(price),
        stock: Number(stock) || 0,
        user_id: user.id
      })
      .select()
      .single()
    
    if (error) {
      return NextResponse.json({ error: error.message }, { status: 500 })
    }
    
    return NextResponse.json(data, { status: 201 })
    
  } catch (err) {
    return NextResponse.json({ error: 'Server error' }, { status: 500 })
  }
}
```

### 9.3 Form + Submit Pattern (Client Component)

```typescript
'use client'
import { useState } from 'react'
import { Button } from '@/components/ui/button'
import { Input } from '@/components/ui/input'

export default function AddProductForm() {
  const [loading, setLoading] = useState(false)
  const [error, setError] = useState('')

  async function handleSubmit(e: React.FormEvent<HTMLFormElement>) {
    e.preventDefault()
    setLoading(true)
    setError('')
    
    const formData = new FormData(e.currentTarget)
    
    try {
      const response = await fetch('/api/products', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          name: formData.get('name'),
          price: formData.get('price'),
          stock: formData.get('stock'),
        })
      })
      
      if (!response.ok) {
        const err = await response.json()
        setError(err.error)
        return
      }
      
      // Success — form reset ya redirect
      
    } catch (err) {
      setError('Something went wrong')
    } finally {
      setLoading(false)
    }
  }

  return (
    <form onSubmit={handleSubmit}>
      <Input name="name" placeholder="Product Name" required />
      <Input name="price" type="number" placeholder="Price" required />
      <Input name="stock" type="number" placeholder="Stock" />
      {error && <p className="text-red-500">{error}</p>}
      <Button type="submit" disabled={loading}>
        {loading ? 'Saving...' : 'Add Product'}
      </Button>
    </form>
  )
}
```

### 9.4 AI Prompt Template for Any Feature

```
Read AGENTS.md.

Task from TASKS.md: [exact task number and name]

Build: [Describe exactly what to build]

Input:
- [What data comes in]
- [From where — form/API/database]

Output:
- [What should happen/display]
- [Where to redirect/show]

Files to create/edit:
- [file path 1]
- [file path 2]

DO NOT touch:
- [file to leave alone]

Constraints:
- [Any specific rule — e.g., "Use server component"]
- [e.g., "Mobile responsive banana hai"]
- [e.g., "Error state aur loading state dono include karo"]

After done:
1. List files you touched
2. One line what you did
3. What I should test in browser
```

---

## 🎨 Step 10: UI Polish aur Responsive Design

### 10.1 Dashboard Layout AI Prompt

```
Create app/(dashboard)/layout.tsx

This is the main layout for all dashboard pages.

Requirements:
- Sidebar on left (desktop), hidden on mobile
- Hamburger menu for mobile
- Sidebar links: Dashboard, Products, Sales, Reports, Settings
- Active link highlight karo
- Header: App name on left, User name + Logout on right
- Main content area on right with padding
- Use Shadcn Sheet for mobile sidebar
- Use Lucide icons for nav items
- Responsive: lg mein sidebar visible, mobile mein sheet

Use CSS classes only — no inline styles.
```

### 10.2 Common UI Components Checklist

Har feature mein yeh hona chahiye:

```
EVERY LIST PAGE:
✅ Table/Card list of data
✅ "Add New" button
✅ Search input (client-side filter)
✅ Loading skeleton (while fetching)
✅ Empty state (jab koi data nahi)
✅ Delete confirm dialog
✅ Success/error toast notification

EVERY FORM PAGE:
✅ Form fields with labels
✅ Required field validation
✅ Loading state on submit button
✅ Error message display
✅ Cancel/Back button
✅ Success redirect or message
```

### 10.3 Loading Skeleton Pattern

```typescript
// components/custom/ProductSkeleton.tsx
import { Skeleton } from '@/components/ui/skeleton'

export function ProductSkeleton() {
  return (
    <div className="space-y-3">
      {[...Array(5)].map((_, i) => (
        <div key={i} className="flex items-center space-x-4">
          <Skeleton className="h-12 w-12 rounded" />
          <div className="space-y-2">
            <Skeleton className="h-4 w-[200px]" />
            <Skeleton className="h-4 w-[150px]" />
          </div>
        </div>
      ))}
    </div>
  )
}
```

### 10.4 Empty State Pattern

```typescript
// Jab koi data nahi
{products.length === 0 && (
  <div className="text-center py-12">
    <Package className="mx-auto h-12 w-12 text-gray-400" />
    <h3 className="mt-2 text-sm font-semibold text-gray-900">No products</h3>
    <p className="mt-1 text-sm text-gray-500">
      Start by adding your first product.
    </p>
    <div className="mt-6">
      <Button onClick={() => router.push('/products/add')}>
        Add Product
      </Button>
    </div>
  </div>
)}
```

---

## 🧪 Step 11: Testing Karo Properly

Har module complete hone ke baad yeh test karo:

### 11.1 Module Testing Checklist

```
AUTH MODULE:
□ Sahi credentials se login hota hai?
□ Galat password pe error dikhta hai?
□ /dashboard bina login access nahi hota?
□ Already logged in → /login pe redirect nahi hota?
□ Logout karne ke baad /login pe aata hai?

PRODUCTS MODULE:
□ Product list load hoti hai?
□ New product add hota hai?
□ Edit product kaam karta hai?
□ Delete product kaam karta hai?
□ Delete pe confirm dialog aata hai?
□ Search/filter kaam karta hai?
□ Koi product nahi → empty state dikhta hai?
□ Mobile pe sab sahi dikhta hai?

SALES MODULE:
□ New sale create hoti hai?
□ Stock automatically ghatta hai?
□ Customer ka record create hota hai?
□ Invoice number unique generate hota hai?
□ Total calculation sahi hai?
□ Sale delete pe stock wapas badhta hai?

DASHBOARD:
□ Today's totals sahi hain?
□ Recent sales dikhte hain?
□ Stats real data se match karti hain?
```

### 11.2 Browser Console Errors Check

```
Dev Tools kholne ke baad check karo:
□ Console mein koi red error nahi
□ Network tab mein failed requests nahi
□ No 404 errors for API routes
□ No Supabase RLS errors

Common Console Errors aur Fix:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
❌ "Failed to fetch"
→ API route exist nahi karti ya server nahi chala

❌ "new row violates row-level security"
→ RLS policy mein user_id sahi nahi pass ho rahi

❌ "Cannot read properties of undefined"
→ Data load hone se pehle render ho gaya
→ Fix: data?.property ya loading check karo

❌ "Hydration mismatch"
→ Server aur client render alag hain
→ Fix: dynamic import ya useEffect use karo
```

---

## 🔒 Step 12: Security Lockdown

### 12.1 RLS Final Check

```sql
-- Supabase SQL Editor mein run karo
-- Verify karo ki har table pe RLS enabled hai

SELECT schemaname, tablename, rowsecurity 
FROM pg_tables 
WHERE schemaname = 'public';

-- rowsecurity = true hona chahiye har row mein
```

### 12.2 API Route Security Pattern

Har API route mein pehle yeh check karo:

```typescript
// Template — har route mein copy karo
const { data: { user }, error: authError } = await supabase.auth.getUser()

if (authError || !user) {
  return NextResponse.json(
    { error: 'Unauthorized' },
    { status: 401 }
  )
}
```

### 12.3 Input Validation (Zod)

```typescript
import { z } from 'zod'

const ProductSchema = z.object({
  name: z.string().min(1, 'Name required').max(100),
  price: z.number().positive('Price must be positive'),
  stock: z.number().min(0).optional(),
})

// API route mein use karo:
const result = ProductSchema.safeParse(body)
if (!result.success) {
  return NextResponse.json(
    { error: result.error.errors[0].message },
    { status: 400 }
  )
}
```

### 12.4 Secret Keys Rule

```
✅ SAFE (publicly visible):
NEXT_PUBLIC_SUPABASE_URL
NEXT_PUBLIC_SUPABASE_ANON_KEY
NEXT_PUBLIC_RAZORPAY_KEY_ID

❌ NEVER NEXT_PUBLIC (server only):
SUPABASE_SERVICE_ROLE_KEY
RAZORPAY_KEY_SECRET
RESEND_API_KEY
DATABASE_URL
```

---

## 🚀 Step 13: Vercel Deployment

### 13.1 Pre-Deploy Checklist

```bash
# 1. Build error check karo
npm run build

# Koi error aaye to fix karo pehle

# 2. Final commit karo
git add .
git commit -m "feat: project complete — ready for deployment"
git push origin develop

# 3. develop → main merge karo (GitHub pe PR ya directly)
git checkout main
git merge develop
git push origin main
```

### 13.2 Vercel Deploy Steps

```
1. vercel.com → Sign in with GitHub

2. "Add New Project" → tumhari repo select karo

3. Framework: Next.js (auto-detect hoga)

4. Environment Variables add karo:
   ┌────────────────────────────────────────┐
   │ NEXT_PUBLIC_SUPABASE_URL    → [paste] │
   │ NEXT_PUBLIC_SUPABASE_ANON_KEY → [paste]│
   │ [any other secrets]         → [paste] │
   └────────────────────────────────────────┘

5. Deploy click karo!

6. Vercel ek live URL dega:
   https://project-name.vercel.app
```

### 13.3 Custom Domain Connect

```
Vercel Dashboard → Project → Settings → Domains

1. Add Domain: yourdomain.com

2. DNS Records update karo (GoDaddy/Namecheap pe):
   Type: CNAME
   Name: www
   Value: cname.vercel-dns.com

   Type: A
   Name: @
   Value: 76.76.21.21

3. Wait karo 24-48 hours (propagation)

4. SSL auto-lagega Vercel se (free)
```

### 13.4 Supabase Redirect URLs Update Karo

```
Supabase Dashboard → Authentication → URL Configuration

Site URL:
https://yourdomain.com

Redirect URLs (add karo):
https://yourdomain.com/auth/callback
https://project-name.vercel.app/auth/callback
```

---

## 🛠️ Step 14: Post-Launch Bug Fix Protocol

### 14.1 Bug Report Template (Client se lene ke liye)

```
Bug Report Format:

1. Kya kiya: [Exact steps]
2. Kya expect tha: [Expected result]
3. Kya hua: [Actual result]
4. Screenshot: [Attach karo]
5. Device: [Mobile/Desktop, Browser]
6. Time: [Kab hua]
```

### 14.2 Bug Fix Process

```
BUG AAYA
│
├── Step 1: Reproduce karo
│   (Khud same steps karo)
│
├── Step 2: Console error dekho
│   (Browser Dev Tools → Console)
│
├── Step 3: Supabase logs dekho
│   (Supabase Dashboard → Logs)
│
├── Step 4: Fix karo locally
│   (npm run dev mein test karo)
│
├── Step 5: Test karo thoroughly
│
├── Step 6: Commit aur push karo
│   git commit -m "fix: [describe the bug]"
│
└── Step 7: Vercel auto-deploy karega
    (production mein automatic update)
```

### 14.3 AI Bug Fix Prompt

```
I have a bug in production.

Error (from console/logs):
[Paste exact error]

Steps to reproduce:
1. [Step 1]
2. [Step 2]

Expected: [What should happen]
Actual: [What is happening]

Relevant file:
[Paste the file content]

Fix only this specific bug. Explain what was wrong.
```

---

## ⚡ Quick Reference Cheatsheet

### Git Commands

```bash
git status                        # Changes dekho
git add .                         # Sab stage karo
git commit -m "message"           # Save karo
git push origin branch-name       # GitHub pe bhejo
git restore .                     # Sab undo karo (last commit se)
git log --oneline -10             # Last 10 commits dekho
git diff                          # Changes ka detail dekho
```

### npm Commands

```bash
npm run dev          # Development server start
npm run build        # Production build test
npm run lint         # Code errors check
```

### Supabase Quick SQL

```sql
-- Table data dekho
SELECT * FROM products LIMIT 10;

-- User ka data dekho
SELECT * FROM products WHERE user_id = 'paste-user-id-here';

-- RLS status check
SELECT tablename, rowsecurity FROM pg_tables WHERE schemaname = 'public';

-- Policy list
SELECT * FROM pg_policies WHERE schemaname = 'public';
```

### Common Errors → Quick Fix

| Error | Reason | Fix |
|-------|--------|-----|
| `new row violates RLS` | user_id missing in insert | `user_id: user.id` add karo |
| `Cannot read undefined` | Data load hone se pehle render | `data?.field` use karo |
| `Module not found` | Import path galat | File path check karo |
| `Hydration mismatch` | Server/client alag render | `'use client'` check karo |
| `401 Unauthorized` | Auth token expire | Re-login karo |
| `500 Internal Server Error` | Server side code crash | API route console check karo |

### Shadcn Components — Kab Kya Use Karo

| Need | Component |
|------|-----------|
| Text input | `Input` |
| Dropdown select | `Select` |
| Button | `Button` |
| Modal popup | `Dialog` |
| Side drawer | `Sheet` |
| Notification | `Toast` (Sonner) |
| Data table | `Table` |
| Loading state | `Skeleton` |
| Status badge | `Badge` |
| Info card | `Card` |
| Confirm delete | `AlertDialog` |
| Date picker | `Calendar` + `Popover` |

---

## ✅ Final Project Completion Checklist

Project deliver karne se pehle:

```
FUNCTIONALITY:
□ All TASKS.md items [x] complete hain
□ Login / Logout kaam karta hai
□ Core features kaam karte hain (add/edit/delete/view)
□ Dashboard stats correct hain
□ Reports generate ho rahe hain

UI/UX:
□ Mobile pe test kiya (real device ya DevTools)
□ Loading states hain
□ Empty states hain
□ Error messages user-friendly hain
□ Forms validate karte hain

SECURITY:
□ RLS har table pe enabled hai
□ API routes mein auth check hai
□ .env.local Git mein nahi gaya
□ Vercel mein env variables add kiye hain

DEPLOYMENT:
□ npm run build koi error nahi deta
□ Vercel pe live chal raha hai
□ Custom domain connected hai (if required)
□ Supabase redirect URLs updated hain

HANDOVER:
□ Login credentials client ko diye
□ Training session complete
□ Training recording share ki
□ Support WhatsApp group active hai
```

---

## 🎯 Aage Kya Karna Hai

```
Week 1: Yeh document padhke TASKS.md banao apne project ke liye

Week 2: Database schema finalize karo aur Supabase pe create karo

Week 3: Auth + Layout build karo

Week 4: Core modules build karo

Week 5: Polish, test, aur deploy karo
```

> *"Perfect kab aayega? Kabhi nahi. Ship kar do — fixes production mein hoti hain."*

---

**Ab terminal kholo. Step 4 se shuru karo. Ek kaam. Ek baar. 🚀**

---

<div align="center">

*Built for real-world AI-first development — no fluff, only execution*

⭐ Agar helpful laga to Star karo!

</div>

---
*Version 1.0 | Last Updated: 2025*
