FROM node

WORKDIR /app

COPY package.json .

RUN npm i

COPY . .

EXPOSE 80

ENV MONGO_INITDB_ROOT_USERNAME=root
ENV MONGO_INITDB_ROOT_PASSWORD=secret

CMD [ "node","app.js"]