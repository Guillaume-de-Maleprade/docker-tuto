FROM node

WORKDIR /app

COPY package.json .

RUN npm install

# Still needed for production container, since we won't use "live volumes" in production
COPY . .

ARG DEFAULT_PORT=80

ENV PORT $DEFAULT_PORT

EXPOSE $PORT

CMD [ "npm", "start" ]