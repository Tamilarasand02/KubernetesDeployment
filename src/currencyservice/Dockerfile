FROM node:20.2.0-alpine as builder

# Install required packages
RUN apk add --update --no-cache \
    python3 \
    make \
    g++

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm install --only=production

COPY . .

EXPOSE 7000

CMD ["npm", "start"]
