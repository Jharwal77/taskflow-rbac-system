# 🚀 TaskFlow RBAC System

<p align="center">
  <b>A Full-Stack Role-Based Task Management System built with Node.js, Express.js, PostgreSQL, Prisma ORM, JWT Authentication, and Next.js.</b>
</p>

<p align="center">
  Secure • Scalable • Responsive • Modern UI • Production Ready
</p>

---

# 📖 Overview

**TaskFlow RBAC System** is a production-ready **Full Stack Task Management Application** implementing **Role-Based Access Control (RBAC)**.

The project demonstrates industry-standard backend and frontend development practices including authentication, authorization, secure REST APIs, database design, responsive UI development, and scalable architecture.

The application allows users to manage their personal tasks while administrators can manage all users and tasks across the platform.

---

# ✨ Features

## 🔐 Authentication

* User Registration
* User Login
* JWT Authentication
* Password Hashing (bcrypt)
* Protected Routes
* Current User API
* Logout

---

## 👥 Role Based Access Control (RBAC)

### USER

* Create Own Tasks
* View Own Tasks
* Update Own Tasks
* Delete Own Tasks

### ADMIN

* View All Tasks
* Manage All Tasks
* Access Any User's Tasks

---

## 📝 Task Management

* Create Task
* Get All Tasks
* Get Task By ID
* Update Task
* Delete Task

---

## 📊 Dashboard Features

* Task Statistics
* Total Tasks Card
* Pending Tasks
* In Progress Tasks
* Completed Tasks
* Search Tasks
* Status Filtering
* Pagination
* Created Date
* Responsive Table
* Loading Spinner
* Empty State UI
* Dark Mode

---

# 🛠 Tech Stack

## Frontend

* Next.js 15 App Router
* React
* JavaScript
* Tailwind CSS
* Axios
* React Hook Form
* React Hot Toast
* Context API

---

## Backend

* Node.js
* Express.js
* PostgreSQL
* Prisma ORM
* JWT Authentication
* bcryptjs
* Zod Validation
* Swagger
* Docker

---

# 🏗 System Architecture

```text
                        Browser

                           │

                           ▼

                 Next.js Frontend (React)

                           │

                    Axios HTTP Client

                           │

                           ▼

                 Express REST API Server

                           │

        ┌──────────────────┼──────────────────┐

        ▼                  ▼                  ▼

 Authentication      Task Controller      Middleware

        │

        ▼

      Services

        │

        ▼

    Prisma ORM

        │

        ▼

 PostgreSQL Database
```

---

# 📂 Project Structure

```text
taskflow-rbac-system/

│

├── backend/

│   ├── prisma/

│   │    ├── migrations/

│   │    ├── schema.prisma

│   │    └── seed.js

│   │

│   ├── src/

│   │    ├── controllers/

│   │    ├── routes/

│   │    ├── middleware/

│   │    ├── services/

│   │    ├── validators/

│   │    ├── config/

│   │    ├── utils/

│   │    ├── app.js

│   │    └── server.js

│   │

│   └── package.json

│

├── frontend/

│   ├── app/

│   │    ├── dashboard/

│   │    ├── login/

│   │    ├── register/

│   │    └── tasks/

│   │         ├── create/

│   │         └── edit/[id]/

│   │

│   ├── components/

│   ├── context/

│   ├── lib/

│   ├── services/

│   ├── public/

│   └── package.json

│

├── docker-compose.yml

└── README.md
```

---

# 🗄 Database Schema

## User

| Field     | Type         |
| --------- | ------------ |
| id        | UUID         |
| name      | String       |
| email     | String       |
| password  | String       |
| role      | ADMIN / USER |
| createdAt | DateTime     |

---

## Task

| Field       | Type     |
| ----------- | -------- |
| id          | UUID     |
| title       | String   |
| description | String   |
| status      | PENDING  |
| userId      | UUID     |
| createdAt   | DateTime |
| updatedAt   | DateTime |

---

# 📊 Entity Relationship Diagram

```text
User

├── id

├── name

├── email

├── password

├── role

└── createdAt

      │

      │ 1

      │

      ▼

Task

├── id

├── title

├── description

├── status

├── userId

├── createdAt

└── updatedAt
```

---

# 🔐 Authentication Flow

```text
User Login

      │

      ▼

Validate Credentials

      │

      ▼

Generate JWT

      │

      ▼

Return Token

      │

      ▼

Store Token

      │

      ▼

Protected Request

      │

      ▼

Verify JWT

      │

      ▼

Access Granted
```

---

# 🛡 RBAC Flow

```text
Request

    │

    ▼

JWT Middleware

    │

    ▼

Extract User

    │

    ▼

Check Role

    │

 ┌──┴───────────┐

 │              │

 ▼              ▼

ADMIN          USER

 │              │

 │              ▼

 │        Check Ownership

 │              │

 ▼              ▼

Access      Allow / Deny
```

---

# 📡 REST API Endpoints

## Authentication

```http
POST /api/v1/auth/register

POST /api/v1/auth/login

GET /api/v1/auth/me
```

---

## Tasks

```http
POST /api/v1/tasks

GET /api/v1/tasks

GET /api/v1/tasks/:id

PUT /api/v1/tasks/:id

DELETE /api/v1/tasks/:id
```

---

## Pagination

```http
GET /api/v1/tasks?page=1&limit=10
```

---

## Filtering

```http
GET /api/v1/tasks?status=PENDING

GET /api/v1/tasks?status=IN_PROGRESS

GET /api/v1/tasks?status=COMPLETED
```

---

# 📖 Swagger API Documentation

Start backend server:

```bash
npm run dev
```

Open:

```text
http://localhost:5000/api-docs
```

Swagger provides interactive API testing for all endpoints.

---

# 🧪 Testing

Tested using:

* Postman
* Swagger UI
* Browser Frontend

## Tested Scenarios

* ✅ Registration
* ✅ Login
* ✅ JWT Authentication
* ✅ Protected Routes
* ✅ RBAC
* ✅ Create Task
* ✅ Update Task
* ✅ Delete Task
* ✅ Pagination
* ✅ Filtering
* ✅ Dashboard
* ✅ Search
* ✅ Dark Mode

---

# ⚙ Environment Variables

## Backend

```env
PORT=5000

DATABASE_URL=your_database_url

JWT_SECRET=your_secret
```

---

## Frontend

```env
NEXT_PUBLIC_API_URL=http://localhost:5000/api/v1
```

---

# 🐳 Docker

Start PostgreSQL container:

```bash
docker compose up -d
```

Stop:

```bash
docker compose down
```

---

# 🚀 Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/taskflow-rbac-system.git

cd taskflow-rbac-system
```

---

## Backend

```bash
cd backend

npm install

npx prisma migrate dev

npx prisma generate

npm run seed

npm run dev
```

---

## Frontend

```bash
cd frontend

npm install

npm run dev
```

---

Open:

```text
Frontend

http://localhost:3000

Backend

http://localhost:5000
```

---

# 📷 Screenshots

```text
screenshots/

login.png

register.png

dashboard-light.png

dashboard-dark.png

create-task.png

edit-task.png

swagger.png
```

---

# 📈 Scalability Considerations

The project follows a modular architecture and can be extended with:

* Redis Cache
* Horizontal Scaling
* Load Balancer
* Read Replicas
* Connection Pooling
* Microservices
* RabbitMQ
* Kubernetes
* Activity Logs
* Notification Service
* Email Service

---

# 🔮 Future Enhancements

* User Profile
* Refresh Token Authentication
* Email Verification
* Forgot Password
* File Uploads
* Charts & Analytics
* Sidebar Navigation
* Framer Motion Animations
* SweetAlert2 Dialogs
* Redis Caching
* Unit Testing
* Integration Testing
* CI/CD Pipeline

---

# 👨‍💻 Author

## Rahul Meena

Electronics & Communication Engineering Student

Full Stack Developer

Interested in Backend Engineering, Databases, Distributed Systems, and Scalable Web Applications.

---

# ⭐ Project Highlights

* JWT Authentication
* Role-Based Access Control
* Next.js 15 App Router
* Express.js REST APIs
* PostgreSQL Database
* Prisma ORM
* Docker Support
* Swagger Documentation
* Responsive Dashboard
* Dark Mode
* Pagination & Filtering
* Modern UI
* Production Ready Architecture

---

<p align="center">
⭐ If you found this project useful, consider giving it a Star on GitHub!
</p>
