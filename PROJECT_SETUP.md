# Skill Board - Complete Project Setup

## ✅ Installation Status

### Backend Dependencies ✅
All backend dependencies have been installed:
- ✅ Express.js
- ✅ Prisma & Prisma Client
- ✅ MySQL adapter
- ✅ Auth.js (NextAuth)
- ✅ JWT & bcrypt
- ✅ CORS & cookie-parser
- ✅ dotenv

### Frontend Dependencies ✅
All frontend dependencies have been installed:
- ✅ React 18
- ✅ React Router DOM
- ✅ Vite
- ✅ Axios
- ✅ Vite React Plugin

### Prisma Client ✅
Prisma Client has been generated and is ready to use.

## 📁 Project Structure

```
capstone-2ndyear/
├── backend/
│   ├── config/
│   │   └── auth.js              # Auth.js configuration
│   ├── middleware/
│   │   └── auth.js              # Authentication middleware
│   ├── routes/
│   │   ├── auth.js              # Auth routes (signup, login, etc.)
│   │   └── auth-nextauth.js     # NextAuth routes
│   ├── prisma/
│   │   └── schema.prisma        # Database schema
│   ├── .env                     # Environment variables (created)
│   ├── server.js                # Express server
│   ├── package.json             # ✅ Dependencies installed
│   └── node_modules/            # ✅ Installed
│
└── frontend/
    ├── src/
    │   ├── components/
    │   │   ├── Login.jsx        # Login component
    │   │   ├── Signup.jsx       # Signup component
    │   │   ├── Dashboard.jsx    # Dashboard component
    │   │   ├── Auth.css         # Auth styles
    │   │   └── Dashboard.css    # Dashboard styles
    │   ├── context/
    │   │   └── AuthContext.jsx  # Auth context provider
    │   ├── services/
    │   │   └── api.js           # API service
    │   ├── App.jsx              # Main app component
    │   ├── main.jsx             # Entry point
    │   ├── index.css            # Global styles
    │   └── App.css              # App styles
    ├── index.html               # HTML template
    ├── vite.config.js           # Vite configuration
    ├── package.json             # ✅ Dependencies installed
    └── node_modules/            # ✅ Installed
```

## 🚀 How to Run the Project

### Step 1: Set Up Database (Backend)

1. **Update `.env` file in backend directory:**
   ```bash
   cd backend
   ```
   
   Edit `.env` and update the `DATABASE_URL`:
   ```env
   DATABASE_URL="mysql://your_username:your_password@localhost:3306/your_database"
   ```

2. **Run database migrations:**
   ```bash
   npm run prisma:migrate
   ```
   This will create all necessary database tables.

### Step 2: Start Backend Server

```bash
cd backend
npm run dev
```

The backend will run on `http://localhost:3000`

### Step 3: Start Frontend Server

Open a new terminal:

```bash
cd frontend
npm run dev
```

The frontend will run on `http://localhost:3001`

## 📝 Available Scripts

### Backend Scripts
- `npm run dev` - Start development server with auto-reload
- `npm start` - Start production server
- `npm run prisma:generate` - Generate Prisma Client
- `npm run prisma:migrate` - Run database migrations
- `npm run prisma:studio` - Open Prisma Studio (database GUI)

### Frontend Scripts
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build

## 🔗 API Endpoints

### Backend (http://localhost:3000)
- `GET /health` - Health check
- `POST /api/auth/signup` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user (protected)
- `POST /api/auth/logout` - Logout (protected)
- `GET /api/protected` - Example protected route

### Frontend (http://localhost:3001)
- `/login` - Login page
- `/signup` - Signup page
- `/dashboard` - Dashboard (protected)
- `/` - Redirects to dashboard

## 🔐 Authentication Flow

1. User signs up → Account created in database
2. User logs in → JWT token generated and stored in localStorage
3. Token sent with every API request in Authorization header
4. Protected routes check token validity
5. Invalid/expired tokens redirect to login

## 🛠️ Troubleshooting

### Backend Issues

**Database Connection Error:**
- Check MySQL is running
- Verify DATABASE_URL in `.env` is correct
- Ensure database exists (create it if needed)

**Prisma Errors:**
- Run `npm run prisma:generate` again
- Check `prisma/schema.prisma` for syntax errors

**Port Already in Use:**
- Change PORT in `.env` file
- Or kill the process using port 3000

### Frontend Issues

**Cannot Connect to Backend:**
- Ensure backend is running on port 3000
- Check CORS settings in backend
- Verify `VITE_API_URL` in frontend `.env` (if using custom URL)

**Build Errors:**
- Delete `node_modules` and run `npm install` again
- Check for syntax errors in components

## 📦 Installed Packages Summary

### Backend (144 packages)
- Core: express, cors, dotenv, cookie-parser
- Database: @prisma/client, prisma, @auth/prisma-adapter
- Auth: next-auth, jsonwebtoken, bcryptjs

### Frontend (89 packages)
- Core: react, react-dom, react-router-dom
- Build: vite, @vitejs/plugin-react
- HTTP: axios

## ✨ Next Steps

1. ✅ Dependencies installed
2. ✅ Prisma Client generated
3. ⏳ Update DATABASE_URL in backend/.env
4. ⏳ Run database migrations
5. ⏳ Start both servers
6. ⏳ Test signup and login functionality

## 🎉 You're All Set!

Both backend and frontend are ready to use. Just update your database credentials and start the servers!

