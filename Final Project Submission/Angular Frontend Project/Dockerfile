### STAGE 1: Build ### FROM  node  AS  buil... by Bhavya jain

### STAGE 1: Build ###
FROM node:12.18-alpine as build-step
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install
COPY . .
RUN npm run build
### STAGE 2: Run ###
FROM nginx
COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=build-step /app/dist/library-webUI /usr/share/nginx/html
EXPOSE 80
