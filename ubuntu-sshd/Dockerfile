FROM ubuntu:17.04

RUN apt-get update \
	&& apt-get install -y openssh-server


RUN mkdir /var/run/sshd

RUN mkdir /root/.ssh
RUN touch /root/.ssh/authorized_keys
RUN chmod 0600 /root/.ssh/*

RUN echo 'root:root' | chpasswd

RUN sed -i 's/#\?PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -i 's/#PubkeyAuthentication yes/PubkeyAuthentication yes/' /etc/ssh/sshd_config
RUN sed -i 's|#AuthorizedKeysFile .ssh/authorized_keys|AuthorizedKeysFile .ssh/authorized_keys|' /etc/ssh/sshd_config


RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

ENV NOTVISIBLE "in users profile"

RUN echo "export VISIBLE=now" >> /etc/profile

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]

