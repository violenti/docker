# Debian Jessie with  Oracle Java 7
FROM debian:stable-slim

#Add repository non-free for debian stable and install software-properties-common

RUN echo "deb http://deb.debian.org/debian stable-updates non-free" >> /etc/apt/sources.list  && \
    echo "deb http://deb.debian.org/debian stable  non-free" >> /etc/apt/sources.list && \
    apt-get update
    # && apt-get install -y  software-properties-common debconf-utils


#Install jdk7 from webupd8team
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886 && \
    echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu xenial main" >> /etc/apt/sources.list && \
    echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu xenial main" >> /etc/apt/sources.list && \
    #add-apt-repository -y  "deb http://ppa.launchpad.net/webupd8team/java/ubuntu xenial main" && \
    mkdir /usr/share/man/man1/ && \
    echo "oracle-java7-installer shared/accepted-oracle-license-v1-1 select true" | debconf-set-selections && \
    apt-get update && \
    apt-get install -y oracle-java7-installer && \
    rm -r /var/cache/oracle-jdk7-installer
RUN apt-get purge && apt-get autoremove -y
