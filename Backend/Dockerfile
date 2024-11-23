# Use the official node image
FROM node:20

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the application code
COPY . .

# Expose the backend port
EXPOSE 3000

# Start the application
CMD ["npm", "start"]