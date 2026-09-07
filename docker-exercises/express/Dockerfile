FROM node:19

WORKDIR /app/

COPY Package.*json server.js /app/

RUN npm install 

CMD ["node", "server.js"]