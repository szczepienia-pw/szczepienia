FROM ubuntu

# install packages
RUN apt update && apt upgrade
RUN echo 'y' | apt install ssh
RUN echo 'y' | apt install npm

# configure npm
RUN npm cache clean --force
RUN npm install -g n
RUN n 16.14.0

# configure ssh
RUN ssh-keygen -A
RUN echo 'Port 22' >> /etc/ssh/sshd_config
RUN echo 'AddressFamily any' >> /etc/ssh/sshd_config
RUN echo 'HostKey /etc/ssh/ssh_host_rsa_key' >> /etc/ssh/sshd_config
RUN echo 'PermitRootLogin yes' >> /etc/ssh/sshd_config
RUN echo 'PermitEmptyPasswords yes' >> /etc/ssh/sshd_config
RUN passwd -d root
RUN service ssh start

# expose port 22
EXPOSE 22

# run sshd
CMD ["/usr/sbin/sshd","-D"]