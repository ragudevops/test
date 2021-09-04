Commands:-

C:\Windows\system32>docker run -it -p 9393:9393 infracloudio/csvserver:latest

Unable to find image 'infracloudio/csvserver:latest' locally
latest: Pulling from infracloudio/csvserver
ae43b40a9945: Pull complete
7bb33bb2db38: Pull complete
c82d72e1bb76: Pull complete
Digest: sha256:20bc5a93fac217270fe5c88d639d82c6ecb18fc908283e046d9a3917a840ec1f
Status: Downloaded newer image for infracloudio/csvserver:latest
2021/09/04 14:49:26 error while reading the file "/csvserver/inputdata": open /csvserver/inputdata: no such file or directory

-------------------------------------------------

C:\Windows\system32>docker run -it -p 9393:9393 -v C:\git\csvserver\solution\inputfile:/csvserver/inputdata  infracloudio/csvserver:latest

2021/09/04 15:10:59 listening on ****


------------------------------------------------

C:\Windows\system32>docker ps -a


CONTAINER ID   IMAGE                           COMMAND                  CREATED              STATUS              PORTS                                                 NAMES
ed3c2049069c   infracloudio/csvserver:latest   "/csvserver/csvserver"   About a minute ago   Up About a minute   9300/tcp, 0.0.0.0:9393->9393/tcp, :::9393->9393/tcp   practical_ramanujan


------------------------------------------------

C:\Windows\system32>docker pull prom/prometheus:v2.22.0

v2.22.0: Pulling from prom/prometheus
76df9210b28c: Pull complete
559be8e06c14: Pull complete
97170ed2e56a: Pull complete
4a6c0b5646ca: Pull complete
f6776fcc9f18: Pull complete
7eed139cfec6: Pull complete
c0c3c15c8e94: Pull complete
ad6e678f5b25: Pull complete
9a8236411762: Pull complete
0cfb39b876cc: Pull complete
ffe345581c7a: Pull complete
033c1a7f7349: Pull complete
Digest: sha256:60190123eb28250f9e013df55b7d58e04e476011911219f5cedac3c73a8b74e6
Status: Downloaded newer image for prom/prometheus:v2.22.0
docker.io/prom/prometheus:v2.22.0


------------------------------------------------






