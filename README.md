# webgoat.net

FROM mono
COPY . /usr/local/app/
RUN apt-get update && apt-get upgrade -y && apt-get install -y mono-xsp4 sqlite3
RUN cd /usr/local/app/ && xbuild
CMD cd /usr/local/app/WebGoat && xsp4
 @ProZachJ
 
ProZachJ commented on 16 Dec 2016
Also the launch command needs a port mapping

docker run -t -p 8888:9000 webgoat
