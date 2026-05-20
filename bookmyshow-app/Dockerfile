# Use stable LTS Node version (recommended)
FROM node:22

# Set working directory
WORKDIR /app

# Copy dependency files first (for caching)
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install --legacy-peer-deps

# Copy full source code
COPY . .

# Fix OpenSSL issue (common in React builds)
ENV NODE_OPTIONS=--openssl-legacy-provider

# App config
ENV PORT=3000

# Expose app port
EXPOSE 3000

# Start application
CMD ["npm", "start"]
