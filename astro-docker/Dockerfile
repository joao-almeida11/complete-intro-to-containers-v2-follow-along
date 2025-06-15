# install step
FROM node:24 AS node-installer
RUN mkdir /install && chown node:node /install
WORKDIR /install
USER node
COPY --chown=node:node package.json package-lock.json ./
RUN npm ci

# build step
FROM node:24 AS node-builder
RUN mkdir /build && chown node:node /build
WORKDIR /build
USER node
COPY --from=node-installer --chown=node:node /install ./
COPY --chown=node:node . .
RUN npm run build

# # production step
FROM nginx:alpine
COPY ./nginx/nginx.conf /etc/nginx/nginx.conf
COPY --from=node-builder /build/dist /usr/share/nginx/html

# commands to run this
# docker build --tag astro-docker .
# docker run -it -p 8080:8080 --name my-astro-docker astro-docker