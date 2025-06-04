# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.
FROM node:6-alpine

RUN apk add --no-cache tini
# Set the working directory
WORKDIR /usr/src/app
# Copy package.json and package-lock.json
COPY package*.json ./
# Install dependencies
RUN npm install && npm cache clean --force
# Copy the rest of the application code
COPY . .
# Expose the port the app runs on
EXPOSE 3000
# Start the application
# 7) use tini as PID 1 and start the server via bin/www
CMD ["/sbin/tini", "--", "node", "./bin/www"]