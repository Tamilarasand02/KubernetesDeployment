# Use the official Node.js 20.2.0 Alpine image
FROM node:20.2.0-alpine AS builder

# Install required packages for building native addons
RUN apk add --no-cache \
    python3 \
    make \
    g++

# Set the working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json if available
COPY package*.json ./

# Install production dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Expose the application port
EXPOSE 7000

# Command to run the application
CMD ["npm", "start"]
