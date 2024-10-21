# First stage: Build dependencies
FROM node:20-alpine

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
