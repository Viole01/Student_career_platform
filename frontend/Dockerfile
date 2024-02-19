# -- Build stage
FROM node:18 AS build

WORKDIR /app

COPY . .

RUN npm install

RUN npm run build


# -- Deploying Stage
FROM nginx:alpine

COPY --from=tmfrontend /app/build /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
