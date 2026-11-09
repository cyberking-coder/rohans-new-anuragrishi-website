# Phase 2 — Backend Foundation

**Duration:** Week 2
**Status:** Scaffolded — ready for `composer install` and `php artisan migrate`

## What's in this phase

Everything a developer needs to boot the Laravel + Filament backend with the database structure matching Phase 1's schema.

### Files created

```
composer.json                            # Laravel 11 + Filament v3 + Razorpay + Excel + R2
.env.example                             # DB, mail, R2, Razorpay, admin seed vars
.gitignore
config/
  ├── auth.php                           # Admin guard (not User guard)
  └── filesystems.php                    # Local + public + Cloudflare R2 disks
database/
  ├── migrations/
  │   ├── ...000001_create_admins_table.php
  │   ├── ...000002_create_pages_table.php
  │   ├── ...000003_create_sliders_table.php
  │   ├── ...000004_create_newsline_table.php
  │   ├── ...000005_create_reviews_table.php
  │   ├── ...000006_create_pdfs_table.php
  │   ├── ...000007_create_study_material_table.php
  │   ├── ...000008_create_books_table.php
  │   ├── ...000009_create_exams_table.php
  │   ├── ...000010_create_officer_subscribers_table.php
  │   ├── ...000011_create_soldier_subscribers_table.php
  │   ├── ...000012_create_result_registrations_table.php
  │   ├── ...000013_create_orders_table.php         (+ order_items)
  │   ├── ...000014_create_settings_table.php       (+ redirects)
  │   └── ...000015_create_activity_log_table.php   (+ jobs, cache)
  └── seeders/DatabaseSeeder.php         # Seeds super admin + default settings
app/
  ├── Models/
  │   ├── Admin.php                      # implements FilamentUser
  │   ├── Page.php                       # self-referencing parent/children
  │   ├── Slider.php
  │   ├── Newsline.php
  │   ├── Review.php
  │   ├── Pdf.php
  │   ├── StudyMaterial.php
  │   ├── Book.php                       # effective_price accessor
  │   ├── Exam.php                       # hasMany registrations
  │   ├── OfficerSubscriber.php          # scopes: verified / unverified / unsubscribed
  │   ├── SoldierSubscriber.php          # same scopes + full_name accessor
  │   ├── ResultRegistration.php
  │   ├── Order.php                      # auto order_number, markSuccessful/markRejected
  │   ├── OrderItem.php
  │   ├── Setting.php                    # cached get/set helpers
  │   ├── Redirect.php
  │   └── ActivityLog.php
  └── Providers/Filament/
      └── AdminPanelProvider.php         # purple theme, admin guard, /admin path
routes/web.php                           # Home + legacy redirect fallback
resources/views/public/home.blade.php    # placeholder (Phase 4 replaces)
```

## Phase 2 checklist

- [x] Laravel 11 composer.json
- [x] `.env.example` with all required keys
- [x] All 15 migrations
- [x] All 17 Eloquent models (incl. OrderItem, Setting, Redirect, ActivityLog)
- [x] Filament v3 admin panel provider (purple theme at `/admin`)
- [x] Admin auth config
- [x] Cloudflare R2 disk config
- [x] Super-admin + default settings seeder
- [x] Placeholder home view
- [ ] `composer install` run on dev machine
- [ ] `php artisan migrate --seed` run
- [ ] First admin login at `/admin` verified

## Run on local / dev server

```bash
# 1. Install dependencies
composer install

# 2. Copy env + generate key
cp .env.example .env
php artisan key:generate

# 3. Create the MySQL database
mysql -u root -e "CREATE DATABASE territorial_army CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;"

# 4. Edit .env with your DB credentials + admin seed vars

# 5. Run migrations and seed
php artisan migrate --seed

# 6. Install Filament panel assets
php artisan filament:install --panels
php artisan filament:assets

# 7. Serve
php artisan serve
```

Open <http://localhost:8000/admin> and log in with the credentials you set in `.env` (`ADMIN_EMAIL` / `ADMIN_PASSWORD`).

## What Phase 2 does NOT include (comes in Phase 3)

- Filament **Resource** classes for the 11 admin modules (Orders, Pages, Subscribers, PDFs, etc.) — the panel will load but show no modules yet, only auth + dashboard.
- Public-site frontend views (comes in Phase 4).
- Razorpay integration (Phase 5).
- Email / OTP (Phase 6).

## Next (Phase 3 — Admin Panel Core Modules, Weeks 3–4)

Build Filament resources for every table:
- OrderResource, PageResource, SliderResource, NewslineResource, ReviewResource
- PdfResource, StudyMaterialResource, BookResource, ExamResource
- OfficerSubscriberResource, SoldierSubscriberResource, ResultRegistrationResource

Each with: table columns, filters, search, Excel export action, create/edit forms, and status badges matching the design system from Phase 1.
