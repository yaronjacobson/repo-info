## `golang:rc`

```console
$ docker pull golang@sha256:848d7c6e26a6ca99bdf50ae952769998f4ffd458328e2f4089ba8e784b09ffd7
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x
	-	windows version 10.0.14393.2363; amd64
	-	windows version 10.0.16299.547; amd64
	-	windows version 10.0.17134.165; amd64

### `golang:rc` - linux; amd64

```console
$ docker pull golang@sha256:f192f9a7398377f82cc6dbbd5c6e48a7129e15f3d4e97ea2cd5b4239c09c63cc
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **345.3 MB (345334699 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:798d75db89221fcc3e2b473233f1402c7216abcad5efc3ebd0515d16d7b28c04`
-	Default Command: `["bash"]`

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
# Tue, 17 Jul 2018 12:30:04 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		g++ 		gcc 		libc6-dev 		make 		pkg-config 	&& rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 16:23:52 GMT
ENV GOLANG_VERSION=1.11rc1
# Tue, 14 Aug 2018 16:24:10 GMT
RUN set -eux; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) goRelArch='linux-amd64'; goRelSha256='1a071f069982427b245aea736d3174e065a12e8481c34051c672d62a5ca59ca9' ;; 		armhf) goRelArch='linux-armv6l'; goRelSha256='6f2c0a53850e7dcd2f1592eb51325fa5da20ee953512bebf1b0d3fb046874dc4' ;; 		arm64) goRelArch='linux-arm64'; goRelSha256='8a3d96e3e7604cf5390b7e318ff35112cdb13e0e44ddf0130659cefd196ab50e' ;; 		i386) goRelArch='linux-386'; goRelSha256='afe8f516fbd0316981e70fc0dda8c67116837baaa0431ee2da47f4fee4614433' ;; 		ppc64el) goRelArch='linux-ppc64le'; goRelSha256='972e7b6bfecee780a9cd970100297b35bed4c82cacc2bd55d78428928b66683d' ;; 		s390x) goRelArch='linux-s390x'; goRelSha256='bd30adfb32de8c441fc0b12a9a9acbd5098a77ab77609269aed7ea4f8dd682ae' ;; 		*) goRelArch='src'; goRelSha256='fcb8778ad5d1bb7f5bfd1564ba4107894011f1d65f69be9fa1e693f6b5143828'; 			echo >&2; echo >&2 "warning: current architecture ($dpkgArch) does not have a corresponding Go binary release; will be building from source"; echo >&2 ;; 	esac; 		url="https://golang.org/dl/go${GOLANG_VERSION}.${goRelArch}.tar.gz"; 	wget -O go.tgz "$url"; 	echo "${goRelSha256} *go.tgz" | sha256sum -c -; 	tar -C /usr/local -xzf go.tgz; 	rm go.tgz; 		if [ "$goRelArch" = 'src' ]; then 		echo >&2; 		echo >&2 'error: UNIMPLEMENTED'; 		echo >&2 'TODO install golang-any from jessie-backports for GOROOT_BOOTSTRAP (and uninstall after build)'; 		echo >&2; 		exit 1; 	fi; 		export PATH="/usr/local/go/bin:$PATH"; 	go version
# Tue, 14 Aug 2018 16:24:11 GMT
ENV GOPATH=/go
# Tue, 14 Aug 2018 16:24:11 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 16:24:12 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Tue, 14 Aug 2018 16:24:12 GMT
WORKDIR /go
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
	-	`sha256:9c35c9787a2f7a0fbd6829b8ee0df1aebe44929788186d352b3a12f2046b3948`  
		Last Modified: Tue, 17 Jul 2018 12:32:32 GMT  
		Size: 57.6 MB (57585235 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a586ab5915090ad757af73c3d611d85877f28195a06d2ebaf9d85b0a05c61282`  
		Last Modified: Tue, 14 Aug 2018 16:30:23 GMT  
		Size: 177.3 MB (177298377 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb94d9d3eaaf1ce3bc13cebb900e7a7c120ff30528c27aee9eb0b1226d4d76f1`  
		Last Modified: Tue, 14 Aug 2018 16:29:27 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `golang:rc` - linux; arm variant v7

```console
$ docker pull golang@sha256:8cf82ed8f86722522e14cce983571ae3216b4a25a8583a4eaca55f6285480286
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **299.5 MB (299471175 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:00d7e62d0ee80e2f3ee874a16f9ba0d7c3469de1d9f32940917306936fa04ccf`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 12:05:25 GMT
ADD file:77cbe27c4436cc4c9d81bee6c5ae0fee0c6d1708813d34abd2af2d3ebd7d96a5 in / 
# Tue, 17 Jul 2018 12:05:26 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 13:46:48 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 13:46:56 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 13:47:40 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 17:58:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		g++ 		gcc 		libc6-dev 		make 		pkg-config 	&& rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 16:35:19 GMT
ENV GOLANG_VERSION=1.11rc1
# Tue, 14 Aug 2018 16:35:46 GMT
RUN set -eux; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) goRelArch='linux-amd64'; goRelSha256='1a071f069982427b245aea736d3174e065a12e8481c34051c672d62a5ca59ca9' ;; 		armhf) goRelArch='linux-armv6l'; goRelSha256='6f2c0a53850e7dcd2f1592eb51325fa5da20ee953512bebf1b0d3fb046874dc4' ;; 		arm64) goRelArch='linux-arm64'; goRelSha256='8a3d96e3e7604cf5390b7e318ff35112cdb13e0e44ddf0130659cefd196ab50e' ;; 		i386) goRelArch='linux-386'; goRelSha256='afe8f516fbd0316981e70fc0dda8c67116837baaa0431ee2da47f4fee4614433' ;; 		ppc64el) goRelArch='linux-ppc64le'; goRelSha256='972e7b6bfecee780a9cd970100297b35bed4c82cacc2bd55d78428928b66683d' ;; 		s390x) goRelArch='linux-s390x'; goRelSha256='bd30adfb32de8c441fc0b12a9a9acbd5098a77ab77609269aed7ea4f8dd682ae' ;; 		*) goRelArch='src'; goRelSha256='fcb8778ad5d1bb7f5bfd1564ba4107894011f1d65f69be9fa1e693f6b5143828'; 			echo >&2; echo >&2 "warning: current architecture ($dpkgArch) does not have a corresponding Go binary release; will be building from source"; echo >&2 ;; 	esac; 		url="https://golang.org/dl/go${GOLANG_VERSION}.${goRelArch}.tar.gz"; 	wget -O go.tgz "$url"; 	echo "${goRelSha256} *go.tgz" | sha256sum -c -; 	tar -C /usr/local -xzf go.tgz; 	rm go.tgz; 		if [ "$goRelArch" = 'src' ]; then 		echo >&2; 		echo >&2 'error: UNIMPLEMENTED'; 		echo >&2 'TODO install golang-any from jessie-backports for GOROOT_BOOTSTRAP (and uninstall after build)'; 		echo >&2; 		exit 1; 	fi; 		export PATH="/usr/local/go/bin:$PATH"; 	go version
# Tue, 14 Aug 2018 16:35:47 GMT
ENV GOPATH=/go
# Tue, 14 Aug 2018 16:35:47 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 16:35:48 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Tue, 14 Aug 2018 16:35:48 GMT
WORKDIR /go
```

-	Layers:
	-	`sha256:a92bc499a4699bc1d9bd6631daec00b7b440346221ce91af635e3460f7d4d70b`  
		Last Modified: Tue, 17 Jul 2018 12:17:32 GMT  
		Size: 42.1 MB (42060835 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d56e34dc5db45e25c590c9a353c3562d66546b06312f418f9aae4661c28ee94f`  
		Last Modified: Tue, 17 Jul 2018 14:10:12 GMT  
		Size: 9.4 MB (9440199 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:948d2574fcb06c4081812a267179437a8d624eba8741a8fb5a6e3ef655c3dcff`  
		Last Modified: Tue, 17 Jul 2018 14:10:10 GMT  
		Size: 3.9 MB (3912954 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:94ced04c5b3fc619ca9252df05a702d37000cbcc3fbac10e5e485428deba85ae`  
		Last Modified: Tue, 17 Jul 2018 14:10:55 GMT  
		Size: 46.4 MB (46380475 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15b6302ebab8f482cd218939332af3eb2acc1c67052757f7b28697e14e0a13d7`  
		Last Modified: Tue, 17 Jul 2018 18:00:42 GMT  
		Size: 45.9 MB (45923944 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c9412cd6340cb9be4d1036f04a6e3ee1f62b24a398f0e48fce4d2718c4053a5c`  
		Last Modified: Tue, 14 Aug 2018 16:36:45 GMT  
		Size: 151.8 MB (151752612 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:933caded572d80c7d9a3954373c97c857caa524aedb11ce94e3c28fe6f826e84`  
		Last Modified: Tue, 14 Aug 2018 16:36:09 GMT  
		Size: 156.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `golang:rc` - linux; arm64 variant v8

```console
$ docker pull golang@sha256:add48ae7963114aba7f8ce4590594c84cd9bf207a7561992db3d6942ece4d44b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **304.3 MB (304284975 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a14b748f5741a5b8672c4036132ff0ee8cd80dbe9f3c761daf25f89fbbe4b4c7`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 08:47:22 GMT
ADD file:5e1a1aab339b0b1e3047eeab5d0c6c74ad3f388d0407dc86f41e4a78b99c6fd8 in / 
# Tue, 17 Jul 2018 08:47:23 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 14:51:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 14:52:06 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 14:54:31 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Wed, 18 Jul 2018 04:25:05 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		g++ 		gcc 		libc6-dev 		make 		pkg-config 	&& rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 16:35:36 GMT
ENV GOLANG_VERSION=1.11rc1
# Tue, 14 Aug 2018 16:36:03 GMT
RUN set -eux; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) goRelArch='linux-amd64'; goRelSha256='1a071f069982427b245aea736d3174e065a12e8481c34051c672d62a5ca59ca9' ;; 		armhf) goRelArch='linux-armv6l'; goRelSha256='6f2c0a53850e7dcd2f1592eb51325fa5da20ee953512bebf1b0d3fb046874dc4' ;; 		arm64) goRelArch='linux-arm64'; goRelSha256='8a3d96e3e7604cf5390b7e318ff35112cdb13e0e44ddf0130659cefd196ab50e' ;; 		i386) goRelArch='linux-386'; goRelSha256='afe8f516fbd0316981e70fc0dda8c67116837baaa0431ee2da47f4fee4614433' ;; 		ppc64el) goRelArch='linux-ppc64le'; goRelSha256='972e7b6bfecee780a9cd970100297b35bed4c82cacc2bd55d78428928b66683d' ;; 		s390x) goRelArch='linux-s390x'; goRelSha256='bd30adfb32de8c441fc0b12a9a9acbd5098a77ab77609269aed7ea4f8dd682ae' ;; 		*) goRelArch='src'; goRelSha256='fcb8778ad5d1bb7f5bfd1564ba4107894011f1d65f69be9fa1e693f6b5143828'; 			echo >&2; echo >&2 "warning: current architecture ($dpkgArch) does not have a corresponding Go binary release; will be building from source"; echo >&2 ;; 	esac; 		url="https://golang.org/dl/go${GOLANG_VERSION}.${goRelArch}.tar.gz"; 	wget -O go.tgz "$url"; 	echo "${goRelSha256} *go.tgz" | sha256sum -c -; 	tar -C /usr/local -xzf go.tgz; 	rm go.tgz; 		if [ "$goRelArch" = 'src' ]; then 		echo >&2; 		echo >&2 'error: UNIMPLEMENTED'; 		echo >&2 'TODO install golang-any from jessie-backports for GOROOT_BOOTSTRAP (and uninstall after build)'; 		echo >&2; 		exit 1; 	fi; 		export PATH="/usr/local/go/bin:$PATH"; 	go version
# Tue, 14 Aug 2018 16:36:05 GMT
ENV GOPATH=/go
# Tue, 14 Aug 2018 16:36:05 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 16:36:07 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Tue, 14 Aug 2018 16:36:07 GMT
WORKDIR /go
```

-	Layers:
	-	`sha256:24e48664c69560cde9534aadde23364122f1feb02b5db0ab3776983a4788ea63`  
		Last Modified: Tue, 17 Jul 2018 08:56:03 GMT  
		Size: 43.1 MB (43123568 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbcf842c718cc953be45905967fc6a0114f55314ce412b80107e20d8b43fdcdb`  
		Last Modified: Tue, 17 Jul 2018 15:10:44 GMT  
		Size: 9.7 MB (9690273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:317d79a9c0a5c766d03c1c253fa09f645ed7321dc3a80e0ae33599958677cd1d`  
		Last Modified: Tue, 17 Jul 2018 15:10:41 GMT  
		Size: 4.1 MB (4088491 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a390be6b2f0349f7391582a305479410441bcb0329b8daa800d13f3921fd39b7`  
		Last Modified: Tue, 17 Jul 2018 15:11:46 GMT  
		Size: 48.0 MB (48003327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:94a0d029b36d67dd678c31d091d0d1d44daae01a0f91a80445446578ffb01e49`  
		Last Modified: Wed, 18 Jul 2018 04:28:16 GMT  
		Size: 49.0 MB (48989789 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c67e7e94e51f314340ff8792851bd31a2fb16cc0056a4f4baafab829d90c91b8`  
		Last Modified: Tue, 14 Aug 2018 16:44:29 GMT  
		Size: 150.4 MB (150389401 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d9fbb4c7cc68a4ae18e8b3fb8898b96ee2648bf6d045798a04a6459280f93938`  
		Last Modified: Tue, 14 Aug 2018 16:43:41 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `golang:rc` - linux; 386

```console
$ docker pull golang@sha256:13dc6eb33137cabce68c6dc96b2189fd76788438bcedbec254ddd3e361120364
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **335.9 MB (335924222 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8ba111e70aa30f086163c485763e0d623dee2a2e5055da0f95377b9700e13a77`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 10:49:17 GMT
ADD file:be09029a70a8ca76c88918bd3070fb0cbd97606c95450ec1d27efa9f78536d6f in / 
# Tue, 17 Jul 2018 10:49:20 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 14:34:44 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 14:34:55 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 14:35:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 21:44:54 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		g++ 		gcc 		libc6-dev 		make 		pkg-config 	&& rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 16:36:10 GMT
ENV GOLANG_VERSION=1.11rc1
# Tue, 14 Aug 2018 16:36:44 GMT
RUN set -eux; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) goRelArch='linux-amd64'; goRelSha256='1a071f069982427b245aea736d3174e065a12e8481c34051c672d62a5ca59ca9' ;; 		armhf) goRelArch='linux-armv6l'; goRelSha256='6f2c0a53850e7dcd2f1592eb51325fa5da20ee953512bebf1b0d3fb046874dc4' ;; 		arm64) goRelArch='linux-arm64'; goRelSha256='8a3d96e3e7604cf5390b7e318ff35112cdb13e0e44ddf0130659cefd196ab50e' ;; 		i386) goRelArch='linux-386'; goRelSha256='afe8f516fbd0316981e70fc0dda8c67116837baaa0431ee2da47f4fee4614433' ;; 		ppc64el) goRelArch='linux-ppc64le'; goRelSha256='972e7b6bfecee780a9cd970100297b35bed4c82cacc2bd55d78428928b66683d' ;; 		s390x) goRelArch='linux-s390x'; goRelSha256='bd30adfb32de8c441fc0b12a9a9acbd5098a77ab77609269aed7ea4f8dd682ae' ;; 		*) goRelArch='src'; goRelSha256='fcb8778ad5d1bb7f5bfd1564ba4107894011f1d65f69be9fa1e693f6b5143828'; 			echo >&2; echo >&2 "warning: current architecture ($dpkgArch) does not have a corresponding Go binary release; will be building from source"; echo >&2 ;; 	esac; 		url="https://golang.org/dl/go${GOLANG_VERSION}.${goRelArch}.tar.gz"; 	wget -O go.tgz "$url"; 	echo "${goRelSha256} *go.tgz" | sha256sum -c -; 	tar -C /usr/local -xzf go.tgz; 	rm go.tgz; 		if [ "$goRelArch" = 'src' ]; then 		echo >&2; 		echo >&2 'error: UNIMPLEMENTED'; 		echo >&2 'TODO install golang-any from jessie-backports for GOROOT_BOOTSTRAP (and uninstall after build)'; 		echo >&2; 		exit 1; 	fi; 		export PATH="/usr/local/go/bin:$PATH"; 	go version
# Tue, 14 Aug 2018 16:36:44 GMT
ENV GOPATH=/go
# Tue, 14 Aug 2018 16:36:45 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 16:36:46 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Tue, 14 Aug 2018 16:36:46 GMT
WORKDIR /go
```

-	Layers:
	-	`sha256:79324aeae468dc95e9d1ad7d17eccb16f424671f297c1c8231f48ad8b2a5a949`  
		Last Modified: Tue, 17 Jul 2018 11:07:28 GMT  
		Size: 46.0 MB (46037522 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d55059f59399b1edb44f6fccf01b4b41c46365022205a35f92fa4aee831f1bac`  
		Last Modified: Tue, 17 Jul 2018 15:15:31 GMT  
		Size: 10.8 MB (10752710 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b748c8a9e197a5c36217dc0236e60923d398eef3c44073cffeed563cb61421c3`  
		Last Modified: Tue, 17 Jul 2018 15:15:28 GMT  
		Size: 4.6 MB (4555355 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d33fbb92cee00a6946f3439c773b2a26dfb2db55c4c789ca3e7b53c3c7840823`  
		Last Modified: Tue, 17 Jul 2018 15:16:38 GMT  
		Size: 51.6 MB (51592718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48105a2d2fdec0c63440dcac18aa357da3b64267c32814d155100296d7710c85`  
		Last Modified: Tue, 17 Jul 2018 21:48:00 GMT  
		Size: 62.1 MB (62107873 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8ea152ff5ab385e0a770397dd57ade1e73b7defc1df1810a5fd5f25b37e758ae`  
		Last Modified: Tue, 14 Aug 2018 16:43:56 GMT  
		Size: 160.9 MB (160877918 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce7520ddb6c4fc9263b14ae9f16c6f8d9763f68403c5771e2c250a7f4e29a4d2`  
		Last Modified: Tue, 14 Aug 2018 16:43:06 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `golang:rc` - linux; ppc64le

```console
$ docker pull golang@sha256:da275dc268a4b7cb37707dd1acd8f31c2c9e3984ee84e40e7a655680a3272c57
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **311.7 MB (311670784 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3c9f0e8ca8e49c2d869a9f84f40302bd6f1464865c6a9b2c7827be404cf83574`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 08:20:06 GMT
ADD file:692c439870d267b1a84ee3f6c44eb8a4a8342eef759391242613964e31747b24 in / 
# Tue, 17 Jul 2018 08:20:07 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 13:10:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 13:11:29 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 13:15:12 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 21:54:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		g++ 		gcc 		libc6-dev 		make 		pkg-config 	&& rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 16:35:46 GMT
ENV GOLANG_VERSION=1.11rc1
# Tue, 14 Aug 2018 16:36:17 GMT
RUN set -eux; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) goRelArch='linux-amd64'; goRelSha256='1a071f069982427b245aea736d3174e065a12e8481c34051c672d62a5ca59ca9' ;; 		armhf) goRelArch='linux-armv6l'; goRelSha256='6f2c0a53850e7dcd2f1592eb51325fa5da20ee953512bebf1b0d3fb046874dc4' ;; 		arm64) goRelArch='linux-arm64'; goRelSha256='8a3d96e3e7604cf5390b7e318ff35112cdb13e0e44ddf0130659cefd196ab50e' ;; 		i386) goRelArch='linux-386'; goRelSha256='afe8f516fbd0316981e70fc0dda8c67116837baaa0431ee2da47f4fee4614433' ;; 		ppc64el) goRelArch='linux-ppc64le'; goRelSha256='972e7b6bfecee780a9cd970100297b35bed4c82cacc2bd55d78428928b66683d' ;; 		s390x) goRelArch='linux-s390x'; goRelSha256='bd30adfb32de8c441fc0b12a9a9acbd5098a77ab77609269aed7ea4f8dd682ae' ;; 		*) goRelArch='src'; goRelSha256='fcb8778ad5d1bb7f5bfd1564ba4107894011f1d65f69be9fa1e693f6b5143828'; 			echo >&2; echo >&2 "warning: current architecture ($dpkgArch) does not have a corresponding Go binary release; will be building from source"; echo >&2 ;; 	esac; 		url="https://golang.org/dl/go${GOLANG_VERSION}.${goRelArch}.tar.gz"; 	wget -O go.tgz "$url"; 	echo "${goRelSha256} *go.tgz" | sha256sum -c -; 	tar -C /usr/local -xzf go.tgz; 	rm go.tgz; 		if [ "$goRelArch" = 'src' ]; then 		echo >&2; 		echo >&2 'error: UNIMPLEMENTED'; 		echo >&2 'TODO install golang-any from jessie-backports for GOROOT_BOOTSTRAP (and uninstall after build)'; 		echo >&2; 		exit 1; 	fi; 		export PATH="/usr/local/go/bin:$PATH"; 	go version
# Tue, 14 Aug 2018 16:36:19 GMT
ENV GOPATH=/go
# Tue, 14 Aug 2018 16:36:21 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 16:36:27 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Tue, 14 Aug 2018 16:36:28 GMT
WORKDIR /go
```

-	Layers:
	-	`sha256:4d37f09838fa8757d02699f103191e672c0ecde0fcf23bb3706d1343831762fb`  
		Last Modified: Tue, 17 Jul 2018 08:25:32 GMT  
		Size: 45.6 MB (45594057 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22b62820a77d74ffab7785bdebc26e90a2ad429b6a23be61002b575c308f717e`  
		Last Modified: Tue, 17 Jul 2018 14:16:47 GMT  
		Size: 9.9 MB (9943597 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b71a75676a8f5e4b583626a0edc6859aa782e4d90d17995e1e8251146eedfbe4`  
		Last Modified: Tue, 17 Jul 2018 14:16:45 GMT  
		Size: 4.3 MB (4290027 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce2868b335fa3529e1c024e3f109aa32681130cb83eaadc6c37f7adf1b2d63e6`  
		Last Modified: Tue, 17 Jul 2018 14:17:42 GMT  
		Size: 50.1 MB (50061274 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9153a3afb78fb00db7239f66b6c3dc1581a5e75aa2acb88837fa553712776954`  
		Last Modified: Tue, 17 Jul 2018 22:01:29 GMT  
		Size: 52.8 MB (52762358 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b8f7519eafe934ca23d66f5a5b8305968a69c851148f05b0cb26ff48195745c9`  
		Last Modified: Tue, 14 Aug 2018 16:42:09 GMT  
		Size: 149.0 MB (149019314 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:424b1635deec0bb873ca5d1afc6c719da436287073a15952946e3f334db07eeb`  
		Last Modified: Tue, 14 Aug 2018 16:41:29 GMT  
		Size: 157.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `golang:rc` - linux; s390x

```console
$ docker pull golang@sha256:548753ae441461fe3db3f320345e165e6c6720f2c0f828c4f9ef1d1eaa1c7162
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **306.7 MB (306730495 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:444073ff15d19719c47bf0961fc286adfd5f2635dbd2fb4d6365540661a2d5ed`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 11:43:17 GMT
ADD file:8359a87f8de229cd148a6a7f227042a80cb73366ce79cb1a866426a6a91103e7 in / 
# Tue, 17 Jul 2018 11:43:18 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 13:21:02 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 13:21:06 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 13:21:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 16:25:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		g++ 		gcc 		libc6-dev 		make 		pkg-config 	&& rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 16:35:20 GMT
ENV GOLANG_VERSION=1.11rc1
# Tue, 14 Aug 2018 16:35:37 GMT
RUN set -eux; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) goRelArch='linux-amd64'; goRelSha256='1a071f069982427b245aea736d3174e065a12e8481c34051c672d62a5ca59ca9' ;; 		armhf) goRelArch='linux-armv6l'; goRelSha256='6f2c0a53850e7dcd2f1592eb51325fa5da20ee953512bebf1b0d3fb046874dc4' ;; 		arm64) goRelArch='linux-arm64'; goRelSha256='8a3d96e3e7604cf5390b7e318ff35112cdb13e0e44ddf0130659cefd196ab50e' ;; 		i386) goRelArch='linux-386'; goRelSha256='afe8f516fbd0316981e70fc0dda8c67116837baaa0431ee2da47f4fee4614433' ;; 		ppc64el) goRelArch='linux-ppc64le'; goRelSha256='972e7b6bfecee780a9cd970100297b35bed4c82cacc2bd55d78428928b66683d' ;; 		s390x) goRelArch='linux-s390x'; goRelSha256='bd30adfb32de8c441fc0b12a9a9acbd5098a77ab77609269aed7ea4f8dd682ae' ;; 		*) goRelArch='src'; goRelSha256='fcb8778ad5d1bb7f5bfd1564ba4107894011f1d65f69be9fa1e693f6b5143828'; 			echo >&2; echo >&2 "warning: current architecture ($dpkgArch) does not have a corresponding Go binary release; will be building from source"; echo >&2 ;; 	esac; 		url="https://golang.org/dl/go${GOLANG_VERSION}.${goRelArch}.tar.gz"; 	wget -O go.tgz "$url"; 	echo "${goRelSha256} *go.tgz" | sha256sum -c -; 	tar -C /usr/local -xzf go.tgz; 	rm go.tgz; 		if [ "$goRelArch" = 'src' ]; then 		echo >&2; 		echo >&2 'error: UNIMPLEMENTED'; 		echo >&2 'TODO install golang-any from jessie-backports for GOROOT_BOOTSTRAP (and uninstall after build)'; 		echo >&2; 		exit 1; 	fi; 		export PATH="/usr/local/go/bin:$PATH"; 	go version
# Tue, 14 Aug 2018 16:35:37 GMT
ENV GOPATH=/go
# Tue, 14 Aug 2018 16:35:37 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 16:35:38 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Tue, 14 Aug 2018 16:35:38 GMT
WORKDIR /go
```

-	Layers:
	-	`sha256:9351e2bf09f4d9a6beab73bfd3f913106d30008c3ebde119c4b5820670de53e1`  
		Last Modified: Tue, 17 Jul 2018 11:46:37 GMT  
		Size: 45.2 MB (45198375 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10c6d95a7f071ed59620c691d7cb2ba7909eebd13ad42f2edea64fa6345b1194`  
		Last Modified: Tue, 17 Jul 2018 13:30:29 GMT  
		Size: 10.3 MB (10267412 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c4fda1014bc69bc1831d085530e0e2092c9eaa1f92f6e0861aa060dc4580c9b9`  
		Last Modified: Tue, 17 Jul 2018 13:30:27 GMT  
		Size: 4.4 MB (4366785 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9ee6f36da521265c10265dc58eb783f0fcec8fdfef13b9b8520618833e2208a0`  
		Last Modified: Tue, 17 Jul 2018 13:30:51 GMT  
		Size: 50.5 MB (50482326 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b447b317dd4925937d6474bc6283857e25e25c167cbbfe03c75bb33603fa51f`  
		Last Modified: Tue, 17 Jul 2018 16:27:51 GMT  
		Size: 45.9 MB (45877116 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7313fa89330218ad3abb8e843695673dc1eae3bdf663520db752c61ef3ccce77`  
		Last Modified: Tue, 14 Aug 2018 16:39:47 GMT  
		Size: 150.5 MB (150538355 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a7ca2a753bfdb62985d287fbf85e9adc6f7024b1be548ae35769c836cb1dc69e`  
		Last Modified: Tue, 14 Aug 2018 16:39:24 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `golang:rc` - windows version 10.0.14393.2363; amd64

```console
$ docker pull golang@sha256:b964bbab8eb7caa9dff79ffe985f32a827d4fda8d1e439ed1206dd1a3f92473e
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.7 GB (5714100661 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a42a8f79a320ab86d67b51642adf00cd8aaa30a641afc53a519e73c9afec0b4b`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Tue, 10 Jul 2018 21:16:33 GMT
RUN Install update 10.0.14393.2363
# Wed, 11 Jul 2018 09:36:34 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Fri, 13 Jul 2018 09:19:17 GMT
ENV GIT_VERSION=2.11.1
# Fri, 13 Jul 2018 09:19:17 GMT
ENV GIT_TAG=v2.11.1.windows.1
# Fri, 13 Jul 2018 09:19:18 GMT
ENV GIT_DOWNLOAD_URL=https://github.com/git-for-windows/git/releases/download/v2.11.1.windows.1/MinGit-2.11.1-64-bit.zip
# Fri, 13 Jul 2018 09:19:20 GMT
ENV GIT_DOWNLOAD_SHA256=668d16a799dd721ed126cc91bed49eb2c072ba1b25b50048280a4e2c5ed56e59
# Fri, 13 Jul 2018 09:51:43 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:GIT_DOWNLOAD_URL); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri $env:GIT_DOWNLOAD_URL -OutFile 'git.zip'; 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:GIT_DOWNLOAD_SHA256); 	if ((Get-FileHash git.zip -Algorithm sha256).Hash -ne $env:GIT_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive -Path git.zip -DestinationPath C:\git\.; 		Write-Host 'Removing ...'; 	Remove-Item git.zip -Force; 		Write-Host 'Updating PATH ...'; 	$env:PATH = 'C:\git\cmd;C:\git\mingw64\bin;C:\git\usr\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  git --version'; git --version; 		Write-Host 'Complete.';
# Fri, 13 Jul 2018 09:51:44 GMT
ENV GOPATH=C:\gopath
# Fri, 13 Jul 2018 09:52:51 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	[Environment]::SetEnvironmentVariable('PATH', $newPath, [EnvironmentVariableTarget]::Machine);
# Tue, 14 Aug 2018 16:37:46 GMT
ENV GOLANG_VERSION=1.11rc1
# Tue, 14 Aug 2018 16:44:38 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = 'bcd482bdae421c580897ce0bb350f56679ebe676817ead572ee3a5942611bcc9'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Tue, 14 Aug 2018 16:44:40 GMT
WORKDIR C:\gopath
```

-	Layers:
	-	`sha256:3889bb8d808bbae6fa5a33e07093e65c31371bcf9e4c38c21be6b9af52ad1548`  
		Last Modified: Tue, 13 Dec 2016 10:53:31 GMT  
		Size: 4.1 GB (4069985900 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:fb1ebf2c42b6ac63b874d36a405b413fdf6c314131c3605d77e3cee6f485881f`  
		Last Modified: Tue, 10 Jul 2018 21:16:33 GMT  
		Size: 1.4 GB (1419298293 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:b678e902d6e9a27ab4d61bef7b26997ea26fdec2575d1317c9eab3b31c61fd9b`  
		Last Modified: Wed, 11 Jul 2018 09:53:57 GMT  
		Size: 1.2 KB (1194 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e80d4f601876b861621b8343597ef6241e44c8ebbeb865741f9d7e004dde08d`  
		Last Modified: Fri, 13 Jul 2018 11:04:16 GMT  
		Size: 1.2 KB (1201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6b11d696257875b50977a51053deeb2969178a79c7a37d903f68d05afcf99ab0`  
		Last Modified: Fri, 13 Jul 2018 11:04:14 GMT  
		Size: 1.2 KB (1177 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6cf9b24157930fa51b746051ae6df4fccd85d53aff399333434f87bc7fb44e02`  
		Last Modified: Fri, 13 Jul 2018 11:04:12 GMT  
		Size: 1.2 KB (1200 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3dbc4ad621caff330348a27c442e2344be5c97e1011af2cc95270629d4c6dbcb`  
		Last Modified: Fri, 13 Jul 2018 11:04:12 GMT  
		Size: 1.2 KB (1203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb7c7a610c85b1ffbb940627726d916e9a01a61d4fec2d7947e989c734ee9649`  
		Last Modified: Fri, 13 Jul 2018 11:04:24 GMT  
		Size: 29.4 MB (29446851 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:659b95ea2d59290bd3137a837554af33b3d11697b4e6959c81c827d1b5262352`  
		Last Modified: Fri, 13 Jul 2018 11:04:09 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43f34f043fba841e7abe0f2795476da451834f981cea07db052634bd22ac87fc`  
		Last Modified: Fri, 13 Jul 2018 11:04:11 GMT  
		Size: 5.0 MB (4986011 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6378b724c9d5acc6e93e3fd3040d1d9c50f5cc0c9cf495107666025847cd08c4`  
		Last Modified: Tue, 14 Aug 2018 17:04:51 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcb761e90bded5d4bd1cbc1c6d983e638c644afd8df5a6166c41bc4b939c3793`  
		Last Modified: Tue, 14 Aug 2018 17:06:19 GMT  
		Size: 190.4 MB (190373897 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:409582c640bb778a7cdb81679bb1bc7b46ca62a5f88d213ac20ba4554a8a12cf`  
		Last Modified: Tue, 14 Aug 2018 17:04:51 GMT  
		Size: 1.3 KB (1342 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `golang:rc` - windows version 10.0.16299.547; amd64

```console
$ docker pull golang@sha256:65768020a206e7e8f016b91aedb0ecb49b648ad23ab133c86f4905d7ad2a1691
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.3 GB (3324822468 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:cf9f89218b9234952c5cb01fabe8606cb5813d0db9f22d97e079d106ad4a917b`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Mon, 02 Jul 2018 18:10:50 GMT
RUN Install update 10.0.16299.547
# Wed, 11 Jul 2018 09:41:02 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Fri, 13 Jul 2018 09:59:09 GMT
ENV GIT_VERSION=2.11.1
# Fri, 13 Jul 2018 09:59:10 GMT
ENV GIT_TAG=v2.11.1.windows.1
# Fri, 13 Jul 2018 09:59:11 GMT
ENV GIT_DOWNLOAD_URL=https://github.com/git-for-windows/git/releases/download/v2.11.1.windows.1/MinGit-2.11.1-64-bit.zip
# Fri, 13 Jul 2018 09:59:12 GMT
ENV GIT_DOWNLOAD_SHA256=668d16a799dd721ed126cc91bed49eb2c072ba1b25b50048280a4e2c5ed56e59
# Fri, 13 Jul 2018 10:00:46 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:GIT_DOWNLOAD_URL); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri $env:GIT_DOWNLOAD_URL -OutFile 'git.zip'; 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:GIT_DOWNLOAD_SHA256); 	if ((Get-FileHash git.zip -Algorithm sha256).Hash -ne $env:GIT_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive -Path git.zip -DestinationPath C:\git\.; 		Write-Host 'Removing ...'; 	Remove-Item git.zip -Force; 		Write-Host 'Updating PATH ...'; 	$env:PATH = 'C:\git\cmd;C:\git\mingw64\bin;C:\git\usr\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  git --version'; git --version; 		Write-Host 'Complete.';
# Fri, 13 Jul 2018 10:00:47 GMT
ENV GOPATH=C:\gopath
# Fri, 13 Jul 2018 10:01:34 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	[Environment]::SetEnvironmentVariable('PATH', $newPath, [EnvironmentVariableTarget]::Machine);
# Tue, 14 Aug 2018 16:44:45 GMT
ENV GOLANG_VERSION=1.11rc1
# Tue, 14 Aug 2018 16:50:55 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = 'bcd482bdae421c580897ce0bb350f56679ebe676817ead572ee3a5942611bcc9'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Tue, 14 Aug 2018 16:50:56 GMT
WORKDIR C:\gopath
```

-	Layers:
	-	`sha256:5847a47b8593f7c39aa5e3db09e50b76d42aa8898c0440c70cc9c69747d4c479`  
		Last Modified: Tue, 17 Oct 2017 15:51:05 GMT  
		Size: 2.3 GB (2274300585 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:a01c2a39b5bdf158508b424626efbcede4aa9da21f2d4f6ffbd5bff4deb0fb01`  
		Last Modified: Tue, 10 Jul 2018 23:36:17 GMT  
		Size: 831.1 MB (831119569 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:5c935a79e71d79bf144e02b94352e10d483d43e5c3f4a3491874c5d6d72deda3`  
		Last Modified: Wed, 11 Jul 2018 09:55:02 GMT  
		Size: 1.2 KB (1193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55e039188b8cdcd6d2306c66e6daaca9ed974e64d3b17ce8ae0e327f54cfc931`  
		Last Modified: Fri, 13 Jul 2018 11:06:04 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:06cb70e6140b0978982a4d8f848b7ffe37757c9b454b251930a18ee7b4c775d0`  
		Last Modified: Fri, 13 Jul 2018 11:06:03 GMT  
		Size: 1.2 KB (1187 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c9afba9e858eaab528f647620fc0d49d0fd49e57945f6187ad0d0450f0d72fe`  
		Last Modified: Fri, 13 Jul 2018 11:06:01 GMT  
		Size: 1.2 KB (1201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fe9a0eefa5430dfca3159c6b0e2f7f35f28cd8236d323e440a585ae5a1b5342`  
		Last Modified: Fri, 13 Jul 2018 11:06:00 GMT  
		Size: 1.2 KB (1191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8228bba40556a914a0a62987f89cf2faac16a828a98755212287764086b3409d`  
		Last Modified: Fri, 13 Jul 2018 11:06:12 GMT  
		Size: 29.1 MB (29119290 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff8301abb8f59eee30d309a27d82dfbd54a885c105cbc7c376f6321b911b8e59`  
		Last Modified: Fri, 13 Jul 2018 11:05:58 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5220aaffec8c6508a977b58b8dc750dd947da554793092cf4736c2e81119cd50`  
		Last Modified: Fri, 13 Jul 2018 11:06:00 GMT  
		Size: 4.7 MB (4688092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:78937fe90516f8044bdffcbdd6af203263e0dcd985116448368edc48be4a615d`  
		Last Modified: Tue, 14 Aug 2018 17:06:38 GMT  
		Size: 1.2 KB (1199 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:06713c89e58adf3ecbf320c87e31cad2b84405fbcf9b3a4fb68abaad8c750eeb`  
		Last Modified: Tue, 14 Aug 2018 17:08:05 GMT  
		Size: 185.6 MB (185585222 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c88cc3166d71a5d1395112241634757d2c2124d85b2ca31ca245add748a21510`  
		Last Modified: Tue, 14 Aug 2018 17:06:38 GMT  
		Size: 1.3 KB (1344 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `golang:rc` - windows version 10.0.17134.165; amd64

```console
$ docker pull golang@sha256:f5771ed062a20748461d5af219f7f2b0f5e69a52a96dd13f6ba60bd51b74148f
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **2.4 GB (2363702218 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:111bfec484a6b06bea38bf12e494224bbd362c51e859e97066ac8491acbea58f`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Thu, 12 Apr 2018 09:20:54 GMT
RUN Apply image 10.0.17134.1
# Sat, 07 Jul 2018 22:48:41 GMT
RUN Install update 10.0.17134.165
# Fri, 13 Jul 2018 10:07:25 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Fri, 13 Jul 2018 10:07:26 GMT
ENV GIT_VERSION=2.11.1
# Fri, 13 Jul 2018 10:07:27 GMT
ENV GIT_TAG=v2.11.1.windows.1
# Fri, 13 Jul 2018 10:07:28 GMT
ENV GIT_DOWNLOAD_URL=https://github.com/git-for-windows/git/releases/download/v2.11.1.windows.1/MinGit-2.11.1-64-bit.zip
# Fri, 13 Jul 2018 10:07:28 GMT
ENV GIT_DOWNLOAD_SHA256=668d16a799dd721ed126cc91bed49eb2c072ba1b25b50048280a4e2c5ed56e59
# Fri, 13 Jul 2018 10:08:54 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:GIT_DOWNLOAD_URL); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri $env:GIT_DOWNLOAD_URL -OutFile 'git.zip'; 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:GIT_DOWNLOAD_SHA256); 	if ((Get-FileHash git.zip -Algorithm sha256).Hash -ne $env:GIT_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive -Path git.zip -DestinationPath C:\git\.; 		Write-Host 'Removing ...'; 	Remove-Item git.zip -Force; 		Write-Host 'Updating PATH ...'; 	$env:PATH = 'C:\git\cmd;C:\git\mingw64\bin;C:\git\usr\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  git --version'; git --version; 		Write-Host 'Complete.';
# Fri, 13 Jul 2018 10:08:56 GMT
ENV GOPATH=C:\gopath
# Fri, 13 Jul 2018 10:09:39 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	[Environment]::SetEnvironmentVariable('PATH', $newPath, [EnvironmentVariableTarget]::Machine);
# Tue, 14 Aug 2018 16:51:13 GMT
ENV GOLANG_VERSION=1.11rc1
# Tue, 14 Aug 2018 16:57:21 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = 'bcd482bdae421c580897ce0bb350f56679ebe676817ead572ee3a5942611bcc9'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Tue, 14 Aug 2018 16:57:23 GMT
WORKDIR C:\gopath
```

-	Layers:
	-	`sha256:d9e8b01179bfc94a5bdb1810fbd76b999aa52016001ace2d3a4c4bc7065a9601`  
		Last Modified: Mon, 07 May 2018 21:18:35 GMT  
		Size: 1.7 GB (1659688273 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:e30fefc566f71c5dd5786e4783ff4ae3ad98804d5279c14dcf806c813fdf8f66`  
		Last Modified: Tue, 10 Jul 2018 21:54:14 GMT  
		Size: 493.5 MB (493521205 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:5e25b1252e9b6c8bdfcec66e75be65af2baf4bcf1a67dc96422fef339cc4912c`  
		Last Modified: Fri, 13 Jul 2018 11:07:53 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcb8204d8ec55cb4f90f7d714268cc09d8ba91ea9367280e6ad469af2d402586`  
		Last Modified: Fri, 13 Jul 2018 11:07:53 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:259348c7b912e7c7ec2419f712b8308df80b66b627c4de2676c4cc03d26c7bf4`  
		Last Modified: Fri, 13 Jul 2018 11:07:50 GMT  
		Size: 1.2 KB (1178 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1cea0dfd17e7231f41619c84a6bfde0dd7a121a3d839651ca0566be9ec2c9ea4`  
		Last Modified: Fri, 13 Jul 2018 11:07:49 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b833d9bde7c5fb916270d56937979e5585ece9145afcad775c8861c15a240ad`  
		Last Modified: Fri, 13 Jul 2018 11:07:49 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb5d404de536327f6e5736ad2f9ee6a2186c5ca4975f143da218f8015d66bc43`  
		Last Modified: Fri, 13 Jul 2018 11:08:00 GMT  
		Size: 29.0 MB (28959589 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:73f17e2bb7e96c2294d7e1e57f7b0e50b57bbbe1b6324a8778cf21a0d66b8ffa`  
		Last Modified: Fri, 13 Jul 2018 11:07:45 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a0ad9df6429f66007fe2647b7190df00610952251ce56d5dfc48fa7ca5fffd9d`  
		Last Modified: Fri, 13 Jul 2018 11:07:46 GMT  
		Size: 296.8 KB (296800 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5541d55eda7abf20b565a9a8e87ea6280182f52dfee9d74e389fab2d43d014e9`  
		Last Modified: Tue, 14 Aug 2018 17:08:24 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1febda11502801e157c21bdca388642c9bf691f8531497740bfedc823844ec8a`  
		Last Modified: Tue, 14 Aug 2018 17:09:49 GMT  
		Size: 181.2 MB (181226661 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:351f11705c0bc187626da2aee7f282b6a372b2d8e042bd0e7520d6d3253b3ea4`  
		Last Modified: Tue, 14 Aug 2018 17:08:25 GMT  
		Size: 1.3 KB (1344 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
