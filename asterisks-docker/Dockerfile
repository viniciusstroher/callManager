FROM debian:jessie
MAINTAINER Vinicius Stroher <viniciusferreirawk@gmail.com>

COPY sources.list /etc/apt/sources.list

RUN apt-get update && \ 
	apt-get -y upgrade


RUN aptitude -y install vim php5 apache2 mysql-server mysql-client gcc g++ ncurses-dev libxml2 libxml2-dev \ linux-headers-`uname -r` openssl openssh-server openssh-client libnewt-dev zlib1g zlib1g-dev unixodbc \ unixodbc-dev libtool make tar wget build-essential


EXPOSE 80

