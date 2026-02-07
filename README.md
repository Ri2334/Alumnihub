# 🎓 AlumniHub - Alumni-Student Networking Platform

<div align="center">

[![React](https://img.shields.io/badge/React-19.0-61DAFB?logo=react)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?logo=node.js)](https://nodejs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.6-3178C6?logo=typescript)](https://www.typescriptlang.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-7.0-47A248?logo=mongodb)](https://www.mongodb.com/)
[![Express](https://img.shields.io/badge/Express-5.0-000000?logo=express)](https://expressjs.com/)

**A comprehensive full-stack platform bridging the gap between students and alumni through mentorship, career opportunities, and community building.**

[Live Demo](#) • [Report Bug](#) • [Request Feature](#)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Tech Stack](#-tech-stack)
- [System Architecture](#-system-architecture)
- [Getting Started](#-getting-started)
- [API Documentation](#-api-documentation)
- [Database Schema](#-database-schema)
- [Project Structure](#-project-structure)
- [Environment Variables](#-environment-variables)

---

## 🌟 Overview

AlumniHub is a modern, feature-rich platform designed to foster meaningful connections between students, alumni, and administrators. The platform facilitates networking, mentorship, job opportunities, event management, and community building through an intuitive and responsive interface.

### 🎯 Problem Statement

Educational institutions struggle to maintain active alumni engagement and provide students with valuable industry connections. Traditional methods lack scalability and real-time interaction capabilities.

### 💡 Solution

AlumniHub provides a centralized, interactive platform that:
- Connects students with alumni for mentorship and career guidance
- Enables seamless communication through posts, comments, and direct messaging
- Facilitates event organization and participation
- Streamlines job postings and applications
- Manages donation campaigns transparently
- Provides powerful admin tools for community moderation

---

## ✨ Key Features

### 👤 User Management
- **Multi-role Authentication** (Student, Alumni, Admin)
- JWT-based secure authentication with refresh tokens
- Password reset with OTP verification via email
- Profile management with avatar uploads
- Advanced user search and filtering

### 💬 Communication
- **Reddit-style Post System** with upvote/downvote functionality
- Nested comments with @mentions
- Real-time notifications
- Direct messaging between users
- Content moderation and filtering

### 🎉 Events
- Create and manage events with rich details
- RSVP tracking and attendee management
- Event categorization and search
- Upcoming and past events timeline
- Admin approval workflow

### 💼 Job Board
- Alumni can post job opportunities
- Students can browse and apply for jobs
- Job verification by admins
- Filter by company, location, and job type
- Application tracking

### 💰 Donations
- Create donation campaigns with goals
- Track donation progress with visual indicators
- Multiple payment gateway integration ready
- Donation history and receipts
- Admin oversight and reporting

### 📊 Admin Dashboard
- Comprehensive analytics and insights
- User management and verification
- Content moderation tools
- Report handling system
- Activity monitoring

### 🎨 UI/UX
- Responsive design (mobile, tablet, desktop)
- Smooth animations with Framer Motion
- Progressive Web App (PWA) capabilities
- Modern design with TailwindCSS & Shadcn UI

---

## 🛠 Tech Stack

### Frontend
| Technology | Purpose |
|------------|---------|
| **React 19** | UI library with latest features |
| **TypeScript** | Type-safe JavaScript |
| **Vite** | Lightning-fast build tool |
| **TailwindCSS** | Utility-first CSS framework |
| **Shadcn/ui** | High-quality React components |
| **React Router v6** | Client-side routing |
| **Axios** | HTTP client with interceptors |
| **Framer Motion** | Animation library |
| **Recharts** | Data visualization |

### Backend
| Technology | Purpose |
|------------|---------|
| **Node.js 18+** | JavaScript runtime |
| **Express 5** | Web application framework |
| **MongoDB 7** | NoSQL database |
| **Mongoose** | ODM for MongoDB |
| **JWT** | Token-based authentication |
| **bcryptjs** | Password hashing |
| **Multer** | File upload handling |
| **Cloudinary** | Image/file storage |
| **Nodemailer** | Email service |

### Development Tools
- **ESLint & Prettier** - Code quality and formatting
- **Git** - Version control
- **Postman** - API testing
- **MongoDB Compass** - Database management

---

## 🏗 System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                         Frontend (React)                     │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Pages      │  │  Components  │  │   Services   │      │
│  │ (Views/UI)   │  │ (Reusable)   │  │  (API calls) │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
└────────────────────────────┬────────────────────────────────┘
                             │ HTTP/HTTPS (REST API)
                             │
┌────────────────────────────▼────────────────────────────────┐
│                     Backend (Express.js)                     │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Routes     │  │ Controllers  │  │ Middlewares  │      │
│  │ (Endpoints)  │  │  (Logic)     │  │ (Auth/Valid) │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
│  ┌──────────────┐  ┌──────────────┐                         │
│  │   Models     │  │   Services   │                         │
│  │  (Mongoose)  │  │ (Email/OTP)  │                         │
│  └──────────────┘  └──────────────┘                         │
└────────────────────────────┬────────────────────────────────┘
                             │
                   ┌─────────┴──────────┐
                   │                    │
         ┌─────────▼──────────┐  ┌─────▼──────────┐
         │   MongoDB Atlas    │  │   Cloudinary   │
         │  (Database)        │  │ (File Storage) │
         └────────────────────┘  └────────────────┘
```

---

## 🚀 Getting Started

### Prerequisites

```bash
Node.js >= 18.0.0
npm >= 9.0.0
MongoDB >= 7.0
Git
```

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/krishpatel2310/Alumnihub.git
cd Alumnihub
```

2. **Backend Setup**
```bash
cd backend
npm install

# Create .env file (see Environment Variables section)
# Add your MongoDB URI, JWT secrets, etc.

# Start MongoDB (if running locally)
mongod

# Run backend server
npm start
# Server runs on http://localhost:5001
```

3. **Frontend Setup**
```bash
cd frontend
npm install

# Start development server
npm run dev
# Frontend runs on http://localhost:5173
```

4. **Create Test Users (Optional)**
```bash
cd backend
node create-user.js
```

This creates:
- **Student**: `student@test.com` / `password123`
- **Alumni**: `alumni@test.com` / `password123`
- **Admin**: `admin@test.com` / `admin123`

---

## 📡 API Documentation

### Authentication Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/api/login` | User login | No |
| POST | `/api/logout` | User logout | Yes |
| POST | `/api/refresh-token` | Refresh access token | Yes |
| POST | `/api/forgot-password` | Request password reset | No |
| POST | `/api/verify-otp` | Verify OTP | No |
| POST | `/api/reset-password` | Reset password | No |

### User Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/user/profile` | Get user profile | Yes |
| PUT | `/api/user/profile` | Update profile | Yes |
| GET | `/api/user/search` | Search users | Yes |
| GET | `/api/user/:id` | Get user by ID | Yes |
| POST | `/api/user/avatar` | Upload avatar | Yes |

### Post Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/posts` | Get all posts | Yes |
| POST | `/api/posts` | Create post | Yes |
| GET | `/api/posts/:id` | Get post by ID | Yes |
| PUT | `/api/posts/:id` | Update post | Yes |
| DELETE | `/api/posts/:id` | Delete post | Yes |
| POST | `/api/posts/:id/vote` | Upvote/Downvote | Yes |
| POST | `/api/posts/:id/comment` | Add comment | Yes |

### Event Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/events` | Get all events | Yes |
| POST | `/api/events` | Create event | Yes (Alumni) |
| GET | `/api/events/:id` | Get event details | Yes |
| PUT | `/api/events/:id` | Update event | Yes (Alumni) |
| DELETE | `/api/events/:id` | Delete event | Yes (Alumni) |
| POST | `/api/events/:id/rsvp` | RSVP to event | Yes |

### Job Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/jobs` | Get all jobs | Yes |
| POST | `/api/jobs` | Post a job | Yes (Alumni) |
| GET | `/api/jobs/:id` | Get job details | Yes |
| PUT | `/api/jobs/:id` | Update job | Yes (Alumni) |
| DELETE | `/api/jobs/:id` | Delete job | Yes (Alumni) |
| POST | `/api/jobs/:id/verify` | Verify job | Yes (Admin) |

### Donation Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/donations` | Get all campaigns | Yes |
| POST | `/api/donations` | Create campaign | Yes (Admin) |
| GET | `/api/donations/:id` | Get campaign details | Yes |
| POST | `/api/donations/:id/donate` | Make donation | Yes |

### Admin Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/admin/dashboard` | Get admin stats | Yes (Admin) |
| GET | `/api/admin/users` | Get all users | Yes (Admin) |
| PUT | `/api/admin/users/:id/verify` | Verify user | Yes (Admin) |
| GET | `/api/admin/reports` | Get reports | Yes (Admin) |
| POST | `/api/admin/reports/:id/action` | Handle report | Yes (Admin) |

---

## 🗄 Database Schema

### User Collection
```javascript
{
  _id: ObjectId,
  name: String (required),
  email: String (required, unique),
  password: String (required, hashed),
  role: Enum ['student', 'alumni', 'admin'],
  avatar: String (URL),
  bio: String,
  graduationYear: Number,
  department: String,
  company: String,
  jobTitle: String,
  location: String,
  skills: [String],
  socialLinks: {
    linkedin: String,
    github: String,
    twitter: String
  },
  isVerified: Boolean (default: false),
  refreshToken: String,
  createdAt: Date,
  updatedAt: Date
}
```

### Post Collection
```javascript
{
  _id: ObjectId,
  author: ObjectId (ref: User),
  title: String (required),
  content: String (required),
  images: [String],
  upvotes: [ObjectId] (ref: User),
  downvotes: [ObjectId] (ref: User),
  commentsCount: Number,
  tags: [String],
  createdAt: Date,
  updatedAt: Date
}
```

### Event Collection
```javascript
{
  _id: ObjectId,
  title: String (required),
  description: String,
  organizer: ObjectId (ref: User),
  startDate: Date (required),
  endDate: Date,
  location: String,
  type: Enum ['online', 'offline', 'hybrid'],
  maxAttendees: Number,
  attendees: [ObjectId] (ref: User),
  isVerified: Boolean (default: false),
  images: [String],
  createdAt: Date,
  updatedAt: Date
}
```

### Job Collection
```javascript
{
  _id: ObjectId,
  title: String (required),
  company: String (required),
  location: String,
  type: Enum ['full-time', 'part-time', 'internship', 'contract'],
  description: String,
  requirements: [String],
  salary: String,
  postedBy: ObjectId (ref: User),
  isVerified: Boolean (default: false),
  applicants: [ObjectId] (ref: User),
  deadline: Date,
  createdAt: Date
}
```

---

## 📁 Project Structure

```
Alumnihub/
├── backend/
│   ├── src/
│   │   ├── controllers/       # Business logic
│   │   ├── models/            # Mongoose schemas
│   │   ├── routes/            # API routes
│   │   ├── middlewares/       # Express middlewares
│   │   ├── services/          # Business services
│   │   ├── utils/             # Helper functions
│   │   ├── db/                # Database configuration
│   │   ├── app.js             # Express app setup
│   │   └── index.js           # Entry point
│   ├── public/temp/           # Temporary file uploads
│   ├── .env                   # Environment variables
│   ├── package.json
│   └── create-user.js         # User seeding script
│
├── frontend/
│   ├── src/
│   │   ├── components/        # React components
│   │   ├── pages/             # Page components
│   │   ├── context/           # React Context
│   │   ├── services/          # API services
│   │   ├── hooks/             # Custom hooks
│   │   ├── lib/               # Utilities
│   │   ├── App.tsx            # Root component
│   │   └── main.tsx           # Entry point
│   ├── public/
│   │   ├── manifest.json      # PWA manifest
│   │   └── service-worker.js  # PWA service worker
│   ├── vite.config.ts
│   ├── tailwind.config.ts
│   └── package.json
│
└── README.md
```

---

## 🔐 Environment Variables

### Backend (.env)

```env
# Server Configuration
PORT=5001
NODE_ENV=development

# Database
MONGODB_URI=mongodb://localhost:27017/Alumni-Project

# JWT Secrets
ACCESS_TOKEN_SECRET=your-super-secret-access-token-key-here
REFRESH_TOKEN_SECRET=your-super-secret-refresh-token-key-here
ACCESS_TOKEN_EXPIRY=1d
REFRESH_TOKEN_EXPIRY=10d

# Cloudinary (Image Storage)
CLOUDINARY_CLOUD_NAME=your-cloud-name
CLOUDINARY_API_KEY=your-api-key
CLOUDINARY_API_SECRET=your-api-secret

# Email Service (Nodemailer)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-app-password

# Frontend URL (for CORS)
FRONTEND_URL=http://localhost:5173
```

### Frontend (.env)

```env
# API Base URL
VITE_API_URL=http://localhost:5001/api

# App Configuration
VITE_APP_NAME=AlumniHub
VITE_APP_VERSION=1.0.0
```

---

## 🎯 Future Enhancements

- [ ] Real-time chat with WebSocket
- [ ] Video call integration for mentorship
- [ ] Advanced analytics dashboard
- [ ] Mobile app (React Native)
- [ ] AI-powered job recommendations
- [ ] Resume builder and review system
- [ ] Event livestreaming
- [ ] Alumni directory with advanced filters

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License.

---

## 👨‍💻 Developer

**Krish Patel**
- GitHub: [@krishpatel2310](https://github.com/krishpatel2310)
- Email: kp23104161@gmail.com

---

## 📞 Support

For support, email kp23104161@gmail.com or open an issue in the repository.

---

<div align="center">

**Made with ❤️ by Krish Patel**

⭐ Star this repository if you find it helpful!

</div>
