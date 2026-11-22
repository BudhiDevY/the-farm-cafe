# the-farm-cafe
Online menu, table reservation, and live kitchen ordering portal for The Farm Cafe, Imphal.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Cafe Ordering, Kitchen & Booking System

A lightweight, full-stack cafe management web application built with **HTML, Tailwind CSS, Vanilla JavaScript, and Supabase**.

## Project Structure
- `index.html` — Customer-facing menu, live open/closed hours status, slide-out cart drawer, order checkout, and table reservation form.
- `admin.html` — PIN-protected staff portal with Counter routing, Kitchen Display View, Menu Manager, Bookings list, and DB-synced PIN settings.
- `MANUAL.md` — End-user operating guide for cafe owners and staff.

## Supabase Tables Required
1. `orders` (`id`, `created_at`, `status`, `service`, `customer_name`, `customer_phone`, `zone`, `items` [jsonb], `total`)
2. `bookings` (`id`, `created_at`, `name`, `phone`, `guests`, `date_time`)
3. `custom_menu_items` (`id`, `title`, `category`, `price`, `veg`, `tag`, `description`)
4. `admin_settings` (`id` [text PK], `pin` [text], `updated_at` [timestamptz])

## Pre-Production Checklist (When Client Approves)
1. Replace `SUPABASE_URL` and `SUPABASE_ANON_KEY` if deploying on a dedicated client Supabase project.
2. Upgrade `admin.html` from PIN gate to **Supabase Auth** (`signInWithPassword`) and enable **Row Level Security (RLS)** on all tables.
3. Update cafe branding, contact phone/WhatsApp number, Google Maps coordinates, and operating hours (`updateStatusBadge()`).
4. Connect the client's custom domain via DNS (`A` / `CNAME` records).

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
