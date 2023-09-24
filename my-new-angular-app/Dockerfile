FROM node:18-bullseye-slim AS build
COPY . /app
WORKDIR /app
RUN npm install && npm run build && rm -rf node_modules/

FROM nginx:1.17.1-alpine
COPY --from=build /app/dist/my-new-angular-app /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
COPY /dist/my-new-angular-app /usr/share/nginx/html
EXPOSE 80
