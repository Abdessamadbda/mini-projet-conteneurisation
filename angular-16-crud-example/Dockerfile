# phase 1
FROM node:16-alpine as builder
WORKDIR /app
COPY ["package.json", "package-lock.json", "./"]
RUN npm install
COPY . .
RUN npm run build
# phase 2
FROM nginx:1.23.2-alpine as production
ENV NODE_ENV production
COPY --from=builder /app/dist/angular-16-crud /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
