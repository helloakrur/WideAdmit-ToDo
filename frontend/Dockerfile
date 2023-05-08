# Use the official Node.js Alpine image as the base image
FROM node:alpine

# Set the working directory in the container to /app
WORKDIR /app

# Copy package.json and package-lock.json to the container's working directory
COPY package.json ./
COPY package-lock.json ./

# Copy the rest of the application to the container's working directory
COPY ./ ./

# Install application dependencies using npm
RUN npm i

# Expose port 3000 so it can be accessed from outside the container
EXPOSE 3000

# Start the application using npm when the container starts
CMD ["npm", "run", "start"]
