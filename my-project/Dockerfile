FROM node:20

RUN useradd -ms /bin/bash lolcat

USER lolcat

WORKDIR /home/lolcat/code

COPY --chown=lolcat index.js .

CMD ["node", "index.js" ]