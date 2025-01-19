FROM node:latest

LABEL maintainer=pbhat

# Create app directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# Clone game source code
RUN git clone https://github.com/prasadrevens/pacman_jan25 .

# Install app dependencies
RUN npm install

# Expose port 8080
EXPOSE 8080

# Install the @splunk/otel package
RUN npm install @splunk/otel
# Set appropriate permissions
RUN chmod -R go+r /usr/src/app/node_modules/@splunk/otel

# Run container
CMD ["npm", "start"]
#CMD ["node", "-r @splunk/otel/instrument", "server.js"]
