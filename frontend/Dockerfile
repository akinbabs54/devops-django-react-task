# Download the slim version of node
FROM node:16-alpine

# Set the work directory to app folder. 
# We will be copying our code here
WORKDIR /frontend

#Copy package.json file in the node folder inside container
COPY package*.json ./
COPY . .

# Install the dependencies in the container
RUN npm i
RUN npm run build

# Copy the rest of the code in the container
COPY . .

ENV NODE_ENV production
# Expose the service over PORT 3000
EXPOSE 3000
CMD ["npx", "serve", "build"]
