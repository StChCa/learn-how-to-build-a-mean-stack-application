
FROM node:10

# Create app directory
WORKDIR /usr/src/lafs/api

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./

RUN npm install
run npm run start
# If you are building your code for production
# RUN npm ci --only=production

# Bundle app source
COPY . .

EXPOSE 3000
#CMD [ "node", "server/server.js" ]
CMD ng serve --host 0.0.0.0