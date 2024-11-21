# Step 1
#Use official node image as base image
FROM node:20-alpine AS build
#Config main workspace
WORKDIR /usr/app
#Copy
COPY . /usr/app/
#Install global command (Angular CLI) into container
RUN npm install -g @angular/cli
#Install dependencies (to install package.json dependencies)
RUN npm install
#let build angular app
RUN ng build --configuration production

#Step 2

FROM nginx:latest
COPY --from=build /usr/app/dist/paris-janitor-back-office /usr/share/nginx/html/
EXPOSE 80
# command to launch Nginx
CMD ["nginx","-g","daemon off;"]
