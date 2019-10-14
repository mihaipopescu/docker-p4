FROM phusion/baseimage:latest

# Ensure that the apt tool doesn't require any user interaction
ENV DEBIAN_FRONTEND=noninteractive

ENV HELIX_VERSION=2019.1-1845413~xenial

RUN apt-get update && \
    apt-get install -yq --no-install-recommends -q wget && \
    wget -qO - https://package.perforce.com/perforce.pubkey | apt-key add - && \
    echo 'deb http://package.perforce.com/apt/ubuntu xenial release' > /etc/apt/sources.list.d/perforce.list && \
    apt-get update

RUN apt-get install -yq --no-install-recommends helix-git-connector=${HELIX_VERSION} && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENV P4PORT=perforce:1666
ENV P4USER=swarm
ENV P4PASSWD=swarm
ENV GCUSERP4PASSW=gconn-user
ENV GRAPHDEPOT=git 

# Expose default HTTPS port
EXPOSE 443

ADD ./run.sh /

CMD ["/run.sh"]
