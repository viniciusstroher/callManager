FROM debian:jessie
MAINTAINER Vinicius Stroher <viniciusferreirawk@gmail.com>

COPY sources.list /etc/apt/sources.list

RUN apt-get update && \ 
	apt-get -y upgrade && \
	apt-get -y install aptitude

RUN aptitude -y install unixodbc-dev libtool make tar wget build-essential
RUN aptitude -y install linux-headers
RUN aptitude -y install vim php5 apache2 gcc g++ ncurses-dev libxml2 libxml2-dev 
RUN aptitude -y install openssl openssh-server openssh-client libnewt-dev zlib1g zlib1g-dev unixodbc

RUN uname -a


RUN wget https://downloads.asterisk.org/pub/telephony/asterisk/asterisk-13-current.tar.gz && \
	tar -xzvf dahdi-linux-2.11.1.tar.gz -C /usr/src/ && \
	tar -xzvf dahdi-tools-2.11.1.tar.gz -C /usr/src/ && \
	tar -xzvf libpri-1.6.0.tar.gz -C /usr/src/ && \
	tar -xzvf asterisk-13-current.tar.gz -C /usr/src

#make dos dahdi

RUN cd /usr/src/asterisk-13-current/ && \
	./contrib/scripts/install_prereq install && \
	make clean && \
	./configure && \
	make menuselect && \
	make && \
	make install && \
	make config && \
	make install-logrotate

EXPOSE 80

