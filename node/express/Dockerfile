FROM node:latest

WORKDIR /usr/app

COPY package.json .
RUN yarn
COPY . .

RUN yarn add global typescript
ENV TZ=America/Sao_Paulo
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
CMD ["yarn", "start"]
