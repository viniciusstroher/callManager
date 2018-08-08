FROM debian:jessie
MAINTAINER Vinicius Stroher <viniciusferreirawk@gmail.com>

COPY sources.list /etc/apt/sources.list

RUN apt-get update && \ 
	apt-get -y upgrade && \
	apt-get -y install aptitude

RUN aptitude -y install unixodbc-dev libtool make tar wget build-essential
RUN aptitude -y install vim php5 apache2 gcc g++ ncurses-dev libxml2 libxml2-dev 
RUN aptitude -y install openssl openssh-server openssh-client libnewt-dev zlib1g zlib1g-dev unixodbc

#linux-headers-`uname -r`
RUN wget http://downloads.asterisk.org/pub/telephony/asterisk/asterisk-13.5.0.tar.gz && \
	wget http://downloads.asterisk.org/pub/telephony/libpri/libpri-1.4-current.tar.gz && \
	wget http://downloads.asterisk.org/pub/telephony/dahdi-linux-complete/dahdi-linux-complete-current.tar.gz && \
	tar -xvf libpri-1.4-current.tar.gz && \
	tar -xvf dahdi-linux-complete-current.tar.gz && \
	tar -xvf asterisk-13.5.0.tar.gz

EXPOSE 80

