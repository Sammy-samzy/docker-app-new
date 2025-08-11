# Use official Node.js image as the base
FROM node:18-alpine

# Set working directory inside container
WORKDIR /app

# Copy package.json and package-lock.json first (for better caching)
COPY package*.json ./

# Copy the environment file
COPY .env ./

# Install dependencies
RUN npm install

# Copy the rest of your app files
COPY . .

# Build the Next.js app (this will use env vars from .env)
RUN npm run build

# Expose port 3000 (default for Next.js)
EXPOSE 3000

# Start the Next.js app in production mode
CMD ["npm", "start"]
