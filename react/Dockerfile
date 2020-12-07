FROM node:alpine as builder

WORKDIR /usr/src/app

COPY package.json yarn.lock ./
COPY . ./

RUN yarn
RUN yarn build

FROM nginx:1.15.2-alpine

COPY --from=builder /usr/src/app/build /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
