# SYSLOG-NG

The following ports are exposed:
* Syslog UDP: 514
* Syslog TCP: 601
* Syslog TLS: 6514

# Using default configuration

    sudo docker run -it -p 514:514 -p 601:601 --name syslog-ng lichtl/syslog-ng:latest

# Using custom syslog-ng configuration

    sudo docker run -it -v "$PWD/syslog-ng.conf":/etc/syslog-ng/syslog-ng.conf lichtl/syslog-ng:latest
