# 🍽️ RestroPRO SaaS v1.8.0

A comprehensive multi-tenant restaurant management SaaS platform with real-time order tracking, QR menu ordering, inventory management, and analytics.

## 🚀 Features

- **Multi-tenant Architecture** - Fully isolated tenant data
- **Point of Sale (POS)** - Fast and intuitive order taking
- **Kitchen Display System** - Real-time order management for kitchen staff
- **QR Menu & Ordering** - Contactless menu viewing and self-ordering
- **Table Reservations** - Advanced booking system with unique codes
- **Inventory Management** - Track stock levels and movements
- **Customer Management** - Customer database with membership support
- **Feedback System** - Customer ratings and reviews
- **Reports & Analytics** - Comprehensive business insights
- **Multi-currency Support** - 100+ currencies with exchange rates
- **Multi-language** - Support for 7 languages (AR, EN, ES, FR, HI, JA, KO)
- **Subscription Billing** - Stripe integration for SaaS payments
- **Real-time Updates** - Socket.IO for live order notifications
- **Receipt Printing** - Customizable print templates
- **Role-based Access Control** - Granular permissions system

## 🏗️ Tech Stack

### Backend
- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MySQL
- **Real-time:** Socket.IO
- **Authentication:** JWT with refresh tokens
- **Payment:** Stripe
- **Email:** Nodemailer
- **File Upload:** express-fileupload
- **i18n:** i18n library

### Frontend
- **Framework:** React 18
- **Build Tool:** Vite
- **Styling:** Tailwind CSS + DaisyUI
- **State Management:** React Context + SWR
- **Routing:** React Router v6
- **HTTP Client:** Axios
- **Charts:** ApexCharts
- **Notifications:** React Hot Toast
- **i18n:** i18next
- **Real-time:** Socket.IO Client

## 📋 Prerequisites

- Node.js (v14 or higher)
- MySQL (v8.0 or higher)
- npm or yarn
- Git

## 🔧 Installation

### 1. Clone the Repository

```bash
git clone <repository-url>
cd code
```

### 2. Database Setup

```bash
# Create a new MySQL database
mysql -u root -p

# In MySQL prompt:
CREATE DATABASE restropro_saas;
exit;

# Import the database schema
mysql -u root -p restropro_saas < restropro_saas.sql
```

### 3. Backend Setup

```bash
cd restropro-saas-backend-1.8.0

# Install dependencies
npm install

# Copy environment file
cp .env.example .env

# Edit .env with your configuration
# Required variables:
# - DATABASE_URL
# - JWT_SECRET
# - FRONTEND_DOMAIN
# - STRIPE_SECRET (if using subscriptions)
# - SMTP credentials (if using email)

# Start development server
npm run dev

# Or start production server
npm start
```

Backend will run on `http://localhost:3000`

### 4. Frontend Setup

```bash
cd ../restropro-saas-frontend-main

# Install dependencies
npm install

# Copy environment file
cp .env .env.local

# Edit .env.local with your configuration
# Set VITE_API_URL to your backend URL

# Start development server
npm run dev

# Or build for production
npm run build
```

Frontend will run on `http://localhost:5173`

## 🌐 Environment Variables

### Backend (.env)

```env
DATABASE_URL="mysql://username:password@localhost:3306/restropro_saas"
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRY=15m
JWT_EXPIRY_REFRESH=30d
COOKIE_EXPIRY=900000
COOKIE_EXPIRY_REFRESH=2592000000
PASSWORD_SALT=10
FRONTEND_DOMAIN="http://localhost:5173"
FRONTEND_DOMAIN_COOKIE="localhost"

# Stripe (optional)
STRIPE_SECRET=sk_test_...
STRIPE_WEBHOOK_SECRET=whsec_...

# Email (optional)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_EMAIL=your-email@gmail.com
SMTP_PASSWORD=your-app-password

ENCRYPTION_KEY=your_encryption_key
```

### Frontend (.env)

```env
VITE_API_URL=http://localhost:3000
VITE_SOCKET_URL=http://localhost:3000
```

## 📱 API Endpoints

Base URL: `http://localhost:3000/api/v1`

- `/auth` - Authentication & registration
- `/settings` - Store & system settings
- `/customers` - Customer management
- `/reservations` - Table reservations
- `/users` - User management
- `/menu-items` - Menu CRUD operations
- `/pos` - Point of sale
- `/kitchen` - Kitchen display system
- `/orders` - Order management
- `/invoices` - Billing
- `/dashboard` - Analytics
- `/reports` - Reporting
- `/qrmenu` - QR menu & ordering
- `/feedback` - Customer feedback
- `/superadmin` - Platform administration
- `/inventory` - Inventory management

## 👥 Default Roles

- **Super Admin** - Platform administrator
- **Admin** - Restaurant administrator (full access)
- **User** - Staff member (limited access based on scopes)

## 🔐 Security

- JWT-based authentication
- Refresh token rotation
- bcrypt password hashing
- Multi-tenant data isolation
- CORS protection
- Rate limiting support
- Scope-based permissions

## 🌍 Supported Languages

- Arabic (ar)
- English (en)
- Spanish (es)
- French (fr)
- Hindi (hi)
- Japanese (ja)
- Korean (ko)

## 📊 Database Schema

The application uses a multi-tenant MySQL database with 24+ tables including:

- `tenants` - Tenant/restaurant information
- `users` - Staff accounts
- `customers` - Customer database
- `menu_items` - Menu with variants and addons
- `orders` - Order management
- `invoices` - Billing records
- `reservations` - Table bookings
- `feedbacks` - Customer reviews
- `inventory` - Stock management
- And more...

## 🚀 Deployment

### Backend Deployment

1. Set `NODE_ENV=production`
2. Update `.env` with production values
3. Run `npm start`
4. Configure reverse proxy (nginx/Apache)
5. Set up SSL certificate

### Frontend Deployment

1. Update `.env.production` with production API URL
2. Run `npm run build`
3. Deploy `dist` folder to hosting service
4. Configure web server to serve SPA

### Docker Support

Dockerfile is included for containerized deployment.

## 📝 License

Proprietary - All rights reserved

## 🤝 Support

For support and inquiries, please contact the development team.

## 🔄 Version History

- **v1.8.0** - Current version
  - Added inventory management
  - Enhanced feedback system
  - Improved multi-language support
  - Performance optimizations

---

**Built with ❤️ for modern restaurants**
