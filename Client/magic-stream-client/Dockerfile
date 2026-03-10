# ============================================
# Stage 1: Base image with common setup
# ============================================
FROM node:25-alpine3.22 as base

WORKDIR /app

# Copy package files and install dependencies with caching
COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 5173

# Start application
CMD [ "npm", "run", "dev", "--", "--host"]



