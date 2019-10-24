FROM debian:latest

ENV TS3SERVER_LICENSE=accept

EXPOSE 9987/udp 10111 3033

WORKDIR /home/TS3

RUN apt-get update && apt-get upgrade -y && \
	apt-get install -y wget bzip2 && \
	wget https://files.teamspeak-services.com/releases/server/3.9.1/teamspeak3-server_linux_amd64-3.9.1.tar.bz2 && \
	tar xvf teamspeak3-server_linux_amd64-3.9.1.tar.bz2 && \
	cd teamspeak3-server_linux_amd64 && mv * /home/TS3 && cd .. && rm -rf teamspeak3-server_linux_amd64-3.9.1.tar.bz2 && \
	touch .ts3server_license_accepted 

ENTRYPOINT sh ts3server_minimal_runscript.sh

