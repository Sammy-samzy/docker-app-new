FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package.json files first
COPY package*.json ./

# Install dependencies
RUN npm install

# Accept build arguments
ARG NEXT_PUBLIC_APPWRITE_ENDPOINT
ARG NEXT_PUBLIC_APPWRITE_PROJECT

# Make them available as environment variables
ENV NEXT_PUBLIC_APPWRITE_ENDPOINT=$NEXT_PUBLIC_APPWRITE_ENDPOINT
ENV NEXT_PUBLIC_APPWRITE_PROJECT=$NEXT_PUBLIC_APPWRITE_PROJECT

# Copy the rest of the files
COPY . .

# Build the Next.js app
RUN npm run build

# Expose port 3000
EXPOSE 3000

# Start the app
CMD ["npm", "start"]
