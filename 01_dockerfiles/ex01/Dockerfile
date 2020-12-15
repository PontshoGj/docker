FROM debian

ENV TS3SERVER_LICENSE=accept

EXPOSE 9987/udp 10011 30033

RUN apt-get update -y && apt-get upgrade -y && \
    apt-get -y install wget bzip2 ca-certificates && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    apt-get autoremove -y && \
    apt-get clean

RUN wget http://dl.4players.de/ts/releases/3.12.1/teamspeak3-server_linux_amd64-3.12.1.tar.bz2

RUN tar xvf *.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh


#sudo docker run --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 server
#sudo docker build -t server .