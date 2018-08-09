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
	tar -xzvf asterisk-13-current.tar.gz -C /usr/src

RUN	 cd /usr/src/asterisk-13.22.0/ && \ ./contrib/scripts/install_prereq install
RUN	 cd /usr/src/asterisk-13.22.0/ && \ make clean

RUN cd /usr/src/asterisk-13.22.0/ && \
	./configure 1 > /dev/null

RUN cd /usr/src/asterisk-13.22.0/ && \
	make menuselect && \
	make && \
	make install && \
	make config && \
	make install-logrotate && \
	make samples

EXPOSE 80

