FROM node:16-alpine as build
WORKDIR /app
COPY . /app
RUN npm install
RUN npm run build


FROM nginx:1.16.0-alpine
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
