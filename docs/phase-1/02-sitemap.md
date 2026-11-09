# Phase 1 — Sitemap & URL Structure

## Public Website

```
/                                   Homepage (slider, newsline, highlights)
├── /join-as-jawan                   Static info page (admin-editable)
├── /join-as-officer                 Static info page (admin-editable)
│   ├── /join-as-officer/civilians   Child page
│   ├── /join-as-officer/ex-service  Child page
│   └── /join-as-officer/syllabus    Child page
├── /pages/{slug}                    Any dynamic page admin creates
├── /pdfs                            PDF library listing
│   └── /pdfs/{slug}                 Individual PDF detail / download
├── /study-material                  Study material listing
│   └── /study-material/{slug}       Individual item
├── /books                           Books catalog
│   ├── /books/{slug}                Book detail + Buy button
│   ├── /cart                        Cart
│   ├── /checkout                    Checkout (address + payment)
│   └── /order/{order_id}            Order confirmation
├── /exams                           Exam list
│   └── /exams/{slug}/register       Exam result registration form
├── /subscribe/officer               Officer subscription + OTP flow
├── /subscribe/soldier               Soldier subscription + OTP flow
├── /verify-otp                      OTP verification page
├── /unsubscribe/{token}             One-click unsubscribe
├── /reviews                         Public reviews page
├── /newsline                        All announcements
├── /about                           About page
├── /contact                         Contact form
├── /privacy                         Privacy policy
├── /terms                           Terms & conditions
├── /sitemap.xml                     SEO sitemap (auto-generated)
└── /robots.txt                      Crawler rules
```

## Admin Panel

```
/admin/login                         Login screen
/admin                               Dashboard (counts: orders today, new subscribers)
/admin/orders                        Orders table
├── /admin/orders/pending
├── /admin/orders/successful
├── /admin/orders/rejected
└── /admin/orders/{id}               Order detail + status change
/admin/pages                         Pages list
├── /admin/pages/create
└── /admin/pages/{id}/edit
/admin/registrations                 Exam result registrations
├── /admin/registrations/create
└── /admin/registrations/export
/admin/officer-subscribers           Officer subscribers
├── /admin/officer-subscribers/verified
├── /admin/officer-subscribers/unverified
└── /admin/officer-subscribers/unsubscribed
/admin/soldier-subscribers           Soldier subscribers (same sub-routes)
/admin/pdfs                          PDFs CRUD
/admin/study-material                Study material CRUD
/admin/books                         Books CRUD
/admin/exams                         Exam names master
/admin/sliders                       Homepage slider
/admin/newsline                      Announcements
/admin/reviews                       Review moderation
/admin/settings                      Icon settings, site title
/admin/change-password
/admin/logout
```

---

## URL Conventions

- All URLs are **lowercase**, words joined with hyphens
- Slugs are **auto-generated** from the Title field, editable by admin
- Admin can set a custom `menu_name` (what appears in the top nav) independent of the page title
- Child pages inherit parent URL: `/parent/child` structure
- Legacy URLs from old site will 301-redirect to new equivalents

## Navigation Rules

- **Top nav** shows only pages where `parent_id = null`
- Hovering a parent reveals its children in a dropdown
- Admin can set menu display order (`sort` column)
- Pages with `status = draft` are accessible by direct URL only (for preview) and hidden from nav
