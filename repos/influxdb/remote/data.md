## `influxdb:data`

```console
$ docker pull influxdb@sha256:1e070e49291266a08b201298d039421768276004f8dd010c0a98aefecf3c0adf
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `influxdb:data` - linux; amd64

```console
$ docker pull influxdb@sha256:3a63a5c231916ad9d9783df06b9bed26ff3895a4ae81ba9f53a238ae90d5c79c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **86.9 MB (86926707 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5e5ed905d3504f5b072859c78c624d82ea1ce7fb7fc7017cd589c7ccf0ef8b82`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["influxd"]`

```dockerfile
# Tue, 17 Jul 2018 00:27:24 GMT
ADD file:370028dca6e8ca9ed228549d52231cf8139515cc3a14c00aaed75a60b679775f in / 
# Tue, 17 Jul 2018 00:27:24 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 03:12:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 03:13:02 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 13:54:39 GMT
RUN set -ex &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done
# Mon, 06 Aug 2018 19:52:25 GMT
ENV INFLUXDB_VERSION=1.6.1-c1.6.1
# Mon, 06 Aug 2018 19:52:32 GMT
RUN wget --no-verbose https://dl.influxdata.com/enterprise/releases/influxdb-data_${INFLUXDB_VERSION}_amd64.deb.asc &&     wget --no-verbose https://dl.influxdata.com/enterprise/releases/influxdb-data_${INFLUXDB_VERSION}_amd64.deb &&     gpg --batch --verify influxdb-data_${INFLUXDB_VERSION}_amd64.deb.asc influxdb-data_${INFLUXDB_VERSION}_amd64.deb &&     dpkg -i influxdb-data_${INFLUXDB_VERSION}_amd64.deb &&     rm -f influxdb-data_${INFLUXDB_VERSION}_amd64.deb*
# Mon, 06 Aug 2018 19:52:32 GMT
COPY file:a7fc957fd6465cc132b5d41618061e4ac55bd347b790cd87cc496ab4f67a274b in /etc/influxdb/influxdb.conf 
# Mon, 06 Aug 2018 19:52:33 GMT
EXPOSE 8086/tcp
# Mon, 06 Aug 2018 19:52:33 GMT
VOLUME [/var/lib/influxdb]
# Mon, 06 Aug 2018 19:52:33 GMT
COPY file:efb819384a9e7a972c15df74e1d18c7d6296e633a7c533def9a6d400b69468fc in /entrypoint.sh 
# Mon, 06 Aug 2018 19:52:34 GMT
COPY file:44e0050f3b04248a6900eace944c581b13b4ad9af1e5cfb91d837cb5e24356e6 in /init-influxdb.sh 
# Mon, 06 Aug 2018 19:52:34 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Mon, 06 Aug 2018 19:52:35 GMT
CMD ["influxd"]
```

-	Layers:
	-	`sha256:55cbf04beb7001d222c71bfdeae780bda19d5cb37b8dbd65ff0d3e6a0b9b74e6`  
		Last Modified: Tue, 17 Jul 2018 00:42:31 GMT  
		Size: 45.3 MB (45310044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1607093a898cc241de8712e4361dcd907898fff35b945adca42db3963f3827b3`  
		Last Modified: Tue, 17 Jul 2018 03:53:34 GMT  
		Size: 10.7 MB (10740168 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a8ea045c9261c180a34df19cfc9bb3c3f28f29b279bf964ee801536e8244f2f`  
		Last Modified: Tue, 17 Jul 2018 03:53:32 GMT  
		Size: 4.3 MB (4336107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c8b66fe64951b691526fc65d6c67b05aba22d733dab6c55d0fcae893bdaaf8e`  
		Last Modified: Tue, 17 Jul 2018 13:57:05 GMT  
		Size: 2.9 KB (2887 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c7b6429d766e63e2f5ad4f3a32a097b6b8fdf21f0259db9d24c941a656a5c26`  
		Last Modified: Mon, 06 Aug 2018 19:57:12 GMT  
		Size: 26.5 MB (26535849 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12e66adccadb56b5c902a9ec6cbb4fe26092ebf252adb3e6d8c2f10f3ed8c521`  
		Last Modified: Mon, 06 Aug 2018 19:57:00 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:74a984e12037f6780feca6dcf2a2a795ca432487f5b5239105f79ea14ff06bf1`  
		Last Modified: Mon, 06 Aug 2018 19:57:00 GMT  
		Size: 250.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85accaa5a6e929a6a166f2c11af20873453cb8af7041a35d3931b96207fbc788`  
		Last Modified: Mon, 06 Aug 2018 19:57:00 GMT  
		Size: 1.2 KB (1162 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
