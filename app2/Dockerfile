# Use a small official Node image
FROM node:20-alpine

# Create app directory
WORKDIR /usr/src/app

# Copy package files and install deps (leverages Docker cache)
COPY package.json ./

RUN npm install --production

# Copy app source
COPY . .

# Expose the internal port the app listens on
EXPOSE 3002

# Start the app
CMD ["npm", "start"]
