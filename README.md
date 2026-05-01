# Laravel Conference Manager

A multi-role conference management web application built with Laravel 12. Users can register for conferences as clients, employees can view scheduled events, and admins have full control over conferences and users.

## Tech Stack

| Layer | Technology |
|-------|------------|
| Backend | Laravel 12, PHP 8.2 |
| Frontend | Blade templates, Vite |
| Database | SQLite (dev) / MySQL |
| Auth | Custom session-based auth + role middleware |

## Features

**Admin**
- Full CRUD for conferences (create, edit, delete)
- View and edit user accounts
- Dashboard overview

**Client**
- Browse available conferences
- View conference details
- Register/sign up for a conference

**Employee**
- Browse and view scheduled conferences

## Architecture

- Role-based access control via custom `role:` middleware
- Namespaced controllers per subsystem (`Admin/`, `Client/`, `Employee/`)
- Service layer (`app/Services/`) for business logic
- Form Request classes for validation
- Pivot tables for many-to-many: `users_roles`, `users_conferences`

## Getting Started

```bash
cd my_app
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate --seed
npm install && npm run dev
php artisan serve
