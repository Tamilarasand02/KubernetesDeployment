FROM node:20.2.0 as base

RUN apk add --update --no-cache \
    python3 \
    make \
    g++

WORKDIR /usr/src/app

COPY package*.json ./

# Set npm log level to verbose for debugging
RUN npm config set loglevel verbose

# Install dependencies
RUN npm install --only=production

COPY . .

EXPOSE 7000

CMD ["npm", "start"]
