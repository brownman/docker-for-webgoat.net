# webgoat.net

```bash
FROM mono
COPY . /usr/local/app/
RUN apt-get update && apt-get upgrade -y && apt-get install -y mono-xsp4 sqlite3
RUN cd /usr/local/app/ && xbuild
CMD cd /usr/local/app/WebGoat && xsp4
```


```
docker build -t goat .

docker run -t -p 8888:9000 webgoat
```

```
setup sqlite db by supplying path to local folder
```

- https://github.com/davevs/dvxte/blob/master/todo/webgoatnet
- https://github.com/jerryhoff/WebGoat.NET/pull/7
- http://www.frameloss.org/2012/05/23/installing-webgoat-net-using-apache-on-ubuntu/
