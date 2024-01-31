<<<<<<< HEAD
FROM node:lts AS development

WORKDIR /code
COPY package.json /code/package.json
COPY package-lock.json /code/package-lock.json

RUN npm ci

COPY . /code

ENV CI=true
ENV PORT=3000

ENTRYPOINT [ "npm", "start" ]
=======
# syntax=docker/dockerfile:1.4

FROM node:14-alpine AS builder
WORKDIR /code

COPY frontend/package*.json ./
RUN npm install

COPY frontend/ .
RUN npm run build

FROM nginx:alpine
COPY --from=builder /code/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]

>>>>>>> Initial commit
