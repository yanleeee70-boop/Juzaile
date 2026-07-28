# Juzaile Business Book - PRD

## Original Problem Statement
Build an app called "Juzaile Business Book" - an inventory management system that can count the stock of more than 500+ items sold. Simple, professional, and efficient design.

## User Personas
- **Business Owner**: Tracks entire inventory, exports data, manages suppliers
- **Staff Member**: Adds/updates stock, records movements, checks low stock alerts

## Core Requirements
- Multi-user authentication with login/registration
- Manage 500+ inventory items with categories
- Stock in/out tracking with history
- Low stock alerts
- Barcode/SKU support
- Supplier information management
- Search and advanced filtering
- Export data (CSV)

## Architecture
- **Backend**: FastAPI + MongoDB with JWT auth (httpOnly cookies)
- **Frontend**: React + Shadcn UI + Tailwind
- **Design**: Swiss & High-Contrast, Chivo/IBM Plex Sans fonts, Deep Emerald (#046A38) primary

## What's Been Implemented (Feb 2026)

### Authentication
- User registration and login with JWT
- Admin seeding (admin@juzaile.com / admin123)
- Brute force protection (5 attempts, 15 min lockout)
- Password reset flow

### Backend API (all under /api)
- `/auth/*` - register, login, logout, me, refresh, forgot-password, reset-password
- `/categories` - Full CRUD
- `/suppliers` - Full CRUD with contact info
- `/items` - Full CRUD with search, category filter, low stock filter
- `/stock-movements` - Create/list with auto quantity update
- `/dashboard/stats` - Aggregated stats
- `/export/items` - CSV export

### Frontend Pages
- Login page (split layout with warehouse image)
- Register page
- Dashboard (stats cards + recent activities)
- Inventory (table with search, filters, add/edit/delete, stock movements)
- Categories (grid view with CRUD)
- Suppliers (card view with full contact info)
- Stock History (timeline of all movements)

## Backlog (P0/P1/P2)
- **P1**: Reports/analytics page with charts
- **P1**: PDF export in addition to CSV
- **P1**: Bulk import items via CSV upload
- **P2**: Barcode scanner integration (camera-based)
- **P2**: Multi-warehouse/location support
- **P2**: Email notifications for low stock alerts
- **P2**: Purchase orders workflow

## Test Credentials
See /app/memory/test_credentials.md
