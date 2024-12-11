# Use the official Node.js image from Docker Hub
FROM node:18

# Set the working directory inside the container
WORKDIR /app

# Install dependencies for your Next.js app
# Copy the package.json and package-lock.json (or yarn.lock) first to take advantage of Docker's caching
COPY package*.json ./

# Install project dependencies
RUN npm install

# Copy the rest of the application code into the container
COPY . .

# Expose port 3000, which is the default for Next.js development
EXPOSE 3000

# Set environment variable for Next.js to run in development mode
ENV NODE_ENV=development

# Install Next.js and its dependencies if not already part of package.json
RUN npm install next react react-dom

# Command to start the Next.js app in development mode
CMD ["npm", "run", "dev"]
