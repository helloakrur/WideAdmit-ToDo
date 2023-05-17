# Stage 1: Install dependencies
FROM node:14-alpine AS install

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package.json package-lock.json ./

# Install dependencies
RUN npm ci --quiet

# Stage 2: Run the React app
FROM node:14-alpine

# Set the working directory
WORKDIR /app

# Copy the installed dependencies from the previous stage
COPY --from=install /app/node_modules ./node_modules

# Copy the app's source code
COPY . .

# Expose port 3000 for the React app
EXPOSE 3000

# Start the React app using npm start
CMD ["npm", "start"]
