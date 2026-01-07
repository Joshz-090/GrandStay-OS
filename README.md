h
----

# 🏨 GrandStay OS  
### The Universal SaaS Hotel Management Engine

**GrandStay OS** is a scalable, multi-tenant **SaaS Hotel Management Platform** designed to power multiple hotels from a **single centralized codebase**.

The platform enables:
- A **Super Admin** to manage hotel onboarding, subscriptions, and system-wide control.
- **Hotel Managers** to operate fully branded, isolated hotel portals with their own data, staff, and bookings.

Built with enterprise-grade architecture, GrandStay OS is designed for **security, scalability, and customization**.

---

## 🚀 Core Features

- **Multi-Tenant Architecture**  
  Schema-based isolation using PostgreSQL to ensure strong data separation between hotels.

- **Dynamic Branding Engine**  
  Hotel-specific logo, name, and theme are injected dynamically at runtime.

- **Automated Subscription Kill-Switch**  
  Middleware blocks all access instantly when a hotel’s subscription expires.

- **Super Admin Dashboard (God Mode)**  
  Central control to create hotels, manage subscriptions, and monitor system health.

- **Hotel Operations Management**  
  Full CRUD for:
  - Rooms & Room Types  
  - Staff & Roles  
  - Bookings & Guests  

---

## 🛠 Tech Stack

| Layer | Technology | Purpose |
|------|-----------|---------|
| Backend | Python · Django · DRF | Business logic, APIs, tenant control |
| Frontend | Vue 3 · Vite · Pinia | Reactive dashboards & dynamic UI |
| Database | PostgreSQL | Schema-based tenant isolation |
| Multi-Tenancy | django-tenants | Subdomain → schema routing |
| File Storage | Cloudinary / AWS S3 | Logos, hotel images, media |

---

## 👥 Team Structure

This project is built by **two software engineers**, following a clear separation of concerns.

### 👨‍💻 Engineer 1 — Backend & Infrastructure
- Configure Django + `django-tenants`
- Design public & tenant database schemas
- Implement subscription **Kill-Switch Middleware**
- Build REST APIs (Auth, Rooms, Bookings)
- Handle migrations & database management

### 🎨 Engineer 2 — Frontend & UX/UI
- Initialize Vue 3 + Pinia architecture
- Build Dynamic Branding System
- Integrate backend APIs
- Implement role-based routing & protected views
- Design responsive hotel dashboards

---

## 🏗 System Architecture (Multi-Tenant Logic)

GrandStay OS uses **PostgreSQL schema-based isolation**.

### Schemas
- **Public Schema**
  - Hotels (Tenants)
  - Subscriptions & Billing
  - Super Admin Accounts

- **Tenant Schemas**
  - Guests
  - Rooms
  - Bookings
  - Staff

Each hotel operates in a **fully isolated schema** while sharing the same codebase.

---

## 🔐 Subscription Kill-Switch (Core Security Feature)

Every incoming request is intercepted by a custom Django middleware:

```python
if request.tenant.subscription_status == "EXPIRED":
    raise PermissionDenied("Access Revoked: Subscription Required")
This guarantees:

Zero access after expiration

No frontend bypass

Full backend enforcement

⚙️ Setup & Installation
Backend (Django)
bash
Copy code
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py migrate_schemas --shared
python manage.py runserver
Frontend (Vue 3)
bash
Copy code
cd frontend
npm install
npm run dev
📈 Roadmap
 Multi-Tenant Schema Configuration

 Dynamic Branding Engine

 Super Admin (God Mode) Dashboard

 Subscription Lock-Out Middleware

 Booking, Billing & Invoice Engine

❤️ Credits
Developed with passion by the GrandStay OS Team
Built for scalability, security, and real-world SaaS deployment.

yaml
Copy code

---

If you want, next I can:
- Generate **public schema models.py**
- Create a **production-grade folder structure**
- Write a **killer GitHub project description**
- Prepare a **Pitch Deck / Architecture Diagram**

Just say the word 🚀
