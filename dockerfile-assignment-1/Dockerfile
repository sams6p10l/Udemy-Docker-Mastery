# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.

# Node official image, with the alpine 6.x branch
FROM node:6.17.1-alpine

# Install tini
RUN apk add --no-cache tini

# Set the working directory
WORKDIR /usr/src/app

# Copy package.json
COPY package.json /usr/src/app/

# Install dependencies
RUN npm install && npm cache clean --force

# Copy the rest of the application files
COPY . /usr/src/app/

# Expose the application port
EXPOSE 3000

# Use tini as the init system
CMD ["/sbin/tini", "--", "node", "./bin/www"]
