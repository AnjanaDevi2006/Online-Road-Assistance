# 🚗 RoadAssist — Online Road Assistance Platform

RoadAssist is a full-stack **MERN** (MongoDB, Express, React, Node.js) web application that connects stranded motorists with nearby verified service providers — mechanics, tow trucks, fuel delivery, tire change, and battery jump-start services — in real time.

---

## 📌 Features

### For Users
- Register/login with JWT authentication
- Add and manage multiple vehicles
- Browse and filter nearby service providers
- Request roadside assistance with live status tracking (pending → accepted → ongoing → completed)
- OTP-based service verification for safety
- Rate and review providers after service completion
- In-app notifications

### For Service Providers
- Separate registration/login flow with service type, experience, and bio
- Toggle availability (online/offline)
- View and accept pending service requests
- Track earnings, completed jobs, and ratings
- Reply to customer reviews

---

## 🛠️ Tech Stack

**Backend**
- Node.js + Express.js
- MongoDB with Mongoose
- JWT for authentication
- bcrypt for password hashing

**Frontend**
- React (Vite)
- Tailwind CSS
- React Router DOM
- Axios

**Testing**
- Thunder Client (VS Code extension) — 32 API tests covering auth, users, providers, services, and reviews

---

## 📁 Project Structure

```
online-road-assistance/
├── backend/
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── userController.js
│   │   ├── providerController.js
│   │   ├── serviceController.js
│   │   └── reviewController.js
│   ├── middleware/
│   │   ├── authMiddleware.js
│   │   └── errorMiddleware.js
│   ├── models/
│   │   ├── User.js
│   │   ├── ServiceProvider.js
│   │   ├── ServiceRequest.js
│   │   ├── Vehicle.js
│   │   ├── Review.js
│   │   ├── Notification.js
│   │   └── Payment.js
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── userRoutes.js
│   │   ├── providerRoutes.js
│   │   ├── serviceRoutes.js
│   │   └── reviewRoutes.js
│   ├── .env
│   └── server.js
└── frontend/
    ├── src/
    │   ├── components/   # Navbar, Footer, Layout, shared UI
    │   ├── pages/         # One file per page/route
    │   ├── context/       # Auth state
    │   ├── api/           # Axios instance & API calls
    │   ├── App.jsx
    │   └── main.jsx
    ├── tailwind.config.js
    └── vite.config.js
```

---

## 🔌 API Overview

Base URL: `http://localhost:5000/api`

| Module | Base Route | Description |
|---|---|---|
| Auth | `/auth` | Register/login for users and providers |
| Users | `/users` | Profile, vehicles, dashboard, notifications |
| Providers | `/providers` | Provider profile, dashboard, availability |
| Services | `/services` | Service request lifecycle (create → accept → start → complete → cancel) |
| Reviews | `/reviews` | Ratings, review replies |

All protected routes require a JWT in the header:
```
Authorization: Bearer <token>
```

Full endpoint documentation and example requests/responses are available in the **RoadAssist API Testing Guide** (32 tests, Thunder Client).

---

## ⚙️ Installation & Setup

### Backend
```bash
cd backend
npm install
```

Create a `.env` file in `backend/`:
```
PORT=5000
MONGO_URL=mongodb://localhost:27017/Road
JWT_SECRET=your_jwt_secret_here
```

Start the server:
```bash
npm start
```

### Frontend
```bash
cd frontend
npm install
npm run dev
```

Frontend runs at `http://localhost:5173`, backend at `http://localhost:5000`.

---

## 🧪 Testing

Backend was tested using **Thunder Client** with 32 API tests covering:
- Authentication (register/login for users & providers)
- User profile, vehicles, notifications
- Provider profile, availability, dashboard
- Full service request lifecycle including OTP verification
- Reviews and provider replies

---

## 📄 License

This project was built for educational purposes as part of a Full Stack Web Development course.

---

## 👤 Author

Built by Anjana Devi — [GitHub](https://github.com/AnjanaDevi2006/AnjanaDevi)
