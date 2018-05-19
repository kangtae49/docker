docker exec -d $(docker run --name centos_ssh --privileged -h centos_ssh -d -v d:/:/data -p 22:22 centos_ssh /usr/sbin/init) systemctl start sshd

