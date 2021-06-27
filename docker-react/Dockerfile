FROM node:alpine as builder

WORKDIR /usr/src/app

COPY package.json ./

RUN npm install

COPY ./ ./

RUN npm run build

## 운영환경을 위한 nginx 기본포트 80
FROM nginx

COPY --from=builder /usr/src/app/build /usr/share/nginx/html

