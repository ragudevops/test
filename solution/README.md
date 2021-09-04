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

C:\Windows\system32>docker logs ed3c2049069c

2021/09/04 15:10:59 listening on ****

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

C:\git\csvserver\solution>docker-compose up

Creating solution_db_1  ... done
Creating solution_web_1 ... done
Attaching to solution_web_1, solution_db_1
web_1  | 2021/09/04 15:48:53 error while reading the file "/csvserver/inputdata": open /csvserver/inputdata: no such file or directory
solution_web_1 exited with code 1
db_1   | level=info ts=2021-09-04T15:48:56.304Z caller=main.go:315 msg="No time or size retention was set so using the default time retention" duration=15d
db_1   | level=info ts=2021-09-04T15:48:56.323Z caller=main.go:353 msg="Starting Prometheus" version="(version=2.22.0, branch=HEAD, revision=0a7fdd3b76960808c3a91d92267c3d815c1bc354)"
db_1   | level=info ts=2021-09-04T15:48:56.323Z caller=main.go:358 build_context="(go=go1.15.3, user=root@6321101b2c50, date=20201015-12:29:59)"
db_1   | level=info ts=2021-09-04T15:48:56.323Z caller=main.go:359 host_details="(Linux 5.10.16.3-microsoft-standard-WSL2 #1 SMP Fri Apr 2 22:23:49 UTC 2021 x86_64 ffc145a69f84 localdomain)"
db_1   | level=info ts=2021-09-04T15:48:56.324Z caller=main.go:360 fd_limits="(soft=1048576, hard=1048576)"
db_1   | level=info ts=2021-09-04T15:48:56.324Z caller=main.go:361 vm_limits="(soft=unlimited, hard=unlimited)"
db_1   | level=info ts=2021-09-04T15:48:56.409Z caller=main.go:712 msg="Starting TSDB ..."
db_1   | level=info ts=2021-09-04T15:48:56.411Z caller=web.go:516 component=web msg="Start listening for connections" address=0.0.0.0:9090
db_1   | level=info ts=2021-09-04T15:48:56.504Z caller=head.go:642 component=tsdb msg="Replaying on-disk memory mappable chunks if any"
db_1   | level=info ts=2021-09-04T15:48:56.504Z caller=head.go:656 component=tsdb msg="On-disk memory mappable chunks replay completed" duration=70.711µs
db_1   | level=info ts=2021-09-04T15:48:56.504Z caller=head.go:662 component=tsdb msg="Replaying WAL, this may take a while"
db_1   | level=info ts=2021-09-04T15:48:56.530Z caller=head.go:714 component=tsdb msg="WAL segment loaded" segment=0 maxSegment=0
db_1   | level=info ts=2021-09-04T15:48:56.530Z caller=head.go:719 component=tsdb msg="WAL replay completed" checkpoint_replay_duration=81.081µs wal_replay_duration=25.763058ms total_replay_duration=25.949987ms
db_1   | level=info ts=2021-09-04T15:48:56.545Z caller=main.go:732 fs_type=EXT4_SUPER_MAGIC
db_1   | level=info ts=2021-09-04T15:48:56.545Z caller=main.go:735 msg="TSDB started"
db_1   | level=info ts=2021-09-04T15:48:56.545Z caller=main.go:861 msg="Loading configuration file" filename=/etc/prometheus/prometheus.yml
db_1   | level=info ts=2021-09-04T15:48:56.765Z caller=main.go:892 msg="Completed loading of configuration file" filename=/etc/prometheus/prometheus.yml totalDuration=220.04632ms remote_storage=73.73µs web_handler=979ns query_engine=1.973µs scrape=82.426395ms scrape_sd=388.808µs notify=136.04304ms notify_sd=248.413µs rules=5.117µs
db_1   | level=info ts=2021-09-04T15:48:56.765Z caller=main.go:684 msg="Server is ready to receive web requests."




