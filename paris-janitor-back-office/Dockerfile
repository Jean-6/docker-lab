# Step 1
# Use official node image as base image
FROM node:14 AS build

# Config main workspace
WORKDIR /app

# Copy
COPY package*.json ./

# Install app dependencies into container
RUN npm install

# Copy others app files
COPY . .

# Let build angular app
RUN npm run build --prod

# Step 2

# Use NGINX image to serve app
FROM nginx:alpine

# Copy build files of angular app to Nginx directory
COPY --from=build /app/dist/paris-janitor-back-office /usr/share/nginx/html

# Expose port on which nginx execute
EXPOSE 80

# Launch Nginx
CMD ["nginx", "-g", "daemon off;"]

# Copy
COPY --from=build /usr/app/dist/paris-janitor-back-office /usr/share/nginx/html/

# Expose port 80
EXPOSE 80

# Command to launch Nginx
CMD ["nginx","-g","daemon off;"]
