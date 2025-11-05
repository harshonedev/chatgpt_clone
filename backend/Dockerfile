# Use the official Node.js image
FROM node:24-slim

# Install OpenSSL (required for Prisma)
RUN apt-get update -y && apt-get install -y openssl

# Create app directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy app source code
COPY . .

# Generate Prisma Client
RUN npx prisma generate

# Expose the port the app runs on
EXPOSE 5000

# Command to run the app
CMD ["node", "src/index.js"]
