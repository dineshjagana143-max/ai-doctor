# Backend Dockerfile
FROM node:20-alpine

WORKDIR /app

COPY package.json ./
COPY src ./src

ENV PORT=8080
ENV NODE_ENV=production
EXPOSE 8080

CMD ["npm", "start"]
