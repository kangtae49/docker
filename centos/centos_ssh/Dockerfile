FROM centos:latest
MAINTAINER KangTae Kim <kangtae49@gmail.com>


RUN yum -y update
#RUN yum -y reinstall glibc-common
RUN yum -y install openssh-server
RUN mkdir /var/run/sshd
RUN ssh-keygen -q -t rsa1 -N '' -f /etc/ssh/ssh_host_key
RUN ssh-keygen -q -t rsa -N '' -f /etc/ssh/ssh_host_rsa_key
RUN ssh-keygen -q -t dsa -N '' -f /etc/ssh/ssh_host_dsa_key
RUN ssh-keygen -q -t ecdsa -N '' -f /etc/ssh/ssh_host_ecdsa_key
RUN ssh-keygen -A

EXPOSE 22
RUN ssh-keygen -q -t rsa -N '' -f ~/.ssh/id_rsa

# [local]
# ssh-keygen
# cp ~/.ssh/id_rsa.pub ./authorized_keys
ADD ./authorized_keys /root/.ssh/authorized_keys 
RUN chmod 644 /root/.ssh/authorized_keys

RUN echo "export LANG=en_US.UTF-8" >> /root/.bash_profile
RUN echo "export LANGUAGE=en_US.UTF-8" >> /root/.bash_profile
RUN echo "export LC_ALL=en_US.UTF-8" >> /root/.bash_profile
#ENV LANG en_US.UTF-8
#ENV LANGUAGE en_US.UTF-8
#ENV LC_ALL en_US.UTF-8
#ADD ./locale.conf /etc/locale.conf

VOLUME ["/data"]

#ADD ./start.sh /data/start.sh
#RUN chmod 755 /data/start.sh
#ENTRYPOINT ["/usr/sbin/sshd", "-D"]


