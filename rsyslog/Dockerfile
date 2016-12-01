FROM ubuntu:latest

MAINTAINER Carsten Wache <lichtl@x-modder.de>

RUN apt-get update -qq && apt-get install -y \
	rsyslog

EXPOSE 514

RUN sed 's/#module(load="imudp")/module(load="imudp")/' -i /etc/rsyslog.conf
RUN sed 's/#input(type="imudp" port="514")/input(type="imudp" port="514")/' -i /etc/rsyslog.conf
RUN sed 's/#module(load="imtcp")/module(load="imtcp")/' -i /etc/rsyslog.conf
RUN sed 's/#input(type="imtcp" port="514")/input(type="imtcp" port="514")/' -i /etc/rsyslog.conf

RUN sed 's/$KLogPermitNonKernelFacility on/#$KLogPermitNonKernelFacility on/' -i /etc/rsyslog.conf

RUN sed 's/module(load="imuxsock")/#module(load="imuxsock")/' -i /etc/rsyslog.conf
RUN sed 's/module(load="imklog")/#module(load="imklog")/' -i /etc/rsyslog.conf

RUN rm /etc/rsyslog.d/50-default.conf

RUN echo "*.* /var/log/remote.log" > /etc/rsyslog.d/100-rsyslogd.conf

ENTRYPOINT ["/usr/sbin/rsyslogd", "-n"]
