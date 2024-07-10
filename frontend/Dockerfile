# # # # Frontend Dockerfile
# # # FROM node:16.18

# # # WORKDIR /app

# # # COPY package*.json ./
# # # RUN npm install

# # # COPY . .

# # # RUN npm run build

# # # FROM nginx:alpine
# # # COPY --from=0 /app/build /usr/share/nginx/html

# # # EXPOSE 3000

# # # CMD ["nginx", "-g", "daemon off;"]

# # # Stage 1: Build the React app
# # FROM node:18 AS build

# # # Set the working directory
# # WORKDIR /app

# # # Copy package.json and package-lock.json
# # COPY package*.json ./

# # # Install dependencies
# # RUN npm install

# # # Copy the rest of the application code
# # COPY . .

# # # Build the React app
# # RUN npm run build

# # # Stage 2: Serve the React app with Nginx
# # FROM nginx:alpine

# # # Copy the build output to Nginx's html directory
# # COPY --from=build /app/build /usr/share/nginx/html

# # # Expose port 80
# # EXPOSE 80

# # # Start Nginx
# # CMD ["nginx", "-g", "daemon off;"]# Stage 1: Build the React app
# FROM node:18 AS build

# # Set the working directory
# WORKDIR /app

# # Copy package.json and package-lock.json
# COPY package*.json ./

# # Install dependencies
# RUN npm install

# # Copy the rest of the application code
# COPY . .

# # Build the React app
# RUN npm run build

# # Stage 2: Serve the React app with Nginx
# FROM nginx:alpine

# # Copy the build output to Nginx's html directory
# COPY --from=build /app/build /usr/share/nginx/html

# # Expose port 80
# EXPOSE 80

# # Start Nginx
# CMD ["nginx", "-g", "daemon off;"]

# Use a Node.js base image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package.json
COPY package.json ./
COPY ./package-lock.json ./

# Install dependencies
RUN npm install

# Copy your frontend code
COPY . .
COPY ./ /app/

# Expose port (adjust if your app uses a different port)
EXPOSE 3000

# Command to run the development server (replace with your actual command)
CMD [ "npm", "run", "dev", "--", "--host" ]

