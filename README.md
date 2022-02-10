docker-oracle-xe-10g
====================

(based on the work done by Wei-Ming Wu <wnameless@gmail.com> on
[wnameless/docker-oracle-xe-11g](https://github.com/wnameless/docker-oracle-xe-11g)

Oracle Express Edition 10g Release 2 (10.2.0.1) 32-bit on Debian 7.0 Wheezy.


### Installation
```
docker pull dkfi/docker-oracle-xe-10g
```

Run with 22, 1521 and 8080 ports opened:
```
docker run -d -p 49160:22 -p 49161:1521 -p 49162:8080 dkfi/docker-oracle-xe-10g
```

Connect database with following setting:
```
hostname: localhost
port: 49161
sid: xe
username: system
password: oracle
```

For example, connect to database with sqlplus:
```
sqlplus system/oracle@//localhost:49161/xe
```

Password for SYS & SYSTEM
```
oracle
```

Login by SSH
```
ssh root@localhost -p 49160
password: admin
```

Login to web administrator on a browser:
```
http://localhost:49162/apex
```


## Additional Information For Running on Linux or macOs

Make sure docker is installed first, to install docker please head to [Docker macOs Install](https://docs.docker.com/desktop/mac/install/) or [Docker Linux Install](https://docs.docker.com/engine/install/)

1. Clone this repo `git clone https://github.com/liehart/docker-oracle-xe-10g.git`
2. Change dir to cloned repo `cd docker-oracle-xe-10g`
3. Build image `docker build -t oracle-docker .`
4. Run container `docker run -d -p 49160:22 -p 49161:1521 -p 49162:8080 oracle-docker`
5. SSH to Container `ssh root@localhost -p 49160` Use password `admin` if asked
6. After successfully connected, login to `sqlplus` with `sqlplus system/oracle`

Additional command:
1. To stop container `docker stop oracle-docker`
2. To run container again `docker start oracle-docker`