FROM node:20

USER node

RUN mkdir /home/node/code

WORKDIR /home/node/code

COPY --chown=node:node package-lock.json package.json ./

RUN npm ci

COPY --chown=node:node . .

CMD ["node", "index.js"]

# docker network create --driver=bridge app-net
# docker build --tag=my-app-with-mongo .
# docker run -d --network=app-net -p 27017:27017 --name=db mongo:7