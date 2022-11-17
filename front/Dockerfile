FROM node:alpine as builder

WORKDIR '/app/front'

COPY package.json .

RUN npm i

COPY . .

RUN npm run build

FROM nginx

COPY --from=builder /app/front/build /usr/share/nginx/html