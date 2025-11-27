##Stage-1
FROM node:18-alpine AS build

WORKDIR /usr/src/app

COPY . .

COPY package*.json ./

RUN npm install

##Stage-2
FROM node:18-alpine

WORKDIR /usr/src/app

COPY --from=build /usr/src/app .

EXPOSE 8080

CMD ["node", "server.js"]