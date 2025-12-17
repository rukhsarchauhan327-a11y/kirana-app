# Kirana Konnect

## Overview

Kirana Konnect is a store management system designed for Indian kirana (grocery) stores. It provides inventory management, billing, customer credit tracking, sales reporting, and staff attendance features. The application is built as a Flask web application with a mobile-first responsive design using Tailwind CSS.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Backend Framework
- **Flask** serves as the web framework, handling routing, API endpoints, and template rendering
- **Flask-SQLAlchemy** provides ORM capabilities for database operations
- Database connection uses PostgreSQL (configured via `DATABASE_URL` environment variable)
- **ReportLab** generates PDF receipts and reports

### Frontend Architecture
- Server-rendered HTML templates using Jinja2 templating
- **Tailwind CSS** (loaded via standalone JS file) for styling with custom color theme
- **Font Awesome** for icons (loaded locally from static files)
- Mobile-first responsive design optimized for store counter use
- **ZXing library** for barcode scanning functionality
- **Chart.js** for sales analytics and reporting visualizations
- **html2pdf.js** for client-side PDF generation

### Data Models
The application uses SQLAlchemy models including:
- **Customer** - stores customer info (name, phone, address, Aadhar number, email) with relationships to bills and payments
- **Bill** - tracks sales transactions linked to customers
- **Payment** - records payment history for credit management
- Products support both unit-based and weight-based pricing

### Key Features
- **Dashboard** - overview of store metrics and quick actions
- **Inventory Management** - product tracking with barcode scanning, low stock alerts, expiry tracking
- **Billing System** - cart-based checkout with customer selection
- **Customer Credit/Ledger** - tracks pending payments and customer balances
- **Sales Reports** - analytics with charts and PDF export
- **Staff Attendance** - employee tracking
- **Notifications** - alerts for low stock, expiring products

### Design Patterns
- Template inheritance for consistent page layouts
- RESTful API endpoints returning JSON for dynamic updates
- Session-based state management
- Environment-based configuration for secrets and database URLs

## External Dependencies

### Database
- **PostgreSQL** - primary database (connection via `DATABASE_URL` environment variable)
- Connection pooling configured with 300-second recycle and pre-ping enabled

### Frontend Libraries (Self-hosted)
- Tailwind CSS (standalone build in `/static/js/tailwind.js`)
- Font Awesome 6.4.0 (CSS and fonts in `/static/css/` and `/static/fonts/`)
- ZXing barcode scanner library
- Chart.js (CDN for sales reports)
- html2pdf.js for receipt generation

### Python Dependencies
- Flask and Flask-SQLAlchemy for web framework and ORM
- ReportLab for server-side PDF generation
- psycopg2 (implied for PostgreSQL connectivity)

### Environment Variables
- `DATABASE_URL` - PostgreSQL connection string
- `SESSION_SECRET` - Flask session encryption key