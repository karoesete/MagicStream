# ============================================
# Stage 1: Base image with common setup
# ============================================
FROM node:25-alpine3.22 as base

WORKDIR /app

# install envsubst for dynamic environment variable replacement
RUN apk add --no-cache gettext
# Copy package files and install dependencies with caching
COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 5173

# Start application
# CMD [ "npm", "run", "dev", "--", "--host"]
CMD sh -c "envsubst < public/env.template.js > public/env.js && npm run dev -- --host"


