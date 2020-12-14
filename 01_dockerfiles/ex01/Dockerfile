FROM debian

ENV TS3SERVER_LICENSE: accept

EXPOSE 9987/udp 10011 30033

RUN apt-get update -y && apt-get upgrade -y && \
    apt-get -y install wget bzip2 ca-certificates && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    apt-get autoremove -y && \
    apt-get clean

RUN wget http://dl.4players.de/ts/releases/3.12.1/teamspeak3-server_linux_amd64-3.12.1.tar.bz2

RUN tar jxf teamspeak3-server_linux_amd64-$TSV.tar.bz2 && \
    mv teamspeak3-server_linux_amd64 /opt/teamspeak && \
    rm teamspeak3-server_linux_amd64-$TSV.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh
