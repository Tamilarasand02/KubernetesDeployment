# First stage: Build dependencies
FROM node:20.2.0-alpine@sha256:f25b0e9d3d116e267d4ff69a3a99c0f4cf6ae94eadd87f1bf7bd68ea3ff0bef7 as builder

# Install required packages
RUN apk add --update --no-cache \
    python3 \
    make \
    g++

# Set working directory
WORKDIR /usr/src/app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application files
COPY . .
# Expose the application port
EXPOSE 4051
# Command to run the application
CMD ["npm", "start"]
