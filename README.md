# AI-Based Skin Cancer Risk Screening with Lesion Evolution: A CNN–Vision Transformer Framework

A decision-support web application and API prototype for dermatological risk assessment, TEM-Seg boundary segmentation, longitudinal trajectory tracking, and explainable AI (XAI) feature visualizers.

---

## 📁 Project Architecture

```
excel/
├── client/                     # Frontend SPA Application
│   ├── public/
│   │   └── index.html          # Main SPA (HTML5, Tailwind CSS, FontAwesome, JS)
│   ├── .env.example            # Client environment template
│   ├── Dockerfile              # Docker container configuration for client
│   ├── netlify.toml            # Netlify deployment configuration
│   ├── package.json            # Client package definition
│   ├── server.js               # Static asset server for client
│   └── vercel.json             # Vercel deployment configuration
├── server/                     # Backend API Service
│   ├── src/
│   │   └── server.js           # Express/Node HTTP API with CORS & endpoints
│   ├── .env.example            # Server environment template
│   ├── Dockerfile              # Docker container configuration for backend
│   └── package.json            # Server package definition
├── .gitignore                  # Git ignore rules
├── docker-compose.yml          # Multi-container local orchestration
├── package.json                # Monorepo root script runner
└── README.md                   # Documentation
```

---

## 🔑 Environment Variables

### Frontend (`/client/.env.example`)
```env
PORT=3000
NODE_ENV=production
API_URL=http://localhost:8080
```

### Backend (`/server/.env.example`)
```env
PORT=8080
NODE_ENV=production
CLIENT_ORIGIN=http://localhost:3000
```

---

## 🚀 Quick Start (Local Development)

### Option A: Run via Docker Compose (Recommended)
```bash
docker compose up --build
```
- **Frontend SPA**: `http://localhost:3000`
- **Backend API**: `http://localhost:8080`

### Option B: Run via Node.js

#### 1. Start the Backend Server:
```bash
cd server
npm start
```

#### 2. Start the Frontend Application:
```bash
cd client
npm start
```

---

## ☁️ Deployment Instructions

### 1. Deploying Frontend (Vercel / Netlify)
- **Root Directory**: `client`
- **Publish Directory**: `public`
- Set Environment Variable: `API_URL=https://your-backend-api.onrender.com`

### 2. Deploying Backend (Render / Railway / AWS / Heroku)
- **Root Directory**: `server`
- **Build Command**: `npm install`
- **Start Command**: `npm start`
- Set Environment Variables:
  - `PORT`: (automatically provided by cloud host)
  - `CLIENT_ORIGIN`: `https://your-frontend.vercel.app`
