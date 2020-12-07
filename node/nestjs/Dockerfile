FROM node:10

WORKDIR /api

COPY nest-cli.json package.json yarn.lock tsconfig.json tsconfig.build.json ./

RUN yarn

COPY src ./src

ENV PORT 3000

RUN yarn build
RUN yarn install --production

RUN rm -rf ./src

EXPOSE 3000

CMD ["yarn", "start:prod"]