# Phase 1 — Database Schema (ERD)

MySQL 8, utf8mb4_unicode_ci, InnoDB. All tables have `id` (bigint PK), `created_at`, `updated_at`.

---

## Core Tables

### `admins`
Admin users for the panel.

| Column | Type | Notes |
|---|---|---|
| id | bigint PK | |
| name | varchar(100) | |
| email | varchar(150) | unique |
| password | varchar(255) | bcrypt |
| role | enum | `super_admin`, `editor` |
| last_login_at | timestamp | nullable |
| remember_token | varchar(100) | |

### `pages`
Dynamic pages the admin creates.

| Column | Type | Notes |
|---|---|---|
| id | bigint PK | |
| title | varchar(200) | |
| slug | varchar(200) | unique |
| parent_id | bigint FK | nullable → pages.id |
| menu_name | varchar(100) | shown in nav |
| description | longtext | rich HTML (TipTap) |
| meta_title | varchar(160) | SEO |
| meta_description | varchar(300) | SEO |
| sort | int | ordering |
| status | enum | `draft`, `publish` |

### `sliders`
Homepage banner slider.

| Column | Type | Notes |
|---|---|---|
| id | bigint PK | |
| image_path | varchar(500) | R2 key |
| title | varchar(200) | |
| caption | varchar(500) | |
| link_url | varchar(500) | optional CTA |
| sort | int | |
| is_active | boolean | |

### `newsline`
Short announcements (ticker).

| id, headline, link_url, starts_at, ends_at, is_active, sort |

### `reviews`
User-submitted reviews, moderated.

| id, name, rating(1-5), comment, is_published, submitted_at |

---

## File Libraries

### `pdfs`
| id | title | slug | description | file_path (R2) | file_size_kb | category | downloads_count | is_active |

### `study_material`
| id | title | slug | description | file_path | subject | is_active |

### `books`
| id | title | slug | author | description | cover_image_path | price | discount_price | stock | is_active |

### `exams`
| id | name | slug | description | exam_date | is_active |

---

## Subscribers

### `officer_subscribers`
| id | full_name | mobile | email | status (`subscribed`,`unverified`,`unsubscribed`) | otp | otp_expires_at | verified_at | unsubscribed_at | ip_address |

### `soldier_subscribers`
| id | first_name | last_name | mobile | email | status | otp | otp_expires_at | verified_at | unsubscribed_at | ip_address |

### `result_registrations`
Public exam-result registration form data.

| Column | Type |
|---|---|
| id | bigint PK |
| exam_id | bigint FK → exams |
| name | varchar(100) |
| mobile | varchar(20) |
| email | varchar(150) |
| roll_no | varchar(50) |
| zone | varchar(100) |
| submitted_at | timestamp |

---

## Orders (Books)

### `orders`
| Column | Type | Notes |
|---|---|---|
| id | bigint PK | |
| order_number | varchar(20) | unique, human-readable |
| full_name | varchar(150) | |
| mobile | varchar(20) | |
| email | varchar(150) | |
| shipping_address | text | |
| city | varchar(80) | |
| state | varchar(80) | |
| pincode | varchar(10) | |
| subtotal | decimal(10,2) | |
| discount | decimal(10,2) | |
| final_cost | decimal(10,2) | |
| status | enum | `pending`, `successful`, `rejected` |
| payment_id | varchar(100) | Razorpay payment_id |
| razorpay_order_id | varchar(100) | |
| consignment_number | varchar(100) | nullable (admin fills) |
| notes | text | |

### `order_items`
| id | order_id FK | book_id FK | quantity | unit_price | line_total |

---

## Supporting

### `settings`
Key-value site config (icon, site title, SMTP creds encrypted).

| id | key | value | type |

### `redirects`
Legacy URL → new URL (for SEO preservation after migration).

| id | from_path | to_path | status_code (301/302) |

### `activity_log`
Audit trail of admin actions.

| id | admin_id | action | subject_type | subject_id | ip | user_agent | created_at |

---

## ERD (text diagram)

```
admins ──┐
         │ (writes)
         ▼
      activity_log

pages ──(self-ref)── pages      (parent_id → id)

exams ───<──── result_registrations

books ───<──── order_items ────>── orders

officer_subscribers   (standalone)
soldier_subscribers   (standalone)

sliders, newsline, reviews, pdfs, study_material   (all standalone)

settings, redirects   (standalone)
```

---

## Index Strategy

- `pages.slug` — unique index
- `pages.parent_id` — index
- `orders.status` — index (filter heavy)
- `orders.order_number` — unique
- `*.status` on subscribers — index
- `result_registrations.zone` — index
- `activity_log.created_at` — index

## Storage Estimates (Year 1)

| Table | Est. rows | Size |
|---|---|---|
| pages | ~200 | <10 MB |
| orders | ~5,000 | ~15 MB |
| officer_subscribers | ~30,000 | ~20 MB |
| soldier_subscribers | ~50,000 | ~30 MB |
| result_registrations | ~100,000 | ~60 MB |
| activity_log | ~500,000 | ~200 MB |
| PDFs on R2 | ~200 files | ~5 GB |

Total DB ≈ 500 MB (comfortably fits any shared MySQL plan).
