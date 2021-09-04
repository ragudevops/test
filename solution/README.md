Commands:-

C:\Windows\system32>docker run -it -p 8080:8080 infracloudio/csvserver:latest


Unable to find image 'infracloudio/csvserver:latest' locally
latest: Pulling from infracloudio/csvserver
ae43b40a9945: Pull complete
7bb33bb2db38: Pull complete
c82d72e1bb76: Pull complete
Digest: sha256:20bc5a93fac217270fe5c88d639d82c6ecb18fc908283e046d9a3917a840ec1f
Status: Downloaded newer image for infracloudio/csvserver:latest
2021/09/04 14:49:26 error while reading the file "/csvserver/inputdata": open /csvserver/inputdata: no such file or directory

-------------------------------------------------

C:\Windows\system32>docker run -it -p 8080:8080 -v C:\git\csvserver\solution\inputfile:/csvserver/inputdata  infracloudio/csvserver:latest


2021/09/04 15:01:30 listening on ****


------------------------------------------------

C:\Windows\system32>docker ps -a


CONTAINER ID   IMAGE                           COMMAND                  CREATED          STATUS                      PORTS                                                 NAMES
dc1d330ad1a6   infracloudio/csvserver:latest   "/csvserver/csvserver"   3 minutes ago    Up 3 minutes                0.0.0.0:8080->8080/tcp, :::8080->8080/tcp, 9300/tcp   musing_lehmann

