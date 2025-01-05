FROM node:18

WORKDIR /app

COPY Jenkins/simple-node-server/package.json .

COPY Jenkins/simple-node-server/package-lock.json .

RUN npm install

COPY Jenkins/simple-node-server/* ./

EXPOSE 5000

CMD [ "node", "index.js" ]