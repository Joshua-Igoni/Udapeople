FROM node:14.8.0-alpine3.12
WORKDIR /front
COPY package.json ./
COPY package-lock.json ./
RUN npm install
COPY . ./
EXPOSE 3000
CMD [ "npm", "start" ]