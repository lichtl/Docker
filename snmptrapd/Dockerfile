FROM ubuntu:latest

MAINTAINER Carsten Wache <lichtl@x-modder.de>

RUN apt-get update -qq && apt-get install -y \
	snmptrapd

EXPOSE 162/udp

RUN mkdir /opt/MIB

ENV MIBDIR /opt/MIB


ENTRYPOINT ["/usr/sbin/snmptrapd", "-f", "-Lf /var/log/snmptrapd.log", "--disable-Authorization=yes", "-M+/opt/MIB"]
