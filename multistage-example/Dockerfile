FROM node:14 as build-stage

WORKDIR /app

COPY ./app/package*.json ./
RUN npm install

COPY ./app .

RUN npm run build

FROM nginx:alpine

COPY --from=build-stage /app/build /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
