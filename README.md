# AI-Based Skin Cancer Risk Screening with Lesion Evolution: A CNN–Vision Transformer Framework

A decision-support web application and API prototype for dermatological risk assessment, TEM-Seg boundary segmentation, longitudinal trajectory tracking, and explainable AI (XAI) feature visualizers.

---

## 📁 Project Architecture

```
excel/
├── frontend/                   # Frontend SPA Application (Vercel Ready)
│   ├── public/
│   │   └── index.html          # Main SPA (HTML5, Tailwind CSS, FontAwesome, JS)
│   ├── .env.example            # Frontend environment template
│   ├── Dockerfile              # Docker container configuration for frontend
│   ├── package.json            # Frontend package definition & build scripts
│   ├── server.js               # Static asset server for local/container dev
│   └── vercel.json             # Vercel deployment & routing configuration
├── backend/                    # Backend API Service (Render Ready)
│   ├── src/
│   │   └── server.js           # Express/Node HTTP API with CORS & endpoints
│   ├── .env.example            # Backend environment template
│   ├── Dockerfile              # Container image optimized for ML/CNN API on Render
│   └── package.json            # Backend package definition
├── .gitignore                  # Git ignore rules
├── docker-compose.yml          # Multi-container local orchestration
├── package.json                # Root script runner for monorepo
├── render.yaml                 # Render Infrastructure-as-Code Blueprint
└── README.md                   # Project documentation
```

---

## 🔑 Environment Variables

### Frontend (`/frontend/.env.example`)
```env
PORT=3000
NODE_ENV=production
API_URL=http://localhost:8080
```

### Backend (`/backend/.env.example`)
```env
PORT=8080
HOST=0.0.0.0
NODE_ENV=production
CLIENT_ORIGIN=http://localhost:3000,https://your-frontend.vercel.app
MODEL_NAME="CNN-EfficientNetB4 + ViT-Base"
MODEL_PATH="./models/cnn_vit_skin_cancer.onnx"
API_SECRET_KEY="your-production-secret-key"
```

---

## 🚀 Quick Start (Local Development)

### Option A: Run via Docker Compose (Recommended)
```bash
docker compose up --build
```
- **Frontend SPA**: `http://localhost:3000`
- **Backend API**: `http://localhost:8080`

### Option B: Run via Root npm Scripts

#### Start Frontend & Backend:
```bash
npm run dev:backend
npm run dev:frontend
```

---

## ☁️ Deployment Instructions

### 1. Deploying Frontend to Vercel
- **Root Directory**: `frontend`
- **Build Command**: `npm run build`
- **Output Directory**: `public`
- **Environment Variables**:
  - `API_URL`: `https://your-backend.onrender.com`

### 2. Deploying Backend to Render
- **Root Directory**: `backend`
- **Deployment Method**: Docker / `render.yaml` Blueprint
- **Dockerfile Path**: `Dockerfile`
- **Environment Variables**:
  - `PORT`: (automatically set by Render, defaults to 8080)
  - `HOST`: `0.0.0.0`
  - `CLIENT_ORIGIN`: `https://your-frontend.vercel.app`
