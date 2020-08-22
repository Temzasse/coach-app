FROM node:12-alpine

# Add psql for `wait-for-db.sh` script
RUN apk --update add postgresql-client

ENV PORT 3000

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY package*.json /usr/src/app/
RUN npm install

COPY . /usr/src/app

RUN npm run next:build
EXPOSE 3000

RUN chmod +x ./wait-for-db.sh

# This does not work...
CMD ["./wait-for-db.sh", "npm", "run", "start"]

# Use below command to get the app running
# CMD ["npm", "run", "next:dev"]