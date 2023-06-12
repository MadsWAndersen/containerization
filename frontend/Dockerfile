# # Build stage
# FROM node:14 as build-stage
# WORKDIR /app
# COPY package*.json ./
# RUN npm install
# COPY . .
# RUN npm run build

# # Production stage
# FROM nginx as production-stage
# COPY --from=build-stage /app/dist /usr/share/nginx/html
# EXPOSE 80
# CMD ["nginx", "-g", "daemon off;"]


# Use an official Node.js runtime as a parent image
# FROM node:16-alpine

# # Set the working directory to /app
# WORKDIR /app

# # Copy package.json and package-lock.json to the container
# COPY package*.json ./

# # Install app dependencies
# RUN npm install

# # Copy the rest of the application code to the container
# COPY . .

# # Expose port 8080
# EXPOSE 4000

# # Start the 
# CMD [ "npm", "run", "dev" ]


FROM node:16-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 80

CMD [ "npm", "run", "dev" ]