
# AI Collab Platform

## Project Structure

- `Collaborative AI-Powered Ideation/server`: Backend (Node.js, Express)
- `Collaborative AI-Powered Ideation/client`: Frontend (React)

## Prerequisites

- Node.js & npm installed
- MongoDB running locally or provide a connection string

## Setup & Run

### 1. Backend
```bash
cd "Collaborative AI-Powered Ideation/server"
npm install
npm start
```
The backend will start on the configured port (default: 5000).

### 2. Frontend
```bash
cd "Collaborative AI-Powered Ideation/client"
npm install
npm start
```
The frontend will start on port 3000 by default.

## Environment Variables

Create a `.env` file in the backend folder with:
```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
```

## Features
- AI-powered ideation
- Real-time chat & collaboration
- Kanban board
- Document editor
- Analytics dashboard

## Troubleshooting
- Ensure MongoDB is running and accessible
- Check terminal for errors during `npm start`

## License
MIT
# Collaborative-AI-Powered-Ideation  
