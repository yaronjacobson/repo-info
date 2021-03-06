## `spiped:latest`

```console
$ docker pull spiped@sha256:e6ff2285cd6e73c2fcd192c644a406b8a8b1500e5e265fd2feca06f8f0682a8a
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `spiped:latest` - linux; amd64

```console
$ docker pull spiped@sha256:d61dac69d1635142e68d01617d7042864e286ed7d14142984461d793461718f5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **30.2 MB (30247263 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4c13f5071c92dbb57e06b824dcc1ab347c57737966b320f31692aa2103f69a8f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Tue, 17 Jul 2018 00:28:04 GMT
ADD file:919939fa022472751b717443eea9f1d7ab5c0723f1f3a6b776d3b83d22bde818 in / 
# Tue, 17 Jul 2018 00:28:04 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 09:49:16 GMT
RUN groupadd -r spiped &&	useradd -r -g spiped spiped
# Tue, 17 Jul 2018 09:49:23 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	apt-get update &&	apt-get install -y libssl1.1 --no-install-recommends &&	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 09:49:23 GMT
ENV SPIPED_VERSION=1.6.0
# Tue, 17 Jul 2018 09:49:23 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Tue, 17 Jul 2018 09:49:24 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Tue, 17 Jul 2018 09:50:05 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	buildDeps='libssl-dev libc-dev gcc make curl ca-certificates' &&	apt-get update && apt-get install -y $buildDeps --no-install-recommends &&	rm -rf /var/lib/apt/lists/* &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apt-get purge -y --auto-remove $buildDeps
# Tue, 17 Jul 2018 09:50:05 GMT
VOLUME [/spiped]
# Tue, 17 Jul 2018 09:50:05 GMT
WORKDIR /spiped
# Tue, 17 Jul 2018 09:50:06 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Tue, 17 Jul 2018 09:50:06 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 17 Jul 2018 09:50:06 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:be8881be8156e4068e611fe956aba2b9593ebd953be14fb7feea6d0659aa3abe`  
		Last Modified: Tue, 17 Jul 2018 00:44:17 GMT  
		Size: 22.5 MB (22485906 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8fe4e2ed65ea6a02627fefaa3679f2e448c4474c936d04d252eb4b573d190b6f`  
		Last Modified: Tue, 17 Jul 2018 09:50:33 GMT  
		Size: 1.7 KB (1744 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a249268d54b299a169df5e1461346c598ace67113eeef169de25f37c146b3bff`  
		Last Modified: Tue, 17 Jul 2018 09:50:35 GMT  
		Size: 1.9 MB (1881434 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cf092d9af97463bac2bf26fd4e89458f5776f73d1f545cd08266cc90b1f92458`  
		Last Modified: Tue, 17 Jul 2018 09:50:36 GMT  
		Size: 5.9 MB (5877735 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:808fa7a3d76b5646428565f3acb8487070a24c919a5aa17d951c87b9d6dac81b`  
		Last Modified: Tue, 17 Jul 2018 09:50:35 GMT  
		Size: 95.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e3a3acce00aee3f66d14f8c8df8bfe28e6a0f0c3b523eecb9809e947c8b2f8a8`  
		Last Modified: Tue, 17 Jul 2018 09:50:33 GMT  
		Size: 349.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `spiped:latest` - linux; arm variant v5

```console
$ docker pull spiped@sha256:726c6e0953e783e78c69e4d7aad0bf5beb63cf0a527da021f1eca9659e637e65
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **27.7 MB (27739306 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9daa7f1d8ec4e1ebe05bd58f1974bae2d0eca0dcdbea75449a9d773fca2d2c94`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Tue, 17 Jul 2018 08:56:27 GMT
ADD file:60830ba735048c6cbecbc75b83364ad442e1e5ee691ef74dad4eb07f720f8919 in / 
# Tue, 17 Jul 2018 08:56:29 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 11:39:13 GMT
RUN groupadd -r spiped &&	useradd -r -g spiped spiped
# Tue, 17 Jul 2018 11:39:22 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	apt-get update &&	apt-get install -y libssl1.1 --no-install-recommends &&	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 11:39:22 GMT
ENV SPIPED_VERSION=1.6.0
# Tue, 17 Jul 2018 11:39:22 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Tue, 17 Jul 2018 11:39:23 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Tue, 17 Jul 2018 11:39:59 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	buildDeps='libssl-dev libc-dev gcc make curl ca-certificates' &&	apt-get update && apt-get install -y $buildDeps --no-install-recommends &&	rm -rf /var/lib/apt/lists/* &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apt-get purge -y --auto-remove $buildDeps
# Tue, 17 Jul 2018 11:40:00 GMT
VOLUME [/spiped]
# Tue, 17 Jul 2018 11:40:00 GMT
WORKDIR /spiped
# Tue, 17 Jul 2018 11:40:01 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Tue, 17 Jul 2018 11:40:01 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 17 Jul 2018 11:40:01 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:235e2c34c6b727f2b00aae7eed907f84338b4002c487e0caaa123a50334c0810`  
		Last Modified: Tue, 17 Jul 2018 09:09:00 GMT  
		Size: 21.2 MB (21162647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75493df0edd4d489efad9691b1cdc3403582978e9d70599f6d94e2ef942ea58a`  
		Last Modified: Tue, 17 Jul 2018 11:40:18 GMT  
		Size: 1.7 KB (1734 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:662c5c60dfa07bfe644e15c0fcbc05e9a92d0f9f6893ddb0bade3821b813759c`  
		Last Modified: Tue, 17 Jul 2018 11:40:17 GMT  
		Size: 1.6 MB (1622965 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ceaec47a781711f455d32b29099e7438e0a3a551737b7e89e7248f9d44ba5f4`  
		Last Modified: Tue, 17 Jul 2018 11:40:19 GMT  
		Size: 5.0 MB (4951484 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:916595e04ad0f34d98bf46ba608016d28d79b77b09b90518d3fe02c4a394b498`  
		Last Modified: Tue, 17 Jul 2018 11:40:17 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28f2ce29f68f2527f755ba67743c748346d05b72414cd86f50c3bc623b5131cb`  
		Last Modified: Tue, 17 Jul 2018 11:40:17 GMT  
		Size: 347.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `spiped:latest` - linux; arm variant v7

```console
$ docker pull spiped@sha256:0883d6b9c0605e4d5832be6f44c5ac262ee8a2ebb53cc28c087037fb4064848e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **25.5 MB (25544351 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:40ae539699e99100030d61e6772dde19c164201301ce4381cf0c6a0cbdd94b7a`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Tue, 17 Jul 2018 12:06:02 GMT
ADD file:00cfe29a37b88b6eacba9ac7c46483798b55e0aaaa9a4a3cbbd097606fd23268 in / 
# Tue, 17 Jul 2018 12:06:03 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 15:54:04 GMT
RUN groupadd -r spiped &&	useradd -r -g spiped spiped
# Tue, 17 Jul 2018 15:54:11 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	apt-get update &&	apt-get install -y libssl1.1 --no-install-recommends &&	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 15:54:12 GMT
ENV SPIPED_VERSION=1.6.0
# Tue, 17 Jul 2018 15:54:12 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Tue, 17 Jul 2018 15:54:12 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Tue, 17 Jul 2018 15:54:42 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	buildDeps='libssl-dev libc-dev gcc make curl ca-certificates' &&	apt-get update && apt-get install -y $buildDeps --no-install-recommends &&	rm -rf /var/lib/apt/lists/* &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apt-get purge -y --auto-remove $buildDeps
# Tue, 17 Jul 2018 15:54:43 GMT
VOLUME [/spiped]
# Tue, 17 Jul 2018 15:54:43 GMT
WORKDIR /spiped
# Tue, 17 Jul 2018 15:54:44 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Tue, 17 Jul 2018 15:54:44 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 17 Jul 2018 15:54:44 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:e07de503944f9c1ea958f38d01af058a6e01c94d6df8bf8af06ed73fcf57793e`  
		Last Modified: Tue, 17 Jul 2018 12:18:34 GMT  
		Size: 19.3 MB (19270183 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b25eb79a8391407331bd4e11616c4896c371aa257582599a27fc25f90ccff36`  
		Last Modified: Tue, 17 Jul 2018 15:55:00 GMT  
		Size: 1.7 KB (1737 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:597056bfa84180788fefbfda5cb48e1622f6fcc6c27dd47dc687cf78bdbc80b0`  
		Last Modified: Tue, 17 Jul 2018 15:55:01 GMT  
		Size: 1.6 MB (1564299 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:726a0d2066a21b22cd1e4580c138c94f709b9b83efe8715927c96e3f16243ad0`  
		Last Modified: Tue, 17 Jul 2018 15:55:02 GMT  
		Size: 4.7 MB (4707655 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c89904d601dc1d6d02a49a9c85b807051e42f413ca7967c5334e56bd497da46e`  
		Last Modified: Tue, 17 Jul 2018 15:55:00 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22b8577b2658225630e2cbaa29035ff60b3df99ce2720361a4a1b757f54e6959`  
		Last Modified: Tue, 17 Jul 2018 15:55:00 GMT  
		Size: 348.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `spiped:latest` - linux; arm64 variant v8

```console
$ docker pull spiped@sha256:315b8127aa32294c767da3a6970b5c1256359af8fa7077d568a7b744066e579f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **27.2 MB (27185209 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b34d89374bef0d37133c293bef8c2182ef5c474be7a8ea984a2cb4e0ff38619a`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Tue, 17 Jul 2018 08:48:06 GMT
ADD file:b6ea996ffd5aa4dade8cb1d721c2716614c03110d98683aca206c7ab52fcb9e5 in / 
# Tue, 17 Jul 2018 08:48:07 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 19:29:58 GMT
RUN groupadd -r spiped &&	useradd -r -g spiped spiped
# Tue, 17 Jul 2018 19:30:10 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	apt-get update &&	apt-get install -y libssl1.1 --no-install-recommends &&	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 19:30:11 GMT
ENV SPIPED_VERSION=1.6.0
# Tue, 17 Jul 2018 19:30:12 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Tue, 17 Jul 2018 19:30:12 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Tue, 17 Jul 2018 19:32:39 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	buildDeps='libssl-dev libc-dev gcc make curl ca-certificates' &&	apt-get update && apt-get install -y $buildDeps --no-install-recommends &&	rm -rf /var/lib/apt/lists/* &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apt-get purge -y --auto-remove $buildDeps
# Tue, 17 Jul 2018 19:32:41 GMT
VOLUME [/spiped]
# Tue, 17 Jul 2018 19:32:42 GMT
WORKDIR /spiped
# Tue, 17 Jul 2018 19:32:43 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Tue, 17 Jul 2018 19:32:44 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 17 Jul 2018 19:32:45 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:74a932489409d8d15db14c8a4a811fb46c7386bb06ea678ff27084d5657eeaaf`  
		Last Modified: Tue, 17 Jul 2018 08:57:35 GMT  
		Size: 20.3 MB (20331647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9bf12f1b6e3709fe4e57be9e4f43b2ec22b50bfad37244e1c3639016305c4843`  
		Last Modified: Tue, 17 Jul 2018 19:33:26 GMT  
		Size: 1.8 KB (1751 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85631bb1905daa222028a82c084b1c56dd7d102a037d8c0df7b4de5dbcfb94ec`  
		Last Modified: Tue, 17 Jul 2018 19:33:28 GMT  
		Size: 1.6 MB (1614898 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5eb044f9e4392b03ca3e229de5d059256ef2b0a3a0b6d7403fa0f8f9aed75bd8`  
		Last Modified: Tue, 17 Jul 2018 19:33:28 GMT  
		Size: 5.2 MB (5236469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:26614e7c71669416b32a0f5d50bc13d98346473f128a52783a95a73929248bcd`  
		Last Modified: Tue, 17 Jul 2018 19:33:25 GMT  
		Size: 95.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:96977fdc87fbc8e70071d17a17214cf7a81b89c52430cb5d7cc57fb1755b9e57`  
		Last Modified: Tue, 17 Jul 2018 19:33:26 GMT  
		Size: 349.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `spiped:latest` - linux; 386

```console
$ docker pull spiped@sha256:9e33f81a88df51dceecf3166d4fcb474b57c72e822766f5aa0d9e8c80455071d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **34.3 MB (34305938 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:907855db1261728ec16d59c2885df4b4b87c9c8eaf98d643f35ff115a040a823`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Tue, 17 Jul 2018 10:50:00 GMT
ADD file:14cbcb91de201f648f46b04170dcae29163968a641f94d6ad7c3d77fc707a890 in / 
# Tue, 17 Jul 2018 10:50:03 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 15:28:12 GMT
RUN groupadd -r spiped &&	useradd -r -g spiped spiped
# Tue, 17 Jul 2018 15:28:20 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	apt-get update &&	apt-get install -y libssl1.1 --no-install-recommends &&	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 15:28:21 GMT
ENV SPIPED_VERSION=1.6.0
# Tue, 17 Jul 2018 15:28:21 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Tue, 17 Jul 2018 15:28:22 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Tue, 17 Jul 2018 15:29:13 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	buildDeps='libssl-dev libc-dev gcc make curl ca-certificates' &&	apt-get update && apt-get install -y $buildDeps --no-install-recommends &&	rm -rf /var/lib/apt/lists/* &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apt-get purge -y --auto-remove $buildDeps
# Tue, 17 Jul 2018 15:29:13 GMT
VOLUME [/spiped]
# Tue, 17 Jul 2018 15:29:14 GMT
WORKDIR /spiped
# Tue, 17 Jul 2018 15:29:14 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Tue, 17 Jul 2018 15:29:15 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 17 Jul 2018 15:29:15 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:9f3675ed6653666b64ffa6c3dc93755d10c6f906a1cab9f061cdbe09c65323f4`  
		Last Modified: Tue, 17 Jul 2018 11:09:22 GMT  
		Size: 23.1 MB (23126377 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7682d71d3fe7c6bdcf981942a541f7897ae2d74fc706a39d41c7936d18289764`  
		Last Modified: Tue, 17 Jul 2018 15:29:38 GMT  
		Size: 1.7 KB (1735 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d46f53f1a167f3ea6943149ad73267ef428384557cf43a206283c5c1abd3e711`  
		Last Modified: Tue, 17 Jul 2018 15:29:38 GMT  
		Size: 1.9 MB (1874202 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b4594baceeac08403cc691d2f5d189dda98b562e869ab29729db9b5262be0a4`  
		Last Modified: Tue, 17 Jul 2018 15:29:42 GMT  
		Size: 9.3 MB (9303182 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:68c68a92103e0c80f8dc722d498b85e201d7bae22c01bc08a772f32984077782`  
		Last Modified: Tue, 17 Jul 2018 15:29:38 GMT  
		Size: 95.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2776579ab3a6ed837a5ceb18849c7f0d493089ac3fae812babb560457df0d637`  
		Last Modified: Tue, 17 Jul 2018 15:29:37 GMT  
		Size: 347.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `spiped:latest` - linux; ppc64le

```console
$ docker pull spiped@sha256:5544c46b8972c6b86fb3f85947c1154be442f42776690d30e9cd8f01b7bb3e27
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **30.1 MB (30143056 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8b349e36acf351dd46fe71ace02e3c5baeece370f5f6fbb78008f408b92422b3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Tue, 17 Jul 2018 08:20:29 GMT
ADD file:d8fd3ee34d99a5bb7abafecc4f8991a3de0ad779e8fd8f3ebb33a4811ecfd5a5 in / 
# Tue, 17 Jul 2018 08:20:30 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 13:49:57 GMT
RUN groupadd -r spiped &&	useradd -r -g spiped spiped
# Tue, 17 Jul 2018 13:50:18 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	apt-get update &&	apt-get install -y libssl1.1 --no-install-recommends &&	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 13:50:22 GMT
ENV SPIPED_VERSION=1.6.0
# Tue, 17 Jul 2018 13:50:24 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Tue, 17 Jul 2018 13:50:24 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Tue, 17 Jul 2018 13:55:27 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	buildDeps='libssl-dev libc-dev gcc make curl ca-certificates' &&	apt-get update && apt-get install -y $buildDeps --no-install-recommends &&	rm -rf /var/lib/apt/lists/* &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apt-get purge -y --auto-remove $buildDeps
# Tue, 17 Jul 2018 13:55:43 GMT
VOLUME [/spiped]
# Tue, 17 Jul 2018 13:55:45 GMT
WORKDIR /spiped
# Tue, 17 Jul 2018 13:55:47 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Tue, 17 Jul 2018 13:55:49 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 17 Jul 2018 13:55:50 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:6dc0c10e32a730b4a6b92aaa59148a751864a834dc8ac1b0032717f378efc701`  
		Last Modified: Tue, 17 Jul 2018 08:26:26 GMT  
		Size: 22.7 MB (22740445 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:74e4b0a55c2fb337126c969e2b9a2911c0a7a41b4481a1ecfe376a730677ae0a`  
		Last Modified: Tue, 17 Jul 2018 13:56:20 GMT  
		Size: 1.8 KB (1753 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e18acc53ef592e406e91851c6ae46a38c55cb4298e2ca0be29e578c7f3aa77e8`  
		Last Modified: Tue, 17 Jul 2018 13:56:19 GMT  
		Size: 1.6 MB (1552507 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b7e513175318134a60f1e25a01bb1e47d82ba860a2a9e368ca2c43474cdfbd50`  
		Last Modified: Tue, 17 Jul 2018 13:56:21 GMT  
		Size: 5.8 MB (5847873 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:29d393572b20c0f2e63d0593f0798094b7c8c52aca849c7b75780ca8ae6e289f`  
		Last Modified: Tue, 17 Jul 2018 13:56:19 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec4fb0e60ac856b58e015cbad400667cede0a9219852b73fb5c86443fabca8b7`  
		Last Modified: Tue, 17 Jul 2018 13:56:19 GMT  
		Size: 349.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `spiped:latest` - linux; s390x

```console
$ docker pull spiped@sha256:afba85d5a3604aaf55eaf94deee189a9f094518d38f97d33077c4b99ac7f4953
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **30.7 MB (30722586 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ff7179a91c784d4f06f87a0381efbacc5ef034b62e36f4a8573708f7c2a3d520`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Tue, 17 Jul 2018 11:43:35 GMT
ADD file:32e6375c708c1a29a33eef651992d744ae278ef980cfb74086bc899cb8fffdfb in / 
# Tue, 17 Jul 2018 11:43:36 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 13:36:09 GMT
RUN groupadd -r spiped &&	useradd -r -g spiped spiped
# Tue, 17 Jul 2018 13:36:14 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	apt-get update &&	apt-get install -y libssl1.1 --no-install-recommends &&	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 13:36:14 GMT
ENV SPIPED_VERSION=1.6.0
# Tue, 17 Jul 2018 13:36:14 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Tue, 17 Jul 2018 13:36:14 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Tue, 17 Jul 2018 13:36:35 GMT
RUN DEBIAN_FRONTEND="noninteractive" &&	set -x &&	buildDeps='libssl-dev libc-dev gcc make curl ca-certificates' &&	apt-get update && apt-get install -y $buildDeps --no-install-recommends &&	rm -rf /var/lib/apt/lists/* &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apt-get purge -y --auto-remove $buildDeps
# Tue, 17 Jul 2018 13:36:35 GMT
VOLUME [/spiped]
# Tue, 17 Jul 2018 13:36:36 GMT
WORKDIR /spiped
# Tue, 17 Jul 2018 13:36:36 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Tue, 17 Jul 2018 13:36:36 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 17 Jul 2018 13:36:36 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:f27811d943553766d4449683ea06b6eac1147fe5de5663e94d39150eb2180735`  
		Last Modified: Tue, 17 Jul 2018 11:47:07 GMT  
		Size: 22.3 MB (22334517 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aafd734e67c7f8e052a18fd2304770042ce5b7dd79d24ba15a2a7b6b7aa7cf8e`  
		Last Modified: Tue, 17 Jul 2018 13:36:53 GMT  
		Size: 1.7 KB (1745 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b4d242495c871b7e54d8246bcf24d8313c8905b1a0cf8ee40cb15f418962a0ee`  
		Last Modified: Tue, 17 Jul 2018 13:36:54 GMT  
		Size: 1.6 MB (1615597 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8619dcbeeae9391f2a86b44d9058ca801feb0f0434de8e6caa7a6ca9f325620e`  
		Last Modified: Tue, 17 Jul 2018 13:36:54 GMT  
		Size: 6.8 MB (6770284 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a78f3c4e93df4bdc349a8830b3cb21868df66625c2e1a3204c180b791553b7f5`  
		Last Modified: Tue, 17 Jul 2018 13:36:53 GMT  
		Size: 95.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5d759fbe57767339a3a09a541b1be53c99e5be6076689823f2eabd92b2c3d1bb`  
		Last Modified: Tue, 17 Jul 2018 13:36:53 GMT  
		Size: 348.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
