# Use a node image for building the frontend
FROM node:20 AS build

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application
COPY . .

# Build the frontend
RUN npm run build

# Use a lightweight server for serving the built files
FROM nginx:1.25

# Copy build files to nginx
COPY --from=build /app/dist /usr/share/nginx/html

# Expose the port for the container
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]