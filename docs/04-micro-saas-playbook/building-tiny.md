# Building Tiny

> Constraints make you profitable. Build the smallest thing that works.

## The 2-Day Rule

If you can't build it in 2 days, you're over-scoping.

**Breakdown:**
- Day 1: Core functionality, basic UI
- Day 2: Polish, deploy, test

This assumes you're using vibecoding properly. If you're doing everything manually, add a day or two — but question whether the scope is still "micro."

## Tech Stack for Micro-SaaS

Keep it simple and cheap.

### Recommended Stack

| Layer | Tool | Why |
|-------|------|-----|
| Frontend | Astro + Tailwind | Fast, static where possible |
| Backend | Cloudflare Workers | Zero cold start, generous free tier |
| Database | Cloudflare D1 | SQLite in the cloud, free tier |
| Auth | Simple email/password or magic link | Don't overcomplicate |
| Hosting | Cloudflare Pages + Workers | Free/cheap, fast globally |

### Cost Reality

| Component | Free Tier | Paid (when you exceed) |
|-----------|----------|----------------------|
| Pages | Unlimited | — |
| Workers | 100k req/day | $5/mo for 10M+ |
| D1 | 5M reads/day, 100k writes | ~$0.75 per extra million |
| KV | 100k reads/day | ~$0.50 per extra million |

**Reality:** Most Micro-SaaS tools for single clients will never leave free tier.

## Architecture Pattern

Keep it dead simple:

```
┌─────────────────┐
│  Static Pages   │  ← Astro (Client UI)
│  (Cloudflare    │
│   Pages)        │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  API Workers    │  ← Cloudflare Workers
│  (few routes)   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  D1 Database    │  ← Simple SQLite
└─────────────────┘
```

For most Micro-SaaS:
- 2-5 API routes
- 2-4 database tables
- 3-6 pages/screens

## Example: Booking System

### Database (2 tables)

```sql
-- Slots available per day
CREATE TABLE slots (
  id INTEGER PRIMARY KEY,
  date TEXT NOT NULL,
  time TEXT NOT NULL,
  available INTEGER DEFAULT 1
);

-- Bookings made
CREATE TABLE bookings (
  id INTEGER PRIMARY KEY,
  slot_id INTEGER,
  customer_name TEXT,
  customer_phone TEXT,
  created_at TEXT
);
```

### API Routes (4 routes)

```
GET  /api/slots?date=2024-01-15    → Available slots for date
POST /api/bookings                 → Create booking
GET  /api/admin/bookings           → All bookings (admin)
POST /api/admin/slots              → Add/edit slots (admin)
```

### Pages (3 pages)

1. **Customer booking page** — Shows slots, takes booking
2. **Admin dashboard** — Shows all bookings
3. **Admin slot editor** — Manage availability

That's the entire app.

## Building Checklist

### Before You Start
- [ ] Scope defined in one paragraph
- [ ] Core feature identified (the ONE thing)
- [ ] Database schema sketched (2-4 tables max)
- [ ] API routes listed (5 max)
- [ ] UI screens listed (5 max)

### During Build
- [ ] Start with database and API
- [ ] Build simplest possible UI
- [ ] Test core flow end-to-end
- [ ] Mobile-friendly (most clients use phones)
- [ ] Don't add features not in scope

### Before Handoff
- [ ] Works on mobile and desktop
- [ ] Error handling (show user-friendly messages)
- [ ] Basic security (auth on admin routes)
- [ ] Deployed to production URL
- [ ] Tested with real data

## Common Mistakes

### Mistake 1: Adding Auth Complexity

Don't build a full user system for one client.

**Simple approach:**
- Admin: Single password or magic link
- Customers: No login needed (booking by phone/name)

### Mistake 2: Building Admin Dashboard Features

Client asks for "reports" or "analytics."

**Reality check:** Do they need it?
- If they have 10 bookings/week, they can count manually
- If they need exports, add CSV download (1 hour)
- Don't build a dashboard they won't use

### Mistake 3: Over-Engineering

You don't need:
- Caching (traffic is low)
- Queue systems (nothing is async)
- Microservices (one Worker is enough)
- CI/CD pipelines (wrangler deploy is fine)

### Mistake 4: Premature Optimization

Build it. Deploy it. See if it breaks.

Single client = low traffic = no scaling issues.

## Feature Requests During Build

Client will ask for more. Every time.

**Response:**
> "Great idea. That's outside current scope. I can add it for $[X]. Want me to include it in the next update?"

Track requests. Some become real features. Some don't.

## When to Stop

Ship when:
1. Core flow works
2. UI is usable (not beautiful, usable)
3. Admin can do what they need
4. It's deployed and accessible

Don't wait for:
- Perfect design
- Every edge case handled
- Features "they might need"

---

**Next**: [Client Handoff](client-handoff.md) — Training, support, and maintenance.
