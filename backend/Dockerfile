# Stage 1: Build and Test Stage
FROM node:21 AS backend-builder

# Set working directory
WORKDIR /app

# Copy source code
COPY . .

# Install dependencies
RUN npm install

# Run tests
RUN npm run test


# Stage 2: Production Stage
FROM node:21-slim

# Set working directory
WORKDIR /app

# Copy built app from the builder stage
COPY --from=backend-builder /app .

# Copy environment file
COPY .env.docker .env

# Expose port
EXPOSE 5000

# Command to run the app
CMD ["npm", "start"]
