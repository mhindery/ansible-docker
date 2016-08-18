FROM python:2.7
RUN apt-get update
RUN apt-get install -y python
RUN apt-get install -y openssh-server

RUN mkdir -p /root/.ssh
RUN chmod 700 /root/.ssh


RUN echo 'root:root' | chpasswd
RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
COPY id_rsa.pub /root/.ssh/authorized_keys
RUN chmod 644 /root/.ssh/authorized_keys
ENTRYPOINT service ssh restart && bash