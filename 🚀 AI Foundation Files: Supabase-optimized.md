# (Product Requirements Document - The Master Seed)

> [!IMPORTANT]
> 🧠 Yeh file aapke cloud/web project ka **brain** hai. AI isse padh kar `ARCHITECTURE`, `SCHEMA`, `TASKS` sab generate karega.

## 🏷️ App ka Naam & Vision (📦 00_PRD.md)
**Project Name:** CloudPOS SaaS  
**Vision:** Real-time, multi-user inventory & billing web app for small retail businesses. Offline-capable sync included.

## 👥 Target Audience & Environment
- **Users:** Shop owners, cashiers, managers (non-tech friendly UI)
- **Environment:** Modern browsers (Chrome, Edge, Safari), PWA support for mobile/tablet
- **Network:** Requires internet for real-time sync, but supports offline queue with auto-resync on reconnect

## ⚙️ Strict Tech Stack
- **Frontend:** React 18 + Vite + TypeScript
- **Styling:** Tailwind CSS v4 + shadcn/ui components
- **State Management:** Zustand (global) + React Query (server cache/sync)
- **Backend/DB:** Supabase (PostgreSQL, Auth, Realtime, Storage)
- **Hosting:** Vercel / Netlify (CI/CD ready)

## 📦 Core Features (Must-Haves)
- 🔐 **Auth:** Email/Password + Google OAuth + Role-based access (Admin/Cashier)
- 📦 **Inventory:** Real-time stock tracking, barcode scan input, low-stock alerts
- 🧾 **Billing/GST:** Quick POS interface, automatic tax calculation, GST-compliant invoices
- 📤 **Exports:** PDF invoices (`@react-pdf/renderer`), CSV inventory reports
- 🔄 **Sync:** Optimistic UI updates + background Supabase realtime subscriptions

## 🚫 Business Logic & Strict Constraints
- Invoices **soft-delete only** (`deleted_at` timestamp), never hard delete
- Stock **cannot go negative** at DB level (check constraints + triggers)
- **Row Level Security (RLS)** mandatory on all tables. No table without RLS.
- All timestamps must be `timestamptz` (UTC)
- Frontend kabhi bhi `service_role` key access nahi karega. Sirf `anon` key use hogi.

## 🤖 Agentic/Developer Preferences
- Code comments Hinglish mein for complex logic
- Strict TypeScript (`strict: true`, no `any`)
- Tailwind utility classes only. Zero inline `style={{}}`
- AI hamesha `supabase-js v2` patterns follow karega
- Error boundaries aur toast notifications mandatory

## 🔮 The Magic Prompt
```text
AI Instruction: Read this 00_PRD.md very carefully and generate ARCHITECTURE_MASTER.md, SCHEMA.md (PostgreSQL/Supabase format with RLS), AGENTS.md, GEMINI.md, PROJECT_BLUEPRINT.md, and TASKS.md. Ensure all cloud sync, auth, and security rules are strictly implemented.
```


### 🗃️ `SCHEMA.md` (Supabase/PostgreSQL Optimized)

# 🗃️ SCHEMA.md (Database Blueprint - Supabase/PostgreSQL)

> [!NOTE]
> Sirf database design aur security rules. AI inhi tables/RLS ke hisaab se client code generate karega.

## 📋 Table List
`profiles`, `products`, `categories`, `invoices`, `invoice_items`, `audit_logs`

## 🏗️ Table Structure (PostgreSQL)
```sql
-- Enable UUID extension (Supabase default)
create extension if not exists "uuid-ossp";

-- 1. PROFILES (Extends Supabase auth.users)
create table public.profiles (
  id uuid references auth.users(id) primary key,
  role text check (role in ('admin', 'cashier')) default 'cashier',
  full_name text not null,
  created_at timestamptz default now(),
  updated_at timestamptz default now()
);

-- 2. PRODUCTS
create table public.products (
  id uuid default uuid_generate_v4() primary key,
  sku text unique not null,
  name text not null,
  category_id uuid references public.categories(id),
  price numeric(10,2) not null check (price >= 0),
  stock_qty integer not null default 0 check (stock_qty >= 0),
  created_at timestamptz default now(),
  updated_at timestamptz default now()
);

-- 3. INVOICES
create table public.invoices (
  id uuid default uuid_generate_v4() primary key,
  invoice_no text unique not null,
  user_id uuid references public.profiles(id) not null,
  subtotal numeric(10,2) not null,
  tax_amount numeric(10,2) default 0,
  total_amount numeric(10,2) not null,
  status text check (status in ('paid', 'cancelled')) default 'paid',
  deleted_at timestamptz, -- Soft delete
  created_at timestamptz default now()
);

-- 4. INVOICE_ITEMS
create table public.invoice_items (
  id uuid default uuid_generate_v4() primary key,
  invoice_id uuid references public.invoices(id) on delete cascade not null,
  product_id uuid references public.products(id) not null,
  quantity integer not null check (quantity > 0),
  unit_price numeric(10,2) not null,
  total numeric(10,2) not null
);
```

## 🔐 Row Level Security (RLS) - MANDATORY
```sql
-- Enable RLS on all tables
alter table public.profiles enable row level security;
alter table public.products enable row level security;
alter table public.invoices enable row level security;
alter table public.invoice_items enable row level security;

-- Example RLS Policy (Users can only access their own org/tenant data)
create policy "Users can view own invoices" on public.invoices
  for select using (auth.uid() = user_id);

create policy "Admins can manage products" on public.products
  for all using (
    exists (select 1 from public.profiles where id = auth.uid() and role = 'admin')
  );
```

## 🔗 Relationships & Triggers
- `profiles.id` ↔ `auth.users.id` (1:1)
- `invoices.user_id` ↔ `profiles.id` (N:1)
- `invoice_items.invoice_id` ↔ `invoices.id` (N:1, `ON DELETE CASCADE`)
- `invoice_items.product_id` ↔ `products.id` (N:1)
- **Stock Trigger:** `BEFORE INSERT ON invoice_items` → Auto-decrement `products.stock_qty`. Rollback if `stock_qty < 0`.

## 🚀 Indexes & Performance
```sql
create index idx_products_sku on public.products(sku);
create index idx_invoices_user on public.invoices(user_id);
create index idx_invoices_status on public.invoices(status);
create index idx_invoice_items_invoice on public.invoice_items(invoice_id);
```

## 📌 Supabase Specific Notes
- Use `@supabase/supabase-js` v2 client
- Enable `Realtime` for `invoices` & `inventory` tables in Supabase dashboard
- Use `pg_cron` for auto-cleanup of `deleted_at > 90 days` if needed
- Environment variables: `VITE_SUPABASE_URL`, `VITE_SUPABASE_ANON_KEY`


### 🔁 Firebase ke liye Quick Adaptation Tips
Agar aap **Firebase (Firestore + Auth)** use karna chahte hain, toh bas yeh changes karein:
| Section | Supabase | Firebase Equivalent |
|:---|:---|:---|
| `id` Type | `UUID` | Auto-generated `string` (Firestore doc ID) |
| `SCHEMA.md` Format | SQL + RLS | NoSQL Collections/Documents + `firestore.rules` |
| Security | `Row Level Security` policies | `match /{collection}/{doc} { allow read, write: if request.auth.uid == resource.data.uid; }` |
| Realtime | Supabase Realtime | `onSnapshot()` listeners + IndexedDB persistence |
| Timestamps | `timestamptz` | `FieldValue.serverTimestamp()` |

✅ **Next Step:** Aap bas `00_PRD.md` aur `SCHEMA.md` ko apne repo mein paste karein, phir AI ko `"Read 00_PRD.md and generate remaining files"` prompt dein. Baaki AI khud `ARCHITECTURE`, `TASKS`, `AGENTS` sab cloud-optimized bana dega.

Koi specific feature (jaise Multi-tenant, Offline-first sync, ya Payment Gateway) add karna ho toh batao, main uska `SCHEMA` + `TASKS` block ready kar dunga! 🚀
