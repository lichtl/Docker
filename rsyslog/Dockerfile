FROM ubuntu:latest

MAINTAINER Carsten Wache <lichtl@x-modder.de>

RUN apt-get update -qq && apt-get install -y \
	rsyslog

EXPOSE 514

RUN sed 's/#$ModLoad imudp/$ModLoad imudp/' -i /etc/rsyslog.conf
RUN sed 's/#$UDPServerRun 514/$UDPServerRun 514/' -i /etc/rsyslog.conf
RUN sed 's/#$ModLoad imtcp/$ModLoad imtcp/' -i /etc/rsyslog.conf
RUN sed 's/#$InputTCPServerRun 514/$InputTCPServerRun 514/' -i /etc/rsyslog.conf

ENTRYPOINT ["/usr/sbin/rsyslogd", "-n"]
