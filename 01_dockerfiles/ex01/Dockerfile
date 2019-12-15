FROM debian
ENV TS3SERVER_LICENSE accept
RUN apt -y update && apt -y upgrade \
	&& apt -y install wget \
	&& apt -y install bzip2
RUN wget https://files.teamspeak-services.com/releases/server/3.6.1/teamspeak3-server_linux_amd64-3.6.1.tar.bz2
RUN bzip2 -d teamspeak3-server_linux_amd64-3.6.1.tar.bz2
RUN tar xf teamspeak3-server_linux_amd64-3.6.1.tar
WORKDIR /teamspeak3-server_linux_amd64
EXPOSE 9987/udp
CMD ["./ts3server"]
#command to run : docker container run -it -p 9987:9987/udp teamspeak
