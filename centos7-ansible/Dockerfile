FROM centos:7

RUN yum install -y \
  openssh \
  openssh-clients \
  epel-release \
  && yum install -y \
  ansible \
  && yum clean all \
  && mkdir /root/.ssh \
  && chmod 0700 /root/.ssh

COPY id_rsa /root/.ssh/id_rsa
RUN chmod 0700 /root/.ssh \
  && chmod 0600 /root/.ssh/id_rsa \
  && echo -e "\tStrictHostKeyChecking no" >> /etc/ssh/ssh_config

CMD ["/bin/bash"]
