FROM node:20-alpine

USER node

WORKDIR /home/node/code

COPY --chown=node:node package.json package-lock.json ./

RUN npm ci

COPY --chown=node . .

CMD ["node", "index.js" ]