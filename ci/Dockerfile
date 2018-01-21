FROM ubuntu:16.04

# Refresh repositories
RUN apt-get update

# Install base tool
RUN apt-get install -y \
      git \
      apt-transport-https \
      ca-certificates \
      curl \
      software-properties-common

# Add Docker’s official GPG key:
RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -

# Verify key fingerprint
RUN apt-key fingerprint 0EBFCD88

# Add stable repository
RUN add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

# Refresh repositories again for docker installation
RUN apt-get update

# Install docker
RUN apt-get install -y docker-ce

# Install docker-compose
RUN curl -L https://github.com/docker/compose/releases/download/1.18.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

# Apply executable permissions to the binary
RUN chmod +x /usr/local/bin/docker-compose

CMD ["bash"]
