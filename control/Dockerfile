FROM ubuntu:latest
RUN apt-get update
RUN apt-get install -y openssh-server

RUN mkdir -p /root/.ssh
RUN chmod 700 /root/.ssh

#RUN apt-get install -y iputils-ping
RUN apt-get install -y ansible
RUN sed -i 's/#   StrictHostKeyChecking ask/StrictHostKeyChecking no/' /etc/ssh/ssh_config
COPY id_rsa /root/.ssh/id_rsa
RUN chmod 600 /root/.ssh/id_rsa

COPY hosts /etc/ansible/hosts