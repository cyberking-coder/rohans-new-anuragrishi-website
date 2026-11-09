# Phase 1 — Brand & Design System

Design tokens the frontend and admin panel will share. Finalized with client in Phase 1.

---

## Color Palette

Matching the current admin's purple accent while keeping public site professional and military-appropriate.

### Primary

| Token | Hex | Use |
|---|---|---|
| `primary-900` | `#4C1D95` | Headings, deep accents |
| `primary-700` | `#6B21A8` | **Main brand purple** (admin header, buttons) |
| `primary-500` | `#A855F7` | Hover, highlights |
| `primary-100` | `#F5F3FF` | Backgrounds, cards |

### Neutral

| Token | Hex | Use |
|---|---|---|
| `gray-900` | `#111827` | Primary text |
| `gray-700` | `#374151` | Secondary text |
| `gray-500` | `#6B7280` | Muted text |
| `gray-200` | `#E5E7EB` | Borders |
| `gray-100` | `#F3F4F6` | Striped rows |
| `white` | `#FFFFFF` | Card background |

### Semantic

| Token | Hex | Use |
|---|---|---|
| `success` | `#10B981` | "Successful" badges, confirm buttons |
| `warning` | `#F59E0B` | "Pending" badges, edit buttons |
| `danger` | `#EF4444` | "Rejected" badges, delete buttons |
| `info` | `#3B82F6` | View buttons, info tags |

### Patriotic Accents (used sparingly, home page hero)

| Token | Hex |
|---|---|
| `tricolor-saffron` | `#FF9933` |
| `tricolor-white` | `#FFFFFF` |
| `tricolor-green` | `#138808` |
| `tricolor-blue` | `#000080` (Ashoka Chakra) |

---

## Typography

### Public Site

- **Headings:** `Poppins`, 600/700 weight
- **Body:** `Inter`, 400/500 weight
- **Fallback stack:** `-apple-system, Segoe UI, Roboto, sans-serif`

### Admin Panel

- **System stack:** `-apple-system, Segoe UI, Roboto, sans-serif` (snappy, no web-font load)

### Scale

| Role | Size | Weight | Line-height |
|---|---|---|---|
| H1 | 36px / 2.25rem | 700 | 1.2 |
| H2 | 28px / 1.75rem | 700 | 1.25 |
| H3 | 22px / 1.375rem | 600 | 1.3 |
| H4 | 18px / 1.125rem | 600 | 1.4 |
| Body | 16px / 1rem | 400 | 1.6 |
| Small | 14px / 0.875rem | 400 | 1.5 |
| Caption | 12px / 0.75rem | 500 | 1.4 |

---

## Spacing (4px grid)

`4, 8, 12, 16, 24, 32, 48, 64, 96` — Tailwind's default scale.

## Border Radius

| Role | Value |
|---|---|
| Buttons, inputs | `8px` (rounded-lg) |
| Cards | `12px` (rounded-xl) |
| Avatars | `9999px` (rounded-full) |

## Shadows

| Token | Value |
|---|---|
| `shadow-sm` | `0 1px 2px rgba(0,0,0,0.05)` |
| `shadow-md` | `0 4px 6px -1px rgba(0,0,0,0.1)` |
| `shadow-lg` | `0 10px 15px -3px rgba(0,0,0,0.1)` |

---

## Component Patterns

### Buttons

```
Primary:   bg-primary-700 text-white hover:bg-primary-900
Secondary: bg-white text-primary-700 border border-primary-700
Danger:    bg-danger text-white
Ghost:     text-gray-700 hover:bg-gray-100
```

All buttons: `px-4 py-2 rounded-lg font-medium transition-colors`

### Status Badges

```
pending     → amber chip  (bg-amber-100 text-amber-800)
successful  → green chip  (bg-green-100 text-green-800)
rejected    → red chip    (bg-red-100 text-red-800)
publish     → green chip
draft       → gray chip
```

### Form Inputs

- Height: 40px
- Border: 1px solid gray-200, focus:primary-500
- Error state: border-danger + helper text below
- Label above field (sentence case)

---

## Responsive Breakpoints

| Name | Width |
|---|---|
| `sm` | 640px |
| `md` | 768px |
| `lg` | 1024px |
| `xl` | 1280px |
| `2xl` | 1536px |

Mobile-first. Public site layouts collapse single-column below `md`; admin sidebar collapses below `lg`.

---

## Accessibility Targets

- WCAG 2.1 AA minimum
- Color contrast ≥ 4.5:1 for body text, ≥ 3:1 for large text
- All interactive elements keyboard-reachable
- Focus ring: 2px primary-500
- Images have alt text
- Forms have label associations
- Error messages announced to screen readers

---

## Logo Usage

- Minimum size: 32px height (web), 24px (mobile nav)
- Clear space: equal to logo height on all sides
- Never recolor, stretch, or add shadow to logo
- Light background: use full-color logo
- Dark background (admin header): use white logo

---

## Deliverables at End of Phase 1

- [x] Scope document (01-scope.md)
- [x] Sitemap & URL structure (02-sitemap.md)
- [x] Database schema / ERD (03-database-schema.md)
- [x] Wireframes (04-wireframes.md)
- [x] Brand & design system (05-brand-design.md)
- [ ] **Client sign-off on all five** → unlocks Phase 2
