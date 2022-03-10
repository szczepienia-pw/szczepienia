# source: https://vuejs.org/v2/cookbook/dockerize-vuejs-app.html
FROM node:lts-alpine

# install simple http server for serving static content and git, bash and ssh needed to perform jenkins operations
RUN npm install -g http-server
RUN apk update && apk upgrade && apk add --no-cache bash git openssh

# configure SSH
RUN ssh-keygen -A
RUN echo 'Port 22 \nAddressFamily any \nHostKey /etc/ssh/ssh_host_rsa_key \nPermitRootLogin yes \nPermitEmptyPasswords yes'
RUN passwd -d root

# make the 'app' folder the current working directory
WORKDIR /app

EXPOSE 8080
# CMD [ "http-server", "dist" ]
CMD [ "/bin/bash -c /usr/bin/sshd" ]