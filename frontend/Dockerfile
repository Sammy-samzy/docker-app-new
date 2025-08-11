# Use official Node.js image as the base
FROM node:18-alpine

# Set working directory inside container
WORKDIR /app

# Copy package.json and package-lock.json (if present)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy all app files including .env
COPY . .

# Build the Next.js app (env variables available from .env)
RUN npm run build

# Expose port 3000 (default for Next.js)
EXPOSE 3000

# Start the Next.js app in production mode
CMD ["npm", "start"]
