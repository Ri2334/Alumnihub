# 🚀 AlumniHub Setup Guide

This guide will help you set up AlumniHub on your local machine after cloning from GitHub.

## ⚠️ Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v18.0.0 or higher) - [Download](https://nodejs.org/)
- **npm** (v9.0.0 or higher) - Comes with Node.js
- **MongoDB** (v7.0 or higher) - [Download](https://www.mongodb.com/try/download/community)
- **Git** - [Download](https://git-scm.com/downloads)

### Verify Installations

```bash
node --version    # Should show v18.0.0 or higher
npm --version     # Should show v9.0.0 or higher
mongod --version  # Should show v7.0 or higher
```

---

## 📥 Step 1: Clone the Repository

```bash
git clone https://github.com/krishpatel2310/Alumnihub.git
cd Alumnihub
```

---

## 🗄️ Step 2: Set Up MongoDB

### Option A: Local MongoDB

1. **Start MongoDB** (in a separate terminal):
   ```bash
   mongod
   ```

2. MongoDB will create the `Alumni-Project` database automatically when the backend starts.

### Option B: MongoDB Atlas (Cloud)

1. Create a free account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a new cluster
3. Get your connection string (looks like: `mongodb+srv://username:password@cluster.mongodb.net/`)
4. You'll use this in the `.env` file

---

## ⚙️ Step 3: Backend Setup

1. **Navigate to backend directory:**
   ```bash
   cd backend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Create environment file:**
   ```bash
   cp .env.example .env
   ```

4. **Edit the `.env` file** (use your favorite editor):
   ```bash
   # For local MongoDB:
   MONGODB_URI=mongodb://localhost:27017
   
   # For MongoDB Atlas:
   MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/
   ```

   **Note:** The other variables in `.env.example` are already set with default values that work for local development.

5. **Create test users** (important for first login):
   ```bash
   node create-user.js
   ```

   This will create three test accounts:
   - **Student**: `student@test.com` / `password123`
   - **Alumni**: `alumni@test.com` / `password123`
   - **Admin**: `admin@test.com` / `admin123`

6. **Start the backend server:**
   ```bash
   npm start
   ```

   ✅ You should see:
   ```
   MongoDB connected successfully✅
   Server is running on port 5001
   ```

---

## 🎨 Step 4: Frontend Setup

1. **Open a new terminal** and navigate to frontend directory:
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm run dev
   ```

   ✅ You should see:
   ```
   VITE v5.4.19  ready in XXX ms
   ➜  Local:   http://localhost:5173/
   ```

---

## 🎉 Step 5: Access the Application

1. Open your browser and go to: **http://localhost:5173**

2. **Login with test credentials:**
   - Email: `student@test.com`
   - Password: `password123`

3. Explore the features! 🚀

---

## 🔧 Common Issues & Solutions

### Issue 1: "MongoDB connection failed"

**Solution:**
- Ensure MongoDB is running (`mongod` command)
- Check if `MONGODB_URI` in `.env` is correct
- For local MongoDB, use: `mongodb://localhost:27017`

### Issue 2: "Port 5001 already in use"

**Solution:**
- On macOS, AirPlay uses port 5000. Change backend port in `.env`:
  ```bash
  PORT=5001
  ```
- Kill any existing process:
  ```bash
  lsof -ti:5001 | xargs kill -9
  ```

### Issue 3: "Cannot login - 500 error"

**Solution:**
- Make sure you ran `node create-user.js` to create test users
- Check backend terminal for error messages
- Verify MongoDB is running and connected

### Issue 4: "CORS error"

**Solution:**
- Backend is already configured for `http://localhost:5173`
- If frontend runs on a different port, update `FRONTEND_URL` in backend `.env`

### Issue 5: "Module not found" errors

**Solution:**
- Delete `node_modules` and reinstall:
  ```bash
  rm -rf node_modules package-lock.json
  npm install
  ```

---

## 🔐 Environment Variables Explained

### Backend (.env)

| Variable | Description | Default Value |
|----------|-------------|---------------|
| `PORT` | Backend server port | `5001` |
| `MONGODB_URI` | MongoDB connection string | `mongodb://localhost:27017` |
| `ACCESS_TOKEN_SECRET` | JWT secret for access tokens | (provided in .env.example) |
| `REFRESH_TOKEN_SECRET` | JWT secret for refresh tokens | (provided in .env.example) |
| `ACCESS_TOKEN_EXPIRY` | Access token validity | `1d` (1 day) |
| `REFRESH_TOKEN_EXPIRY` | Refresh token validity | `10d` (10 days) |
| `NODE_ENV` | Environment mode | `development` |
| `FRONTEND_URL` | Frontend URL for CORS | `http://localhost:5173` |

### Frontend (.env) - Optional

```env
VITE_API_URL=http://localhost:5001/api
```

If not set, it defaults to `http://localhost:5001/api`

---

## 📝 Testing the Application

### Test User Roles

1. **Student Account** (`student@test.com`)
   - Can view events, jobs, donations
   - Can create posts and comments
   - Can connect with alumni

2. **Alumni Account** (`alumni@test.com`)
   - All student features
   - Can post job opportunities
   - Can create events

3. **Admin Account** (`admin@test.com`)
   - All features
   - Can verify jobs and events
   - Can manage users
   - Access to admin dashboard

---

## 🏗️ Project Ports Overview

| Service | Port | URL |
|---------|------|-----|
| Backend API | 5001 | http://localhost:5001 |
| Frontend | 5173 | http://localhost:5173 |
| MongoDB | 27017 | localhost:27017 |

---

## 📦 Included Test Data

After running `create-user.js`, you'll have:

- ✅ 3 test users (student, alumni, admin)
- ✅ Ready-to-use authentication system
- ✅ All user roles configured

**Note:** No posts, events, or jobs are pre-populated. You can create them after logging in!

---

## 🚀 Next Steps

1. **Customize the application** to your needs
2. **Add your own content** (posts, events, jobs)
3. **Set up Cloudinary** for image uploads (optional)
4. **Configure email service** for password reset (optional)
5. **Deploy to production** when ready

---

## 📞 Need Help?

- Check the [README.md](README.md) for more details
- Open an issue on GitHub
- Contact: kp23104161@gmail.com

---

## ✅ Quick Checklist

Before running the application, ensure:

- [ ] Node.js and npm installed
- [ ] MongoDB installed and running
- [ ] Backend `.env` file created and configured
- [ ] Backend dependencies installed (`npm install`)
- [ ] Test users created (`node create-user.js`)
- [ ] Backend server running (`npm start`)
- [ ] Frontend dependencies installed (`npm install`)
- [ ] Frontend server running (`npm run dev`)
- [ ] Browser opened to http://localhost:5173
- [ ] Successfully logged in with test credentials

---

**Happy Coding! 🎉**
