FROM node

WORKDIR /app

COPY package*.json /app

RUN npm install

COPY . /app

# DOCUMENTATION forgotten ;)
EXPOSE 3000

CMD ["node", "server.js"]