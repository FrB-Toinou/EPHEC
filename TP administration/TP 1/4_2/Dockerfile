FROM ubuntu/bind9

RUN apt update && apt install -y nano net-tools

EXPOSE 53/tcp
EXPOSE 53/udp

COPY named.conf.options /etc/bind/named.conf.options

