# 🚀 Quick Start Guide

## ✅ Current Status

### Backend Server ✅
- **Status:** Running
- **URL:** http://localhost:3000
- **Health Check:** http://localhost:3000/health
- **Process ID:** Running in background

### Frontend Server ✅
- **Status:** Running  
- **URL:** http://localhost:3001
- **Process ID:** Running in background

## 🌐 Access Your Application

### Open in Browser:
1. **Frontend (Skill Board):** http://localhost:3001
2. **Backend API:** http://localhost:3000/health

## 🔧 If You Still See Connection Refused

### Check 1: Verify Servers Are Running
```bash
# Check backend (port 3000)
lsof -ti:3000

# Check frontend (port 3001)
lsof -ti:3001
```

### Check 2: Restart Servers

**Stop existing servers:**
```bash
# Kill backend (if needed)
kill $(lsof -ti:3000)

# Kill frontend (if needed)
kill $(lsof -ti:3001)
```

**Start Backend:**
```bash
cd backend
npm run dev
```

**Start Frontend (in new terminal):**
```bash
cd frontend
npm run dev
```

### Check 3: Browser Issues
- Clear browser cache
- Try incognito/private mode
- Try a different browser
- Check if you have any browser extensions blocking localhost

### Check 4: Firewall/Proxy
- Disable VPN if active
- Check system firewall settings
- Ensure localhost is not blocked

## 📝 Common Issues

### Port Already in Use
If you get "port already in use" error:
```bash
# Find and kill process on port 3000
lsof -ti:3000 | xargs kill -9

# Find and kill process on port 3001
lsof -ti:3001 | xargs kill -9
```

### Database Connection Error
If backend shows database errors:
1. Check MySQL is running
2. Verify DATABASE_URL in `backend/.env`
3. Run migrations: `cd backend && npm run prisma:migrate`

### CORS Errors
If you see CORS errors in browser console:
- Ensure backend is running on port 3000
- Check `FRONTEND_URL` in `backend/.env` matches frontend URL

## 🎯 Test the Application

1. **Open:** http://localhost:3001
2. **Sign Up:** Create a new account
3. **Login:** Use your credentials
4. **Dashboard:** You should see your user info

## 📞 Server Logs

Check terminal windows where you started the servers to see:
- Backend: API requests and responses
- Frontend: Build status and errors

## ✅ Everything Working?

If both servers are running and you can access http://localhost:3001, you're all set! 🎉

