# Base image for backend
FROM node:21 

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install required dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .
COPY .env.sample .env
# Expose the port the app runs on
EXPOSE 5000

# Command to start the backend server
CMD ["npm", "start"]
