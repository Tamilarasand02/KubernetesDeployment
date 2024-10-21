FROM node:20

# Set the working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install --production

# Copy the application files
COPY . .

# Expose the port your app runs on
EXPOSE 7000

# Command to run the app
CMD ["node", "server.js"]
