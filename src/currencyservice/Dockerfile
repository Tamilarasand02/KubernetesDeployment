# Use a specific Node.js version as a base image
FROM node:20.2.0-alpine as base

# Build stage
FROM base as builder

# Install build dependencies
RUN apk add --no-cache python3 make g++

# Set working directory
WORKDIR /usr/src/app

# Copy package.json files
COPY package*.json ./

# Install only production dependencies
RUN npm install --only=production

# Copy the rest of the application code
COPY . .

# Expose the port for the gRPC server
EXPOSE 7000

# Command to start the application
CMD [ "node", "server.js" ]
