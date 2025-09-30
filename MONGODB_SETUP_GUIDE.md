# MongoDB Database Integration Guide

## 🎯 Choose Your MongoDB Setup

You have **3 options** for MongoDB integration:

### 🌐 **Option 1: MongoDB Atlas (Cloud) - RECOMMENDED**
✅ **Pros**: Free, no local installation, accessible anywhere, reliable
❌ **Cons**: Requires internet connection

### 💻 **Option 2: Local MongoDB Installation**
✅ **Pros**: Works offline, full control
❌ **Cons**: Requires installation and setup

### 🧪 **Option 3: MongoDB Memory Server (Current Setup)**
✅ **Pros**: No setup required, perfect for development
❌ **Cons**: Data is lost when server restarts

---

## 🌐 Option 1: MongoDB Atlas (Cloud Setup) - RECOMMENDED

### Step 1: Create MongoDB Atlas Account
1. Go to https://www.mongodb.com/cloud/atlas
2. Click "Try Free"
3. Sign up with email or Google account
4. Choose "Free" tier (M0 Sandbox)

### Step 2: Create a Cluster
1. Choose **AWS** as cloud provider
2. Select **Free Tier Available** region (usually us-east-1)
3. Keep cluster name as **Cluster0**
4. Click "Create Cluster" (takes 1-3 minutes)

### Step 3: Configure Database Access
1. Click "Database Access" in left sidebar
2. Click "Add New Database User"
3. Choose "Password" authentication
4. Username: `your-username` (remember this)
5. Password: `your-secure-password` (remember this)
6. Database User Privileges: "Read and write to any database"
7. Click "Add User"

### Step 4: Configure Network Access
1. Click "Network Access" in left sidebar
2. Click "Add IP Address"
3. Click "Allow Access from Anywhere" (for development)
4. Or add your specific IP address for security
5. Click "Confirm"

### Step 5: Get Connection String
1. Go to "Clusters" → Click "Connect" on your cluster
2. Choose "Connect your application"
3. Driver: **Node.js**, Version: **4.1 or later**
4. Copy the connection string (looks like):
```
mongodb+srv://username:password@cluster0.xxxxx.mongodb.net/?retryWrites=true&w=majority
```

### Step 6: Update Your .env File
Replace the connection string in your `.env` file:

```env
# Replace this in your server/.env file
MONGODB_URI=mongodb+srv://username:password@cluster0.xxxxx.mongodb.net/collaborative-ai-platform?retryWrites=true&w=majority
```

**Important**: Replace `username`, `password`, and `xxxxx` with your actual values!

---

## 💻 Option 2: Local MongoDB Installation

### For Windows:
1. Download MongoDB Community Server from https://www.mongodb.com/try/download/community
2. Run the installer (.msi file)
3. Choose "Complete" installation
4. Install as Windows Service (recommended)
5. Install MongoDB Compass (GUI tool)

### Start MongoDB:
- Windows Service should auto-start
- Or run: `mongod --dbpath C:\data\db`

### Update .env:
```env
MONGODB_URI=mongodb://localhost:27017/collaborative-ai-platform
```

---

## 🧪 Option 3: Keep Current Memory Server (Easiest)

Your current setup uses MongoDB Memory Server - perfect for development!

**Current .env setting:**
```env
MONGODB_URI=mongodb://localhost:27017/collaborative-ai-platform
```

**Pros**: Already working, no setup needed
**Cons**: Data resets when server restarts

---

## 🚀 Quick Setup Instructions

### I RECOMMEND: MongoDB Atlas (Cloud)

**Copy this template and fill in your details:**

```bash
# 1. Go to https://mongodb.com/cloud/atlas
# 2. Create free account
# 3. Create free cluster
# 4. Add database user: username/password
# 5. Allow network access from anywhere
# 6. Get connection string
# 7. Update your .env file below:
```

**Update your `server/.env` file:**
```env
NODE_ENV=development
PORT=5000
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
JWT_REFRESH_SECRET=your-super-secret-refresh-key-change-this-in-production
CLIENT_URL=http://localhost:3001

# Replace with your MongoDB Atlas connection string:
MONGODB_URI=mongodb+srv://YOUR_USERNAME:YOUR_PASSWORD@cluster0.XXXXX.mongodb.net/collaborative-ai-platform?retryWrites=true&w=majority
```

---

## 🧪 Test Your Database Connection

After updating your `.env` file, restart your server:

```bash
cd server
npm start
```

**Successful connection will show:**
```
Server running on port 5000
Environment: development
✅ MongoDB connected successfully
📍 Connected to: MongoDB Atlas (or Local MongoDB)
```

**If connection fails, you'll see:**
```
❌ MongoDB connection failed: [error details]
🔄 Attempting to use MongoDB Memory Server for development...
```

---

## 📊 Your Database Schema

Your app will automatically create these collections:
- **users** - User accounts and profiles
- **projects** - Project data
- **tasks** - Kanban board tasks
- **documents** - Collaborative documents
- **comments** - Document comments
- **ideas** - AI-generated ideas

---

## 🔧 Database Management Tools

### MongoDB Compass (GUI)
- Download: https://www.mongodb.com/try/download/compass
- Visual interface for your database

### MongoDB Atlas Web Interface
- Built-in web interface for cloud databases
- View data, create indexes, monitor performance

---

## 🔒 Security Best Practices

### For Production:
1. **Strong Passwords**: Use complex database passwords
2. **IP Whitelisting**: Restrict network access to specific IPs
3. **Environment Variables**: Never commit passwords to git
4. **Connection Limits**: Set connection pooling limits

### Example Production .env:
```env
NODE_ENV=production
MONGODB_URI=mongodb+srv://prod_user:super_secure_password@prod-cluster.xxxxx.mongodb.net/collaborative-ai-platform-prod?retryWrites=true&w=majority
```

---

## 🆘 Troubleshooting

### Common Issues:

**"Authentication failed"**
- Check username/password in connection string
- Verify database user exists in Atlas

**"IP not whitelisted"**
- Add your IP to Network Access in Atlas
- Use 0.0.0.0/0 for development (not production)

**"Cannot connect to MongoDB"**
- Check internet connection (for Atlas)
- Verify cluster is running
- Check connection string format

**"Database not found"**
- Database will be created automatically when first document is inserted
- No action needed

---

## ✅ Next Steps After Database Setup

1. **Update .env file** with your MongoDB connection string
2. **Restart server**: `npm start`
3. **Test API endpoints** with your frontend
4. **Create your first user** through registration
5. **Start building projects** in your app!

---

**Need help? Let me know which option you choose and I'll guide you through the specific setup!**
