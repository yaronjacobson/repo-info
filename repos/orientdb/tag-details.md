<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `orientdb`

-	[`orientdb:2.0.18`](#orientdb2018)
-	[`orientdb:2.1.25`](#orientdb2125)
-	[`orientdb:2.2.36`](#orientdb2236)
-	[`orientdb:2.2.36-spatial`](#orientdb2236-spatial)
-	[`orientdb:3.0.6`](#orientdb306)
-	[`orientdb:3.0.6-tp3`](#orientdb306-tp3)
-	[`orientdb:latest`](#orientdblatest)

## `orientdb:2.0.18`

```console
$ docker pull orientdb@sha256:713a0fd0895ddfae079e73919d46d5392386d3bb1e89c306d44f206668340d46
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:2.0.18` - linux; amd64

```console
$ docker pull orientdb@sha256:a36341d9e6d9056dbc307ab2e1da266571caf3b795920edb8b2d2d2f37e88a2d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **292.2 MB (292165854 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0e01f1ab8214e920c3e93395540fcd2e56f661c41fce44540cb8ba7df56d9b79`
-	Default Command: `["server.sh"]`

```dockerfile
# Tue, 17 Jul 2018 00:27:24 GMT
ADD file:370028dca6e8ca9ed228549d52231cf8139515cc3a14c00aaed75a60b679775f in / 
# Tue, 17 Jul 2018 00:27:24 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 03:12:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 03:13:02 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 03:13:48 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:16:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:16:56 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 06:16:57 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 06:16:58 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:16:58 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 14 Aug 2018 20:32:09 GMT
ENV JAVA_VERSION=8u181
# Tue, 14 Aug 2018 20:32:10 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Tue, 14 Aug 2018 20:32:10 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 14 Aug 2018 20:33:19 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jdk="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 14 Aug 2018 20:33:22 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 14 Aug 2018 22:32:23 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Tue, 14 Aug 2018 22:32:23 GMT
ENV ORIENTDB_VERSION=2.0.18
# Tue, 14 Aug 2018 22:32:23 GMT
ENV ORIENTDB_DOWNLOAD_MD5=9e7b7e7b6d95795b188adb4e5898a1b8
# Tue, 14 Aug 2018 22:32:23 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=f562794536bbf8ae2145f96153e58b1e5d9211b3
# Tue, 14 Aug 2018 22:32:31 GMT
RUN mkdir /orientdb &&   wget  "http://central.maven.org/maven2/com/orientechnologies/orientdb-community/$ORIENTDB_VERSION/orientdb-community-$ORIENTDB_VERSION.tar.gz"   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1  && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Tue, 14 Aug 2018 22:32:40 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 22:32:41 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Tue, 14 Aug 2018 22:32:42 GMT
WORKDIR /orientdb
# Tue, 14 Aug 2018 22:32:43 GMT
EXPOSE 2424/tcp
# Tue, 14 Aug 2018 22:32:43 GMT
EXPOSE 2480/tcp
# Tue, 14 Aug 2018 22:32:44 GMT
CMD ["server.sh"]
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
	-	`sha256:d4eee24d4dacb41c21411e0477a741655303cdc48b18a948632c31f0f3a70bb8`  
		Last Modified: Tue, 17 Jul 2018 03:54:59 GMT  
		Size: 50.1 MB (50064642 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c58988e753d7a34080c68b53f7c27229d8f8fa80b9940c34d5cf77a9a2df10a0`  
		Last Modified: Tue, 17 Jul 2018 06:55:01 GMT  
		Size: 892.4 KB (892350 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:794a04897db9ebf95b1f6430cd4d4051bd227a5f0698b18404ccd4c59e43273d`  
		Last Modified: Tue, 17 Jul 2018 06:55:00 GMT  
		Size: 246.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70fcfa476f730980d7a89f5ea34dd29c0c58e7cfe62652584e3adc38106e30ee`  
		Last Modified: Tue, 17 Jul 2018 06:54:59 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:806029475e0cd4fad9d906385681d719017da9ae333e87ab7e14d8eb8f8eae79`  
		Last Modified: Tue, 14 Aug 2018 20:39:01 GMT  
		Size: 134.0 MB (133988934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67959b355155f692cb7147128e4b67da87d6c66ec26615f174e606dfd4145cbc`  
		Last Modified: Tue, 14 Aug 2018 20:38:22 GMT  
		Size: 246.7 KB (246692 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:73e8057fac5484528d9d6c3a1eebb46994ab22e6133e4a7ebc035b020d28e2ce`  
		Last Modified: Tue, 14 Aug 2018 22:33:30 GMT  
		Size: 46.6 MB (46586540 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:2.1.25`

```console
$ docker pull orientdb@sha256:4fb192e0aee47ef9f14bc0a1f17fd82184a2fe85f3428fd06147b299c766338c
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:2.1.25` - linux; amd64

```console
$ docker pull orientdb@sha256:41f942cc7f8fe6838c743e7bd1f05b84274ccffb6d2b89a6955b12ab333c65d1
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **104.2 MB (104155793 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a4c7f83ea73ae6cf1085f9d96b9bb13521e329de4d959fae5cc3023eb4d92f7d`
-	Default Command: `["server.sh"]`

```dockerfile
# Fri, 06 Jul 2018 14:14:06 GMT
ADD file:25f61d70254b9807a40cd3e8d820f6a5ec0e1e596de04e325f6a33810393e95a in / 
# Fri, 06 Jul 2018 14:14:06 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 00:34:53 GMT
ENV LANG=C.UTF-8
# Wed, 11 Jul 2018 00:34:54 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 11 Jul 2018 00:34:54 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_VERSION=8u171
# Wed, 11 Jul 2018 00:34:55 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 11 Jul 2018 00:35:00 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 11 Jul 2018 02:09:35 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Wed, 11 Jul 2018 02:09:35 GMT
ENV ORIENTDB_VERSION=2.1.25
# Wed, 11 Jul 2018 02:09:35 GMT
ENV ORIENTDB_DOWNLOAD_MD5=054da3fb7c56e7822b2af116966576ce
# Wed, 11 Jul 2018 02:09:35 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=b7b08242b40117ac8eb9a201f8704bde839dfcb8
# Wed, 11 Jul 2018 02:09:37 GMT
RUN apk add --update tar     && rm -rf /var/cache/apk/*
# Wed, 11 Jul 2018 02:09:46 GMT
RUN mkdir /orientdb &&   wget  "http://central.maven.org/maven2/com/orientechnologies/orientdb-community/$ORIENTDB_VERSION/orientdb-community-$ORIENTDB_VERSION.tar.gz"   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1  && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Wed, 11 Jul 2018 02:09:46 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 11 Jul 2018 02:09:46 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Wed, 11 Jul 2018 02:09:47 GMT
WORKDIR /orientdb
# Wed, 11 Jul 2018 02:09:47 GMT
EXPOSE 2424/tcp
# Wed, 11 Jul 2018 02:09:47 GMT
EXPOSE 2480/tcp
# Wed, 11 Jul 2018 02:09:48 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:8e3ba11ec2a2b39ab372c60c16b421536e50e5ce64a0bc81765c2e38381bcff6`  
		Last Modified: Fri, 06 Jul 2018 04:15:58 GMT  
		Size: 2.2 MB (2206542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:311ad0da45338842480bf25c6e6b7bb133b7b8cf709c3470db171ec370da5539`  
		Last Modified: Wed, 11 Jul 2018 00:37:45 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df312c74ce16f20eeb87b5640db9b1579a53534bd3e9f3de1e916fc62744bcf4`  
		Last Modified: Wed, 11 Jul 2018 00:38:02 GMT  
		Size: 70.6 MB (70581383 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ad644bdd33b77bd242bee8330b882a92a186c35c7b1ebf0b88cedb4a4a531d9`  
		Last Modified: Wed, 11 Jul 2018 02:12:06 GMT  
		Size: 279.7 KB (279663 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f25e182054f4ca15021e166f9a555defaba9edd787c9848b4d45e965cd84db7a`  
		Last Modified: Wed, 11 Jul 2018 02:12:10 GMT  
		Size: 31.1 MB (31087966 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:2.2.36`

```console
$ docker pull orientdb@sha256:45255ace6c5f1edd61b0168bd32fca7b2c6ea7f12f89d7ccffd708e5e2520aec
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:2.2.36` - linux; amd64

```console
$ docker pull orientdb@sha256:1759ec09da15cbba7c8380cddfbb2c25a5e2d4f3f32f728d6879d83671e7a7df
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **120.0 MB (120027511 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:82787e68d9b0830c9f0abb26cef85578e81e7b3d116ace0c576b6227843e1355`
-	Default Command: `["server.sh"]`

```dockerfile
# Fri, 06 Jul 2018 14:14:06 GMT
ADD file:25f61d70254b9807a40cd3e8d820f6a5ec0e1e596de04e325f6a33810393e95a in / 
# Fri, 06 Jul 2018 14:14:06 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 00:34:53 GMT
ENV LANG=C.UTF-8
# Wed, 11 Jul 2018 00:34:54 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 11 Jul 2018 00:34:54 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_VERSION=8u171
# Wed, 11 Jul 2018 00:34:55 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 11 Jul 2018 00:35:00 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 11 Jul 2018 02:09:35 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Wed, 11 Jul 2018 02:10:01 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Fri, 13 Jul 2018 18:20:15 GMT
ENV ORIENTDB_VERSION=2.2.36
# Fri, 13 Jul 2018 18:20:15 GMT
ENV ORIENTDB_DOWNLOAD_MD5=0db280d733a000b75adb1e52c819497b
# Fri, 13 Jul 2018 18:20:16 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=ce5527f027d40cb32af5537130316d5ea81588db
# Fri, 13 Jul 2018 18:20:16 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-community/2.2.36/orientdb-community-2.2.36.tar.gz
# Fri, 13 Jul 2018 18:20:17 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Fri, 13 Jul 2018 18:20:21 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Fri, 13 Jul 2018 18:20:21 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Fri, 13 Jul 2018 18:20:22 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Fri, 13 Jul 2018 18:20:22 GMT
WORKDIR /orientdb
# Fri, 13 Jul 2018 18:20:23 GMT
EXPOSE 2424/tcp
# Fri, 13 Jul 2018 18:20:23 GMT
EXPOSE 2480/tcp
# Fri, 13 Jul 2018 18:20:23 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:8e3ba11ec2a2b39ab372c60c16b421536e50e5ce64a0bc81765c2e38381bcff6`  
		Last Modified: Fri, 06 Jul 2018 04:15:58 GMT  
		Size: 2.2 MB (2206542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:311ad0da45338842480bf25c6e6b7bb133b7b8cf709c3470db171ec370da5539`  
		Last Modified: Wed, 11 Jul 2018 00:37:45 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df312c74ce16f20eeb87b5640db9b1579a53534bd3e9f3de1e916fc62744bcf4`  
		Last Modified: Wed, 11 Jul 2018 00:38:02 GMT  
		Size: 70.6 MB (70581383 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:24f24a3fc68869abdb6c85c5091ee13c964c5dc83eb34678aa27cb9916cec9d7`  
		Last Modified: Fri, 13 Jul 2018 18:22:16 GMT  
		Size: 766.0 KB (765975 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:271f35ad3bda372ba9b99e7b0b2c280ead9de0ad6eb5a47bfb1ee001662cd894`  
		Last Modified: Fri, 13 Jul 2018 18:22:22 GMT  
		Size: 46.5 MB (46473372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:2.2.36-spatial`

```console
$ docker pull orientdb@sha256:2364e7a79252d02ad26a785bafb1f0b1fb0003f37b7851d126ff3f0b9680e558
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:2.2.36-spatial` - linux; amd64

```console
$ docker pull orientdb@sha256:100834e84e19ee4a4dc744443bb789030e4b6df2111727e628c4ca18fbf0ae3e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **121.2 MB (121230107 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7f66cf73f4f1c65cdecb54971e0300e4474c45f8ba27f79fc24191874c8caca6`
-	Default Command: `["server.sh"]`

```dockerfile
# Fri, 06 Jul 2018 14:14:06 GMT
ADD file:25f61d70254b9807a40cd3e8d820f6a5ec0e1e596de04e325f6a33810393e95a in / 
# Fri, 06 Jul 2018 14:14:06 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 00:34:53 GMT
ENV LANG=C.UTF-8
# Wed, 11 Jul 2018 00:34:54 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 11 Jul 2018 00:34:54 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_VERSION=8u171
# Wed, 11 Jul 2018 00:34:55 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 11 Jul 2018 00:35:00 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 11 Jul 2018 02:09:35 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Wed, 11 Jul 2018 02:10:01 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Fri, 13 Jul 2018 18:20:15 GMT
ENV ORIENTDB_VERSION=2.2.36
# Fri, 13 Jul 2018 18:20:15 GMT
ENV ORIENTDB_DOWNLOAD_MD5=0db280d733a000b75adb1e52c819497b
# Fri, 13 Jul 2018 18:20:16 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=ce5527f027d40cb32af5537130316d5ea81588db
# Fri, 13 Jul 2018 18:20:16 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-community/2.2.36/orientdb-community-2.2.36.tar.gz
# Fri, 13 Jul 2018 18:20:17 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Fri, 13 Jul 2018 18:20:21 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Fri, 13 Jul 2018 18:20:21 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Fri, 13 Jul 2018 18:20:22 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Fri, 13 Jul 2018 18:20:22 GMT
WORKDIR /orientdb
# Fri, 13 Jul 2018 18:20:23 GMT
EXPOSE 2424/tcp
# Fri, 13 Jul 2018 18:20:23 GMT
EXPOSE 2480/tcp
# Fri, 13 Jul 2018 18:20:23 GMT
CMD ["server.sh"]
# Fri, 13 Jul 2018 18:20:37 GMT
ENV ORIENTDB_DOWNLOAD_SPATIAL_MD5=0b027f68e3dac4f03357d5f3064ec0f3
# Fri, 13 Jul 2018 18:20:38 GMT
ENV ORIENTDB_DOWNLOAD_SPATIAL_SHA1=8f3adeddbad4d7f5436f4e2cdd418294135cd824
# Fri, 13 Jul 2018 18:20:38 GMT
ENV ORIENTDB_DOWNLOAD_SPATIAL_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-spatial/2.2.36/orientdb-spatial-2.2.36-dist.jar
# Fri, 13 Jul 2018 18:20:39 GMT
RUN wget $ORIENTDB_DOWNLOAD_SPATIAL_URL     && echo "$ORIENTDB_DOWNLOAD_SPATIAL_MD5 *orientdb-spatial-$ORIENTDB_VERSION-dist.jar" | md5sum -c -     && echo "$ORIENTDB_DOWNLOAD_SPATIAL_SHA1 *orientdb-spatial-$ORIENTDB_VERSION-dist.jar" | sha1sum -c -     && mv orientdb-spatial-*-dist.jar /orientdb/lib/
```

-	Layers:
	-	`sha256:8e3ba11ec2a2b39ab372c60c16b421536e50e5ce64a0bc81765c2e38381bcff6`  
		Last Modified: Fri, 06 Jul 2018 04:15:58 GMT  
		Size: 2.2 MB (2206542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:311ad0da45338842480bf25c6e6b7bb133b7b8cf709c3470db171ec370da5539`  
		Last Modified: Wed, 11 Jul 2018 00:37:45 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df312c74ce16f20eeb87b5640db9b1579a53534bd3e9f3de1e916fc62744bcf4`  
		Last Modified: Wed, 11 Jul 2018 00:38:02 GMT  
		Size: 70.6 MB (70581383 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:24f24a3fc68869abdb6c85c5091ee13c964c5dc83eb34678aa27cb9916cec9d7`  
		Last Modified: Fri, 13 Jul 2018 18:22:16 GMT  
		Size: 766.0 KB (765975 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:271f35ad3bda372ba9b99e7b0b2c280ead9de0ad6eb5a47bfb1ee001662cd894`  
		Last Modified: Fri, 13 Jul 2018 18:22:22 GMT  
		Size: 46.5 MB (46473372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae7b192473976bfbc97c661bce404aba994e83aff1a633d170b942bd374c3cd9`  
		Last Modified: Fri, 13 Jul 2018 18:22:43 GMT  
		Size: 1.2 MB (1202596 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:3.0.6`

```console
$ docker pull orientdb@sha256:e122d8f3ce9fd259a324314337317646afee327191c30518c1bc864ac70cc1f6
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:3.0.6` - linux; amd64

```console
$ docker pull orientdb@sha256:d56c2a2c5058a0510e8984015c8722abc0a74cbab636541e9a047b76281a18ad
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **110.0 MB (109966167 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:353a74b2c5e4b2dffa1b6e7c45ed3704b4f43799ee766428d34c7476cd365fae`
-	Default Command: `["server.sh"]`

```dockerfile
# Fri, 06 Jul 2018 14:14:06 GMT
ADD file:25f61d70254b9807a40cd3e8d820f6a5ec0e1e596de04e325f6a33810393e95a in / 
# Fri, 06 Jul 2018 14:14:06 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 00:34:53 GMT
ENV LANG=C.UTF-8
# Wed, 11 Jul 2018 00:34:54 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 11 Jul 2018 00:34:54 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_VERSION=8u171
# Wed, 11 Jul 2018 00:34:55 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 11 Jul 2018 00:35:00 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 11 Jul 2018 02:09:35 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Wed, 11 Jul 2018 02:10:01 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Tue, 14 Aug 2018 17:24:42 GMT
ENV ORIENTDB_VERSION=3.0.6
# Tue, 14 Aug 2018 17:24:43 GMT
ENV ORIENTDB_DOWNLOAD_MD5=90d88e4d3e3932c1a99ba7155ec52b09
# Tue, 14 Aug 2018 17:24:43 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=7b0b6a07638b93cbaf53c7dafb2a9e6c451dc135
# Tue, 14 Aug 2018 17:24:43 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-community/3.0.6/orientdb-community-3.0.6.tar.gz
# Tue, 14 Aug 2018 17:24:45 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Tue, 14 Aug 2018 17:24:49 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Tue, 14 Aug 2018 17:24:50 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Tue, 14 Aug 2018 17:24:50 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Tue, 14 Aug 2018 17:24:51 GMT
WORKDIR /orientdb
# Tue, 14 Aug 2018 17:24:51 GMT
EXPOSE 2424/tcp
# Tue, 14 Aug 2018 17:24:52 GMT
EXPOSE 2480/tcp
# Tue, 14 Aug 2018 17:24:52 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:8e3ba11ec2a2b39ab372c60c16b421536e50e5ce64a0bc81765c2e38381bcff6`  
		Last Modified: Fri, 06 Jul 2018 04:15:58 GMT  
		Size: 2.2 MB (2206542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:311ad0da45338842480bf25c6e6b7bb133b7b8cf709c3470db171ec370da5539`  
		Last Modified: Wed, 11 Jul 2018 00:37:45 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df312c74ce16f20eeb87b5640db9b1579a53534bd3e9f3de1e916fc62744bcf4`  
		Last Modified: Wed, 11 Jul 2018 00:38:02 GMT  
		Size: 70.6 MB (70581383 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:680bd0afa0cc903df47e37f4ea00f73c1f57849dbb55bed3847eb00fdf29c325`  
		Last Modified: Tue, 14 Aug 2018 17:26:23 GMT  
		Size: 766.0 KB (765982 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:47b8f2ef59bc6a04e6902deb0b1340c38c2669fa7088f48f66954d6272ebfa7e`  
		Last Modified: Tue, 14 Aug 2018 17:26:30 GMT  
		Size: 36.4 MB (36412021 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:3.0.6-tp3`

```console
$ docker pull orientdb@sha256:3a0729d072ef8a9540e209e628bbfa407e475c641499cc814364afee0a9c1543
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:3.0.6-tp3` - linux; amd64

```console
$ docker pull orientdb@sha256:bf8e67537ca7e6b8ff50aece274040961121a76d2200027d31bd0e72f722bd7a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **137.3 MB (137251188 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a6a887312676a349cb59a3592fee6507aad1f30b1a08faee1d5f8e4ff10e1375`
-	Default Command: `["server.sh"]`

```dockerfile
# Fri, 06 Jul 2018 14:14:06 GMT
ADD file:25f61d70254b9807a40cd3e8d820f6a5ec0e1e596de04e325f6a33810393e95a in / 
# Fri, 06 Jul 2018 14:14:06 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 00:34:53 GMT
ENV LANG=C.UTF-8
# Wed, 11 Jul 2018 00:34:54 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 11 Jul 2018 00:34:54 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_VERSION=8u171
# Wed, 11 Jul 2018 00:34:55 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 11 Jul 2018 00:35:00 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 11 Jul 2018 02:09:35 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Wed, 11 Jul 2018 02:10:01 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Tue, 14 Aug 2018 17:24:42 GMT
ENV ORIENTDB_VERSION=3.0.6
# Tue, 14 Aug 2018 17:25:25 GMT
ENV ORIENTDB_DOWNLOAD_MD5=1ea59a1ceb83bc64e2f1e9c06f2d87a9
# Tue, 14 Aug 2018 17:25:25 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=349b8480c57473fdf41a12de8fb96e4473c4283b
# Tue, 14 Aug 2018 17:25:25 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-tp3/3.0.6/orientdb-tp3-3.0.6.tar.gz
# Tue, 14 Aug 2018 17:25:27 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Tue, 14 Aug 2018 17:25:35 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-tp3-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-tp3-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-tp3-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-tp3-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Tue, 14 Aug 2018 17:25:53 GMT
ADD file:99b7a1625594810d4a6ad850d8e45ce20c6e5e95127b6a7316cae65e7aa03c13 in /orientdb/config 
# Tue, 14 Aug 2018 17:25:53 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Tue, 14 Aug 2018 17:25:53 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Tue, 14 Aug 2018 17:25:54 GMT
WORKDIR /orientdb
# Tue, 14 Aug 2018 17:25:54 GMT
EXPOSE 2424/tcp
# Tue, 14 Aug 2018 17:25:55 GMT
EXPOSE 2480/tcp
# Tue, 14 Aug 2018 17:25:55 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:8e3ba11ec2a2b39ab372c60c16b421536e50e5ce64a0bc81765c2e38381bcff6`  
		Last Modified: Fri, 06 Jul 2018 04:15:58 GMT  
		Size: 2.2 MB (2206542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:311ad0da45338842480bf25c6e6b7bb133b7b8cf709c3470db171ec370da5539`  
		Last Modified: Wed, 11 Jul 2018 00:37:45 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df312c74ce16f20eeb87b5640db9b1579a53534bd3e9f3de1e916fc62744bcf4`  
		Last Modified: Wed, 11 Jul 2018 00:38:02 GMT  
		Size: 70.6 MB (70581383 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11c2ce2b24e2996b714d26b0eb27d3645b5dc47b676adc61e166f6e759c077b8`  
		Last Modified: Tue, 14 Aug 2018 17:27:14 GMT  
		Size: 766.0 KB (765982 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3e61b06e650ee7694370aac56fc9829ca7855b2847868010d4f9c61439f3d9f`  
		Last Modified: Tue, 14 Aug 2018 17:27:22 GMT  
		Size: 63.7 MB (63695662 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f661b0c2bc64bb28be68df982c8eb4db4c7cb5717b5db787cfe4d44a655e177`  
		Last Modified: Tue, 14 Aug 2018 17:27:13 GMT  
		Size: 1.4 KB (1380 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:latest`

```console
$ docker pull orientdb@sha256:e122d8f3ce9fd259a324314337317646afee327191c30518c1bc864ac70cc1f6
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:latest` - linux; amd64

```console
$ docker pull orientdb@sha256:d56c2a2c5058a0510e8984015c8722abc0a74cbab636541e9a047b76281a18ad
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **110.0 MB (109966167 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:353a74b2c5e4b2dffa1b6e7c45ed3704b4f43799ee766428d34c7476cd365fae`
-	Default Command: `["server.sh"]`

```dockerfile
# Fri, 06 Jul 2018 14:14:06 GMT
ADD file:25f61d70254b9807a40cd3e8d820f6a5ec0e1e596de04e325f6a33810393e95a in / 
# Fri, 06 Jul 2018 14:14:06 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 00:34:53 GMT
ENV LANG=C.UTF-8
# Wed, 11 Jul 2018 00:34:54 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 11 Jul 2018 00:34:54 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 11 Jul 2018 00:34:54 GMT
ENV JAVA_VERSION=8u171
# Wed, 11 Jul 2018 00:34:55 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Wed, 11 Jul 2018 00:35:00 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 11 Jul 2018 02:09:35 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Wed, 11 Jul 2018 02:10:01 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Tue, 14 Aug 2018 17:24:42 GMT
ENV ORIENTDB_VERSION=3.0.6
# Tue, 14 Aug 2018 17:24:43 GMT
ENV ORIENTDB_DOWNLOAD_MD5=90d88e4d3e3932c1a99ba7155ec52b09
# Tue, 14 Aug 2018 17:24:43 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=7b0b6a07638b93cbaf53c7dafb2a9e6c451dc135
# Tue, 14 Aug 2018 17:24:43 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-community/3.0.6/orientdb-community-3.0.6.tar.gz
# Tue, 14 Aug 2018 17:24:45 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Tue, 14 Aug 2018 17:24:49 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Tue, 14 Aug 2018 17:24:50 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Tue, 14 Aug 2018 17:24:50 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Tue, 14 Aug 2018 17:24:51 GMT
WORKDIR /orientdb
# Tue, 14 Aug 2018 17:24:51 GMT
EXPOSE 2424/tcp
# Tue, 14 Aug 2018 17:24:52 GMT
EXPOSE 2480/tcp
# Tue, 14 Aug 2018 17:24:52 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:8e3ba11ec2a2b39ab372c60c16b421536e50e5ce64a0bc81765c2e38381bcff6`  
		Last Modified: Fri, 06 Jul 2018 04:15:58 GMT  
		Size: 2.2 MB (2206542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:311ad0da45338842480bf25c6e6b7bb133b7b8cf709c3470db171ec370da5539`  
		Last Modified: Wed, 11 Jul 2018 00:37:45 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df312c74ce16f20eeb87b5640db9b1579a53534bd3e9f3de1e916fc62744bcf4`  
		Last Modified: Wed, 11 Jul 2018 00:38:02 GMT  
		Size: 70.6 MB (70581383 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:680bd0afa0cc903df47e37f4ea00f73c1f57849dbb55bed3847eb00fdf29c325`  
		Last Modified: Tue, 14 Aug 2018 17:26:23 GMT  
		Size: 766.0 KB (765982 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:47b8f2ef59bc6a04e6902deb0b1340c38c2669fa7088f48f66954d6272ebfa7e`  
		Last Modified: Tue, 14 Aug 2018 17:26:30 GMT  
		Size: 36.4 MB (36412021 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
