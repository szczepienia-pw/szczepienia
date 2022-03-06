# source: https://vuejs.org/v2/cookbook/dockerize-vuejs-app.html
FROM node:lts-alpine

# install simple http server for serving static content
RUN npm install -g http-server
RUN npm install git

# make the 'app' folder the current working directory
WORKDIR /app

EXPOSE 8080
CMD [ "http-server", "dist" ]