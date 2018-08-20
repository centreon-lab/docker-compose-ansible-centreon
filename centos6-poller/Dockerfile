FROM centos:6

RUN yum install -y \
  openssh \
  openssh-server \
  wget \
  gnupg \
  && mkdir /root/.ssh \
  && chmod 0700 /root/.ssh

RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -q -C '' -N '' \
  && ssh-keygen -t dsa -f /etc/ssh/ssh_host_dsa_key -q -C '' -N '' \
  && ssh-keygen -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key -q -C '' -N '' \
  && echo 'root:change123' | chpasswd \
  && sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

COPY id_rsa.pub /root/.ssh/authorized_keys
RUN chmod 0600 /root/.ssh/authorized_keys

CMD ["/bin/bash"]
