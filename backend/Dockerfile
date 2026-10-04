# Backend Dockerfile optimized for Render & heavy ML/CNN APIs
FROM node:20-alpine

# Set working directory
WORKDIR /app

# Copy dependency definitions
COPY package.json ./

# Copy source code and model weights (if present)
COPY src ./src

# Set default production environment variables
ENV PORT=8080
ENV HOST=0.0.0.0
ENV NODE_ENV=production
ENV MODEL_NAME="CNN-EfficientNetB4 + ViT-Base"
ENV MODEL_PATH="./models/cnn_vit_skin_cancer.onnx"

# Expose server port
EXPOSE 8080

# Start command binding to 0.0.0.0 and $PORT
CMD ["node", "src/server.js"]
