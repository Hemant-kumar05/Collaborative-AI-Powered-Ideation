# Collaborative AI Platform - Backend Setup Guide

## 🚀 Quick Start

Your backend is now running with the following setup:

### ✅ What's Working
- **Server**: Running on http://localhost:5000
- **Environment**: Development mode
- **Database**: MongoDB Memory Server (in-memory database)
- **API Endpoints**: All routes configured
- **Socket.IO**: Real-time connections ready

### 📊 API Endpoints

#### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/profile` - Get user profile

#### Projects
- `GET /api/projects` - Get all projects
- `POST /api/projects` - Create new project
- `PUT /api/projects/:id` - Update project
- `DELETE /api/projects/:id` - Delete project

#### Tasks (Kanban)
- `GET /api/tasks` - Get all tasks
- `POST /api/tasks` - Create new task
- `PUT /api/tasks/:id` - Update task
- `DELETE /api/tasks/:id` - Delete task

#### Documents
- `GET /api/documents` - Get all documents
- `POST /api/documents` - Create new document
- `PUT /api/documents/:id` - Update document
- `DELETE /api/documents/:id` - Delete document

#### Chat
- `GET /api/chat` - Get chat messages
- `POST /api/chat` - Send message

#### AI Services
- `POST /api/ai/generate-ideas` - Generate AI ideas
- `POST /api/ai/suggest-improvements` - AI suggestions

#### Analytics
- `GET /api/analytics/dashboard` - Dashboard analytics
- `GET /api/analytics/projects` - Project analytics

#### System
- `GET /api/health` - Health check
- `GET /api` - API information

### 🛠️ Development Database

Currently using **MongoDB Memory Server** which:
- ✅ Requires no local MongoDB installation
- ✅ Perfect for development and testing
- ✅ Data resets when server restarts
- ✅ Automatically downloads MongoDB binaries (first time only)

### 🔗 Frontend Integration

Your frontend (http://localhost:3001) can now connect to the backend:

```javascript
// Example API call from frontend
const response = await fetch('http://localhost:5000/api/projects');
const projects = await response.json();
```

### 🌐 Production Database Setup (Optional)

For persistent data, set up MongoDB Atlas:

1. Go to https://www.mongodb.com/atlas
2. Create a free account
3. Create a new cluster
4. Get your connection string
5. Update `.env` file:
```env
MONGODB_URI=mongodb+srv://username:password@cluster0.xxxxx.mongodb.net/collaborative-ai-platform?retryWrites=true&w=majority
```

### 🔐 Environment Variables

Current configuration in `server/.env`:
```env
NODE_ENV=development
PORT=5000
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
JWT_REFRESH_SECRET=your-super-secret-refresh-key-change-this-in-production
CLIENT_URL=http://localhost:3001
MONGODB_URI=mongodb://localhost:27017/collaborative-ai-platform
```

### 🧪 Testing the API

Test endpoints using:
- **Browser**: http://localhost:5000/api/health
- **Postman**: Import endpoints for testing
- **Frontend**: Direct integration with React app

### 🔄 Socket.IO Real-time Features

Your real-time features are configured for:
- Live chat
- Collaborative whiteboard
- Real-time Kanban updates
- Document collaboration

### 📝 Next Steps

1. ✅ Backend server running
2. ✅ Database configured (in-memory)
3. 🔄 Wait for MongoDB download to complete
4. 🚀 Start integrating with frontend
5. 🧪 Test real-time features
6. 🌐 Optional: Set up MongoDB Atlas for persistence

### 🐛 Troubleshooting

**If server won't start:**
```bash
# Kill processes on port 5000
netstat -ano | findstr :5000
taskkill /PID [PID_NUMBER] /F

# Restart server
npm start
```

**Database connection issues:**
- Memory server will automatically handle local database
- Check terminal output for download progress
- For production, verify MongoDB Atlas connection string

---

## 🎉 Your backend is ready for development!

The server will automatically connect to the database once the MongoDB download completes.
You can start integrating your React frontend with the backend API immediately.
