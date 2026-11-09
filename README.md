# Territorial Army Website & Admin Panel

Complete rebuild of the Territorial Army website (reference: jointerritorialarmy.com) with a fully-featured custom admin panel for non-technical administrators.

---

## Project Summary

| Item | Value |
|---|---|
| **Project cost** | ₹60,000 – ₹65,000 (one-time) |
| **Timeline** | ~10 weeks (2.5 months) |
| **Deliverable** | Custom website + admin panel + source code + 30 days support |
| **Monthly running cost** | ₹1,100 – ₹3,800 (hosting, storage, email) |

---

## Tech Stack

| Layer | Technology |
|---|---|
| Public Website | Laravel 11 + Blade + Tailwind CSS + Alpine.js |
| Admin Panel | Filament v3 |
| Backend | Laravel 11 (PHP 8.3) |
| Database | MySQL 8 |
| File Storage | Cloudflare R2 |
| Payments | Razorpay |
| Email | Resend / AWS SES |
| Hosting | VPS (Hostinger / Hetzner) |
| CDN & Security | Cloudflare |

---

## Admin Panel Modules

1. **Orders** – pending / successful / rejected, Excel export
2. **Pages** – dynamic page builder with parent/menu/description
3. **Result Registration** – exam signup data with zone filter, Excel export
4. **Officer Subscribers** – verified / unverified / unsubscribed
5. **Soldier Subscribers** – verified / unverified / unsubscribed
6. **PDFs** – PDF library upload & management
7. **Study Material** – study material files library
8. **Books** – books catalog
9. **Exam Names** – exam master list
10. **Slider** – homepage banner management
11. **Newsline & Reviews** – announcements + review moderation

> Removed from scope per client: Consignment CSV, Coupons, Exam Center, Move to 100% Officers.

---

## Project Phases

### Phase 1 — Discovery & Planning  *(Week 1)*
**Goal:** Lock requirements, design, and architecture before writing code.

- [ ] Client kickoff call & requirement finalization
- [ ] Wireframes for all public pages
- [ ] Wireframes for admin panel screens
- [ ] Color palette, typography, logo review
- [ ] Database schema design (ERD for 15+ tables)
- [ ] URL structure & sitemap
- [ ] Sign-off from client on wireframes

**Deliverables:** Wireframes PDF, ERD diagram, approved scope document.
**Payment milestone:** 40% advance (~₹25,000)

---

### Phase 2 — Backend Foundation  *(Week 2)*
**Goal:** Set up Laravel project, database, and core auth.

- [ ] Laravel 11 project setup with Git repository
- [ ] MySQL database creation & connection
- [ ] All migrations: pages, orders, subscribers, pdfs, books, study_material, exams, sliders, newsline, reviews, admins
- [ ] Eloquent models with relationships
- [ ] Factory + seeders for test data
- [ ] Filament v3 installation
- [ ] Admin authentication (login, password reset, change password)
- [ ] Role-based middleware
- [ ] Cloudflare R2 storage configuration

**Deliverables:** Working Laravel + Filament skeleton with login.

---

### Phase 3 — Admin Panel: Core Modules  *(Weeks 3–4)*
**Goal:** Build the admin panel that the client will use daily.

#### Week 3
- [ ] Orders module (table, filters by status, search, Excel export)
- [ ] Pages module (hierarchical parent-child, rich text editor, publish/draft)
- [ ] Sliders module (image upload, ordering, enable/disable)
- [ ] Newsline module (announcements CRUD)
- [ ] Reviews module (moderation workflow)

#### Week 4
- [ ] PDFs module (upload to R2, metadata, category)
- [ ] Study Material module
- [ ] Books module
- [ ] Exam Names master list
- [ ] Officer Subscribers (verified / unverified / unsubscribed tabs + Excel export)
- [ ] Soldier Subscribers (same structure)
- [ ] Result Registration (filter by exam & zone, bulk delete, Excel export)

**Deliverables:** Fully functional admin panel - all 11 modules working.
**Payment milestone:** 30% on admin demo (~₹18,750)

---

### Phase 4 — Public Website Frontend  *(Weeks 5–6)*
**Goal:** Build the public-facing site that visitors see.

#### Week 5
- [ ] Homepage (hero slider, newsline ticker, featured content)
- [ ] Dynamic page rendering (reads from `pages` table)
- [ ] Auto-generated navigation menu (from parent-child pages)
- [ ] Mobile-responsive layout (Tailwind breakpoints)
- [ ] PDF library page (search, filter, download)
- [ ] Study material & books pages

#### Week 6
- [ ] Exam result registration form (public-facing)
- [ ] Officer subscription form (with OTP flow)
- [ ] Soldier subscription form (with OTP flow)
- [ ] Reviews display page
- [ ] Contact / about pages
- [ ] SEO: meta tags, Open Graph, sitemap.xml, robots.txt
- [ ] Favicon & PWA manifest

**Deliverables:** Public site visible to visitors, admin can control everything from the panel.

---

### Phase 5 — Payments & Order Flow  *(Week 7)*
**Goal:** Full e-commerce order lifecycle.

- [ ] Book product pages with "Buy Now" button
- [ ] Shopping cart (session-based)
- [ ] Checkout form (name, address, mobile)
- [ ] Razorpay integration (order create, checkout, webhook)
- [ ] Order status transitions (pending → successful / rejected)
- [ ] Order confirmation email to customer
- [ ] Order notification to admin
- [ ] Order detail view in admin (with status change buttons)
- [ ] Excel export of orders (filtered)

**Deliverables:** Working end-to-end order flow with live Razorpay.

---

### Phase 6 — Email & Automation  *(Week 8)*
**Goal:** All email flows and queued jobs.

- [ ] SMTP / Resend / SES configuration
- [ ] Email templates (Blade): OTP, welcome, order confirmation, order status update
- [ ] Laravel Queue setup (database driver + Supervisor)
- [ ] OTP generation & verification logic
- [ ] Subscriber verification email flow
- [ ] Unsubscribe link handler
- [ ] Newsletter export CSV (admin → external email tool)
- [ ] Rate limiting on public forms

**Deliverables:** Emails delivered reliably in background.

---

### Phase 7 — Data Migration  *(Week 8, parallel)*
**Goal:** Move existing data from old site to new system.

- [ ] Export old MySQL database dump
- [ ] Write migration scripts (old schema → new schema)
- [ ] Migrate: pages, orders, subscribers, PDFs
- [ ] Download old PDFs & re-upload to R2
- [ ] URL redirects (old URLs → new URLs) for SEO preservation
- [ ] Verify data integrity (counts, random spot checks)

**Deliverables:** All existing data available in new system.

---

### Phase 8 — Testing & QA  *(Week 9)*
**Goal:** Catch bugs before client sees them.

- [ ] Cross-browser testing (Chrome, Firefox, Safari, Edge)
- [ ] Mobile device testing (iOS Safari, Android Chrome)
- [ ] Form validation edge cases
- [ ] Payment flow testing with Razorpay test mode
- [ ] Admin workflow testing (create/edit/delete every module)
- [ ] File upload size & type validation
- [ ] SQL injection / XSS / CSRF audit
- [ ] Load test (homepage, PDF listing)
- [ ] Lighthouse audit (performance, SEO, accessibility)
- [ ] Fix all critical & high-priority bugs

**Deliverables:** Bug report + fixes, ready for production.

---

### Phase 9 — Deployment & Handover  *(Week 10)*
**Goal:** Go live, train client, hand over everything.

- [ ] VPS provisioning (Hostinger / Hetzner)
- [ ] Nginx + PHP-FPM + MySQL setup
- [ ] SSL certificate (Let's Encrypt)
- [ ] Cloudflare DNS + CDN + security rules
- [ ] Deploy application via Git
- [ ] Setup Supervisor for queue workers
- [ ] Cron job for scheduled tasks
- [ ] Database backups (daily automated)
- [ ] `.env` production configuration
- [ ] Admin training session (1–2 hours, screen recorded)
- [ ] User manual PDF for admin
- [ ] Source code handover (Git repo access)
- [ ] 30-day post-launch bug-fix support begins

**Deliverables:** Live website, trained admin, documentation, source code.
**Payment milestone:** 30% final (~₹18,750)

---

## Milestones Summary

| Week | Phase | Milestone |
|---|---|---|
| 1 | Discovery | Wireframes signed off |
| 2 | Foundation | Admin login working |
| 3–4 | Admin Panel | All 11 modules demo-able |
| 5–6 | Public Site | Website visible to public |
| 7 | Payments | Order flow live |
| 8 | Email + Migration | Automation + old data in place |
| 9 | QA | Zero critical bugs |
| 10 | Launch | Live on production |

---

## Payment Schedule

| Milestone | % | Amount (at ₹62,500) |
|---|---|---|
| Project kickoff | 40% | ₹25,000 |
| Admin panel demo (end of week 4) | 30% | ₹18,750 |
| Final delivery & handover | 30% | ₹18,750 |

---

## What's Included

- Complete custom-designed public website (10+ pages, fully responsive)
- Fully-featured admin panel with all 11 modules
- Razorpay payment gateway integration
- Email subscriber system with OTP verification
- PDF, book, and study material library
- Dynamic page builder with hierarchical menus
- Homepage slider, newsline, and reviews management
- Order management with Excel export
- Data migration from existing website
- Deployment on VPS with SSL and Cloudflare
- Admin training session (1–2 hours)
- 30 days of post-launch bug-fix support
- Complete source code handover

## What's NOT Included (Optional Add-Ons)

| Add-On | Cost |
|---|---|
| Logo design / brand identity | ₹5,000 – ₹15,000 |
| Content writing (per page) | ₹500 |
| Annual maintenance contract | ₹15,000 / year |
| SEO setup + Search Console | ₹5,000 one-time |
| WhatsApp Business API | ₹8,000 one-time |

---

## Recurring Monthly Costs (Paid by Client)

| Item | ₹ / month |
|---|---|
| VPS Hosting | 600 – 1,500 |
| Domain (annual ÷ 12) | 100 |
| Cloudflare CDN | Free |
| Cloudflare R2 (PDFs) | 130 |
| Email service | 0 – 1,700 |
| SSL (Let's Encrypt) | Free |
| Razorpay | 2% per transaction |
| **Total** | **₹1,100 – ₹3,800** |

---

## Repository Structure (once scaffolded)

```
.
├── app/
│   ├── Filament/           # Admin panel resources
│   ├── Http/Controllers/   # Public site controllers
│   ├── Models/             # Eloquent models
│   └── Services/           # Razorpay, Email, R2 helpers
├── database/
│   ├── migrations/
│   └── seeders/
├── resources/
│   └── views/              # Blade templates (public site)
├── routes/
│   ├── web.php
│   └── admin.php
└── README.md
```

---

## Contact

Any changes to scope, timeline, or budget will be documented and signed off before work begins.
