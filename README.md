# 🏦 SmartBank – Modular Banking Backend System

A secure, modular **banking backend system** powered by **FastAPI**, **PostgreSQL**, and **Docker**.  
Implements authentication, role-based access, account management, and transaction functionality – all via RESTful APIs (no frontend UI required).

---

## 🧱 Architecture

### Core Components
- **FastAPI** – High-performance Python web API framework  
- **SQLAlchemy ORM** – Database interaction  
- **PostgreSQL** – Relational data storage  
- **JWT** – Authentication and authorization  
- **Docker / Docker Compose** – Consistent environment setup  

---

## ⚙️ Tech Stack

| Component | Technology |
|------------|-------------|
| Language | Python 3.11+ |
| Framework | FastAPI |
| ORM | SQLAlchemy |
| Database | PostgreSQL |
| Authentication | JWT (JSON Web Token) |
| Containerization | Docker, Docker Compose |
| Testing | Pytest, HTTPX |

---

## ✨ Features

### 1. User Management
- Register and authenticate users using JWT tokens  
- Password encryption using `bcrypt`  
- Profile and session validation  

### 2. Account Management
- Create “Savings”, “Current”, or “Fixed Deposit” accounts  
- Auto-generate unique 10-digit account numbers  
- Manage account balances tracked in real-time  

### 3. Transactions
- Secure **Transfer**, **Deposit**, and **Withdraw** endpoints  
- Transaction history with timestamps  
- Balance validation before transfers  

### 4. Role-Based Access Control
- Roles: **Customer** and **Admin**  
- Controlled access for admin-only routes  

### 5. Security
- Passwords hashed with **PassLib**  
- JWT token authentication for all private routes  
- CORS support for all client origins  

---

## 🧠 Database Models

### **User**
| Field | Type | Description |
|--------|------|-------------|
| id | Integer | Unique user identifier |
| name | String | Full name |
| email | String | Unique email per user |
| hashed_password | String | Securely stored password |
| is_admin | Boolean | Role distinction |

### **Account**
| Field | Type | Description |
|--------|------|-------------|
| id | Integer | Account ID |
| account_number | String | Auto-generated number |
| account_type | String | Savings / Current / Fixed Deposit |
| balance | Float | Current account balance |
| user_id | Integer | Foreign key to User |

### **Transaction**
| Field | Type | Description |
|--------|------|-------------|
| id | Integer | Transaction ID |
| account_id | Integer | Related account |
| type | String | deposit / withdraw / transfer |
| amount | Float | Transaction amount |
| created_at | DateTime | Timestamp of operation |

---

## 🚀 API Endpoints

| Method | Endpoint | Description |
|--------|-----------|-------------|
| POST   | `/auth/register` | Register new user |
| POST   | `/auth/login` | Authenticate user (JWT token) |
| GET    | `/accounts/` | Retrieve all user accounts |
| POST   | `/accounts/` | Create a new account |
| POST   | `/accounts/deposit` | Deposit funds |
| POST   | `/accounts/withdraw` | Withdraw funds |
| POST   | `/accounts/transfer` | Transfer between accounts |
| GET    | `/accounts/{account_id}/balance` | Get balance of a specific account |
| GET    | `/admin/users` | View all users (admin only) |
| POST   | `/admin/users/{user_id}/toggle-admin` | Promote/Demote user role |

---

# 🧑‍💻 Author

**Karthick R**  

Developed for **HCL Hackathon 2025**


