# Start with a node image
FROM node:14 

# Set working directory to /app so that the following commands will be executed in /app
WORKDIR /app

# Copy code into the /app folder
COPY . /app

# Install dependencies in /app
RUN npm install

# Expose port --> this is only for documentation purposes
EXPOSE 80

# RUN => command to run at 'image level'
# CMD => command to run at 'container level'. Always ran when a container starts

# Run server
CMD ["node", "server.js"]

