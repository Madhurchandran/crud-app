FROM node:latest AS build

WORKDIR /usr/src/app

COPY package*.json ./

COPY . .

RUN npm install

EXPOSE 8081

RUN npm run build

FROM nginx:stable-alpine

COPY --from=build /usr/src/app/dist/angular-15-crud /usr/share/nginx/html

EXPOSE 8081

CMD ["nginx", "-g", "daemon off;"]