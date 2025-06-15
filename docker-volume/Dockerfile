FROM node:20-alpine
COPY --chown=node:node . /src
WORKDIR /src
CMD ["node", "index.js"]

# docker run --rm --env DATA_PATH=/data/num.txt --mount type=volume,src=incrementor-data,target=/data incrementor