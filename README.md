# 🎟️ Event Booking & Management REST API

A production-ready RESTful API built using ASP.NET Core that enables users to register, browse events, and book tickets securely. Designed with real-world backend architecture principles including authentication, transaction handling, and clean separation of concerns.

---

## 🚀 Features

- 🔐 JWT-based Authentication & Authorization
- 👤 Role-based Access Control (Admin / User)
- 🎫 Event Creation & Ticket Booking System
- 🔁 Booking Cancellation Support
- 💾 SQL Server with Normalized Schema
- ⚙️ Stored Procedures for Transaction Safety
- 🧠 Dependency Injection for Scalable Architecture
- 🛡️ Global Exception Handling Middleware
- 📊 Structured Logging for Debugging & Monitoring

---

## 🛠️ Tech Stack

- **Backend:** ASP.NET Core Web API
- **Language:** C#
- **Database:** SQL Server
- **Authentication:** JWT (JSON Web Tokens)
- **Architecture:** Layered (Controller → Service → Repository)
- **Tools:** Visual Studio / Postman

---

## 📂 Database Design

The system uses a normalized relational schema:

- **Users** – Stores user credentials and roles  
- **Events** – Stores event details created by Admin  
- **Bookings** – Tracks ticket reservations  
- **AuditLog** – Logs all critical operations  

---

## 🔐 Authentication & Authorization

- Users must register and log in to receive a JWT token  
- Token is required for accessing protected endpoints  
- Role-based restrictions:
  - **Admin:** Create/Delete events
  - **User:** Book/Cancel tickets  

---

## 🔄 Booking Transaction Logic

Booking operations are handled using **SQL Stored Procedures** to ensure:

- Atomic transactions (commit / rollback)
- No overbooking issues
- Data consistency under concurrent requests

---

## ⚠️ Error Handling

- Centralized **Global Exception Middleware**
- Returns clean and meaningful HTTP responses:
  - `200 OK`
  - `201 Created`
  - `400 Bad Request`
  - `401 Unauthorized`
  - `403 Forbidden`
  - `404 Not Found`

---

## 🧪 API Endpoints (Sample)

| Method | Endpoint | Description |
|--------|--------|-------------|
| POST | /api/auth/register | Register new user |
| POST | /api/auth/login | Login & get JWT |
| GET | /api/events | Get all events |
| POST | /api/events | Create event (Admin) |
| POST | /api/bookings | Book ticket |
| DELETE | /api/bookings/{id} | Cancel booking |

---

## ▶️ How to Run Locally

```bash
# Clone the repository
git clone https://github.com/your-username/event-booking-api.git

# Navigate to project
cd event-booking-api

# Update connection string in appsettings.json

# Run the application
dotnet run
