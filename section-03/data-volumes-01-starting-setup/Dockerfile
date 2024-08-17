FROM node

WORKDIR /app

COPY package.json .

RUN npm install

# Still needed for production container, since we won't use "live volumes" in production
COPY . .

EXPOSE 80

CMD [ "npm", "start" ]