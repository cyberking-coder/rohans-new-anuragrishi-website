# Phase 1 — Wireframes (Low-Fidelity)

ASCII wireframes for client review. High-fidelity designs come in Phase 2.

---

## Public Homepage

```
┌────────────────────────────────────────────────────────────┐
│ [LOGO]    Home  Join-as-Jawan  Join-as-Officer ▼  Books ▼ │
│                                 PDFs  Exams  Contact       │
├────────────────────────────────────────────────────────────┤
│                                                            │
│   ┌──────────────────────────────────────────────────┐    │
│   │          HERO SLIDER (admin controls)            │    │
│   │   « [image + headline + CTA button]       »     │    │
│   │               ● ● ○ ○ ○                          │    │
│   └──────────────────────────────────────────────────┘    │
│                                                            │
│   📢 Newsline:  ● New exam date announced  ●  ...          │
│                                                            │
│   ┌──────────┬──────────┬──────────┬──────────┐          │
│   │ Join as  │ Join as  │ Download │ Register │          │
│   │ Jawan    │ Officer  │ PDFs     │ for Exam │          │
│   └──────────┴──────────┴──────────┴──────────┘          │
│                                                            │
│   LATEST BOOKS                                             │
│   ┌────┬────┬────┬────┐                                   │
│   │book│book│book│book│   [View all →]                    │
│   └────┴────┴────┴────┘                                   │
│                                                            │
│   WHAT OUR SUBSCRIBERS SAY                                 │
│   ⭐⭐⭐⭐⭐ "Great platform..."  — Avinash P.              │
│                                                            │
├────────────────────────────────────────────────────────────┤
│ Footer: About · Contact · Privacy · Terms · © 2026        │
└────────────────────────────────────────────────────────────┘
```

---

## Dynamic Page (e.g. /join-as-jawan)

```
┌────────────────────────────────────────────────────────────┐
│ [Header + Nav]                                             │
├────────────────────────────────────────────────────────────┤
│                                                            │
│   JOIN AS A JAWAN / JCO                                    │
│   ──────────────────────                                   │
│                                                            │
│   Eligibility                                              │
│   Age: 18 to 42 years                                      │
│   Education: Matriculation...                              │
│                                                            │
│   Process                                                  │
│   Applicant to report to the unit or the recruitment...    │
│                                                            │
│   [ Subscribe for updates ]  [ Download PDF ]              │
│                                                            │
│   Related Pages:                                           │
│   • For Civilians Candidates                               │
│   • For Ex-Service Officer                                 │
│   • Syllabus                                               │
│                                                            │
├────────────────────────────────────────────────────────────┤
│ [Footer]                                                   │
└────────────────────────────────────────────────────────────┘
```

---

## Books Catalog

```
┌──────────────────────────────────────────────────────┐
│ BOOKS                                                 │
│                                                       │
│ [Search ______] [Sort: Newest ▼]                     │
│                                                       │
│ ┌────┐  ┌────┐  ┌────┐  ┌────┐                      │
│ │ 📕 │  │ 📘 │  │ 📗 │  │ 📙 │                      │
│ │Edn │  │Edn │  │Edn │  │Edn │                      │
│ │₹1499│ │₹999 │ │₹1299│ │₹899 │                     │
│ │[Buy]│  │[Buy]│  │[Buy]│  │[Buy]│                   │
│ └────┘  └────┘  └────┘  └────┘                      │
│                                                       │
│   « 1 2 3 »                                          │
└──────────────────────────────────────────────────────┘
```

---

## Book Detail + Buy Flow

```
┌──────────────────────────────────────────────────────┐
│ ← Back                                                │
│                                                       │
│   ┌────────┐   Territorial Army Exam Guide           │
│   │        │   Edition 2026                           │
│   │ cover  │   ⭐⭐⭐⭐⭐ (23 reviews)                    │
│   │        │                                          │
│   │        │   ₹999  ₹1,499 (33% off)                │
│   └────────┘                                          │
│                                                       │
│   Description:                                        │
│   Comprehensive preparation guide covering...         │
│                                                       │
│   [  Buy Now →  ]      [  Add to Cart  ]             │
└──────────────────────────────────────────────────────┘
```

## Checkout

```
┌──────────────────────────────────────────────────────┐
│ CHECKOUT                                              │
│                                                       │
│ Full name   [________________]                       │
│ Mobile      [________________]                       │
│ Email       [________________]                       │
│ Address     [________________]                       │
│             [________________]                       │
│ City        [______] State [____] Pincode [______]  │
│                                                       │
│ ─────────────────────────────                        │
│ Subtotal:        ₹999                                │
│ Shipping:        ₹0                                  │
│ TOTAL:           ₹999                                │
│                                                       │
│ [  Pay with Razorpay →  ]                            │
└──────────────────────────────────────────────────────┘
```

---

## Officer Subscription (public)

```
┌──────────────────────────────────────────────────────┐
│ SUBSCRIBE AS OFFICER                                  │
│                                                       │
│ Full name    [________________]                      │
│ Mobile       [________________]                      │
│ Email        [________________]                      │
│                                                       │
│ [  Send OTP  ]                                       │
│                                                       │
│ After verification, you'll receive updates on new    │
│ exam dates, syllabus changes, and study material.    │
└──────────────────────────────────────────────────────┘
```

---

## Admin Dashboard

```
┌──────────────┬───────────────────────────────────────┐
│              │  Welcome, reet                    👤  │
│  🏠 Dashboard├───────────────────────────────────────┤
│  📦 Orders   │                                       │
│  📄 Pages    │  ┌─────────┬─────────┬─────────┐    │
│  📝 Results  │  │ Orders  │ Pending │ New sub │    │
│  👔 Officers │  │  today  │ orders  │ today   │    │
│  🎖  Soldiers│  │   12    │    3    │   47    │    │
│  📂 PDFs     │  └─────────┴─────────┴─────────┘    │
│  📚 Books    │                                       │
│  📝 Study    │  Recent Orders                        │
│  🎓 Exams    │  ┌──────────────────────────────┐   │
│  🖼  Slider  │  │ #3145728  Kankipati Ajay ...│   │
│  📣 News     │  │ #8062208  Rajul Kumar  ... │   │
│  ⭐ Reviews  │  └──────────────────────────────┘   │
│  ⚙  Settings│                                       │
└──────────────┴───────────────────────────────────────┘
```

## Admin — Orders List

```
Orders > Successful Orders
                [Download Excel] [Pending] [Successful] [Rejected]
┌───────────────────────────────────────────────────────────────┐
│ Search: [order no] [mobile] [name]      [Search]              │
│                                                                │
│ # │ Order #  │ Name       │ Mobile    │ Status   │ Actions    │
│ 1 │ 3145728  │ A. Kumar   │ 90143...  │ ✓ SUCC   │[edit][ship]│
│ 2 │ 8062208  │ R. Kumar   │ 99557...  │ ✓ SUCC   │[edit][ship]│
│                                                                │
│ « 1 2 3 ... 16 »                                              │
└───────────────────────────────────────────────────────────────┘
```

## Admin — Pages List

```
Pages                                       [+ Add page]
┌───────────────────────────────────────────────────────┐
│ Search: [page name]  [Search]                         │
│                                                        │
│ Title            │ Parent    │ Menu       │ Status  │ │
│ Join as Jawan    │ Home      │ Jawan/JCO  │ Publish │ │
│ Join as Officer  │ —         │ Officer    │ Publish │ │
│  └ For Civilians │ Officer   │ Civilians  │ Publish │ │
│  └ Syllabus      │ Officer   │ Syllabus   │ Publish │ │
│                                                        │
│ [View] [Edit] [Delete]                                │
└───────────────────────────────────────────────────────┘
```

---

## Notes

- Purple header + dark sidebar — matches current admin look client approved
- All data tables support: search, filter, sort, pagination, Excel export
- All forms use inline validation (no page reload)
- Mobile admin: sidebar collapses to hamburger
