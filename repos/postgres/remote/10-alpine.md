## `postgres:10-alpine`

```console
$ docker pull postgres@sha256:d09024b892b57663cb22e466fe0d1281bc19565affe7ab2796dc3c307cb0317b
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v6
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `postgres:10-alpine` - linux; amd64

```console
$ docker pull postgres@sha256:d89ec9b53b2f1a55ccc4d33811778dd071c84ba8a12fae7b2165442fafb4a835
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **29.5 MB (29478195 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5df4f9af771f31b44478e7092d7e2a440d6b1628a33b199183792ce80164b0c0`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Fri, 06 Jul 2018 14:14:06 GMT
ADD file:25f61d70254b9807a40cd3e8d820f6a5ec0e1e596de04e325f6a33810393e95a in / 
# Fri, 06 Jul 2018 14:14:06 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 00:47:50 GMT
RUN set -ex; 	postgresHome="$(getent passwd postgres)"; 	postgresHome="$(echo "$postgresHome" | cut -d: -f6)"; 	[ "$postgresHome" = '/var/lib/postgresql' ]; 	mkdir -p "$postgresHome"; 	chown -R postgres:postgres "$postgresHome"
# Wed, 11 Jul 2018 00:47:50 GMT
ENV LANG=en_US.utf8
# Wed, 11 Jul 2018 00:47:51 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 11 Jul 2018 00:50:58 GMT
ENV PG_MAJOR=10
# Fri, 10 Aug 2018 22:11:17 GMT
ENV PG_VERSION=10.5
# Fri, 10 Aug 2018 22:11:17 GMT
ENV PG_SHA256=6c8e616c91a45142b85c0aeb1f29ebba4a361309e86469e0fb4617b6a73c4011
# Fri, 10 Aug 2018 22:13:39 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		coreutils 		dpkg-dev dpkg 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl-utils 		perl-ipc-run 		util-linux-dev 		zlib-dev 		icu-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& wget -O config/config.guess 'https://git.savannah.gnu.org/cgit/config.git/plain/config.guess?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& wget -O config/config.sub 'https://git.savannah.gnu.org/cgit/config.git/plain/config.sub?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& ./configure 		--build="$gnuArch" 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 		--with-includes=/usr/local/include 		--with-libraries=/usr/local/lib 				--with-openssl 		--with-libxml 		--with-libxslt 		--with-icu 	&& make -j "$(nproc)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Aug 2018 22:13:42 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Aug 2018 22:13:43 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod 2777 /var/run/postgresql
# Fri, 10 Aug 2018 22:13:43 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Aug 2018 22:13:44 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Aug 2018 22:13:44 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Aug 2018 22:13:45 GMT
COPY file:ea83254240307acb41cff4ba67980cb25f52871869af6e6c49a729ba283f82ed in /usr/local/bin/ 
# Fri, 10 Aug 2018 22:13:45 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Aug 2018 22:13:46 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Aug 2018 22:13:46 GMT
EXPOSE 5432/tcp
# Fri, 10 Aug 2018 22:13:46 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:8e3ba11ec2a2b39ab372c60c16b421536e50e5ce64a0bc81765c2e38381bcff6`  
		Last Modified: Fri, 06 Jul 2018 04:15:58 GMT  
		Size: 2.2 MB (2206542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fbb9adb8cff82fca4ee56d72d6f8084c02ba5ef008039979a1379e9162703cc6`  
		Last Modified: Wed, 11 Jul 2018 01:05:01 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa8817b9e00daac6d86d105d480aa5c8ef78b76903e15283154197774f718e7e`  
		Last Modified: Wed, 11 Jul 2018 01:05:01 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:53941c55569fdc3fbb42e6108e59949220ccb3cd1f131b6ec66889d4143838c8`  
		Last Modified: Fri, 10 Aug 2018 22:36:11 GMT  
		Size: 27.3 MB (27261471 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f66d499835407dfca77ef2ae16684682a2c182ca6a9354e0849cd0ee5f52d6a7`  
		Last Modified: Fri, 10 Aug 2018 22:36:00 GMT  
		Size: 7.3 KB (7268 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d94e4c4de54db6fdee183118b42d86660783559798702580fa2fceb07e0ac1a9`  
		Last Modified: Fri, 10 Aug 2018 22:35:59 GMT  
		Size: 128.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:480f0e20fdcc6b966366f9f25de01a36eeddf028ad249c4f0b86f163bcd90a3b`  
		Last Modified: Fri, 10 Aug 2018 22:35:59 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:949d41f63bfb1de8694f1a5b2fc332ec3a8bc7cffb6984203336dfa7fdbb2c61`  
		Last Modified: Fri, 10 Aug 2018 22:35:59 GMT  
		Size: 2.2 KB (2233 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1dd1895e17aed31bc0980ee677ed5ac9b714fcc3c464ce731a778c221c091816`  
		Last Modified: Fri, 10 Aug 2018 22:36:01 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `postgres:10-alpine` - linux; arm variant v6

```console
$ docker pull postgres@sha256:a05d25543d6fba321eb23e42b9a7c96995a17e0b0959d77dd4f27c71d47b1eb8
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **28.4 MB (28392017 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ce37fba281e9f4c9d90b6d6518e29c03160ea59ba8edf1e2d614d7873b8bf6ee`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Fri, 06 Jul 2018 07:53:29 GMT
ADD file:122e3422d9afa971806601812374fdd9d00c8edc8e9a6df7256e2caa85fab6d1 in / 
# Fri, 06 Jul 2018 07:53:30 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 07:53:30 GMT
CMD ["/bin/sh"]
# Sat, 14 Jul 2018 07:49:44 GMT
RUN set -ex; 	postgresHome="$(getent passwd postgres)"; 	postgresHome="$(echo "$postgresHome" | cut -d: -f6)"; 	[ "$postgresHome" = '/var/lib/postgresql' ]; 	mkdir -p "$postgresHome"; 	chown -R postgres:postgres "$postgresHome"
# Sat, 14 Jul 2018 07:49:45 GMT
ENV LANG=en_US.utf8
# Sat, 14 Jul 2018 07:49:49 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Sat, 14 Jul 2018 08:30:08 GMT
ENV PG_MAJOR=10
# Sat, 11 Aug 2018 08:30:33 GMT
ENV PG_VERSION=10.5
# Sat, 11 Aug 2018 08:30:33 GMT
ENV PG_SHA256=6c8e616c91a45142b85c0aeb1f29ebba4a361309e86469e0fb4617b6a73c4011
# Sat, 11 Aug 2018 09:10:31 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		coreutils 		dpkg-dev dpkg 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl-utils 		perl-ipc-run 		util-linux-dev 		zlib-dev 		icu-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& wget -O config/config.guess 'https://git.savannah.gnu.org/cgit/config.git/plain/config.guess?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& wget -O config/config.sub 'https://git.savannah.gnu.org/cgit/config.git/plain/config.sub?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& ./configure 		--build="$gnuArch" 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 		--with-includes=/usr/local/include 		--with-libraries=/usr/local/lib 				--with-openssl 		--with-libxml 		--with-libxslt 		--with-icu 	&& make -j "$(nproc)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Sat, 11 Aug 2018 09:10:37 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Sat, 11 Aug 2018 09:10:42 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod 2777 /var/run/postgresql
# Sat, 11 Aug 2018 09:10:42 GMT
ENV PGDATA=/var/lib/postgresql/data
# Sat, 11 Aug 2018 09:10:46 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Sat, 11 Aug 2018 09:10:47 GMT
VOLUME [/var/lib/postgresql/data]
# Sat, 11 Aug 2018 09:10:48 GMT
COPY file:ea83254240307acb41cff4ba67980cb25f52871869af6e6c49a729ba283f82ed in /usr/local/bin/ 
# Sat, 11 Aug 2018 09:10:53 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 11 Aug 2018 09:10:54 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 11 Aug 2018 09:10:54 GMT
EXPOSE 5432/tcp
# Sat, 11 Aug 2018 09:10:55 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:ee7d700abbf209aa401ef5d53f86af298a25e8154b3259036e9307d08f255c5d`  
		Last Modified: Fri, 06 Jul 2018 07:53:45 GMT  
		Size: 2.1 MB (2145998 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1653f4692c1ccea69cd46121d4f1371957f66e97a20141371dd4da10ebaec19`  
		Last Modified: Fri, 06 Jul 2018 07:53:45 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:be89c0bdfe21471b24dd28c380bc35cebe521da2e9615c5be939deafd734624c`  
		Last Modified: Sat, 14 Jul 2018 11:40:24 GMT  
		Size: 180.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:852d2cfc5d822ef2846113436b3d9d9264722ad578117a2e770ea982600c9511`  
		Last Modified: Sat, 14 Jul 2018 11:40:22 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:16e39e434588e28fe9226bb7946a0bd3e6b3766c0dfa36ba375f60eaefb2a68f`  
		Last Modified: Sat, 11 Aug 2018 11:29:26 GMT  
		Size: 26.2 MB (26235521 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b940d8a242778c947bf8bf5b7e73ce26c3fc13639318de6cf32c345ce4024cc`  
		Last Modified: Sat, 11 Aug 2018 11:28:46 GMT  
		Size: 7.3 KB (7276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae8268304b4827361932ff170c91bccdbf87fdc49585cc08b73579e9fe4d0f9f`  
		Last Modified: Sat, 11 Aug 2018 11:28:45 GMT  
		Size: 161.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89fe6a6701b9952e1dc4d3814d985f72bf631166e772756b0295e30ed7371fc9`  
		Last Modified: Sat, 11 Aug 2018 11:28:46 GMT  
		Size: 202.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:577ea1a5a8066a147fdcdb7961d66b8fe0e6f202d733582b1814646a0a271238`  
		Last Modified: Sat, 11 Aug 2018 11:28:46 GMT  
		Size: 2.2 KB (2234 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4133f44c1361300dc8a08a4a5171155bf8bc245e9d4c9eebc733478ff98886d6`  
		Last Modified: Sat, 11 Aug 2018 11:28:46 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `postgres:10-alpine` - linux; arm64 variant v8

```console
$ docker pull postgres@sha256:b012dd8f4e6365e29b4ea60591038bf5fcb7d8bd24bf21cbffcfacc65dfe31b5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **28.2 MB (28167091 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:87f24e45bb928d47349026dad90b2b582a228f8e63c91f62086cb9269147efea`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Fri, 06 Jul 2018 08:41:03 GMT
ADD file:199a5a48bddabaf1f649f58f3b17c323a1aa1a50e939dfdea3542e4041e91b7b in / 
# Fri, 06 Jul 2018 08:41:03 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 08:41:04 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 08:58:15 GMT
RUN set -ex; 	postgresHome="$(getent passwd postgres)"; 	postgresHome="$(echo "$postgresHome" | cut -d: -f6)"; 	[ "$postgresHome" = '/var/lib/postgresql' ]; 	mkdir -p "$postgresHome"; 	chown -R postgres:postgres "$postgresHome"
# Wed, 11 Jul 2018 08:58:15 GMT
ENV LANG=en_US.utf8
# Wed, 11 Jul 2018 08:58:17 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 11 Jul 2018 09:03:33 GMT
ENV PG_MAJOR=10
# Sat, 11 Aug 2018 10:49:51 GMT
ENV PG_VERSION=10.5
# Sat, 11 Aug 2018 10:49:54 GMT
ENV PG_SHA256=6c8e616c91a45142b85c0aeb1f29ebba4a361309e86469e0fb4617b6a73c4011
# Sat, 11 Aug 2018 10:54:13 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		coreutils 		dpkg-dev dpkg 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl-utils 		perl-ipc-run 		util-linux-dev 		zlib-dev 		icu-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& wget -O config/config.guess 'https://git.savannah.gnu.org/cgit/config.git/plain/config.guess?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& wget -O config/config.sub 'https://git.savannah.gnu.org/cgit/config.git/plain/config.sub?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& ./configure 		--build="$gnuArch" 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 		--with-includes=/usr/local/include 		--with-libraries=/usr/local/lib 				--with-openssl 		--with-libxml 		--with-libxslt 		--with-icu 	&& make -j "$(nproc)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Sat, 11 Aug 2018 10:54:15 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Sat, 11 Aug 2018 10:54:33 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod 2777 /var/run/postgresql
# Sat, 11 Aug 2018 10:54:33 GMT
ENV PGDATA=/var/lib/postgresql/data
# Sat, 11 Aug 2018 10:54:35 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Sat, 11 Aug 2018 10:54:36 GMT
VOLUME [/var/lib/postgresql/data]
# Sat, 11 Aug 2018 10:54:37 GMT
COPY file:ea83254240307acb41cff4ba67980cb25f52871869af6e6c49a729ba283f82ed in /usr/local/bin/ 
# Sat, 11 Aug 2018 10:54:38 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 11 Aug 2018 10:54:39 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 11 Aug 2018 10:54:56 GMT
EXPOSE 5432/tcp
# Sat, 11 Aug 2018 10:54:57 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:47e04371c99027fae42871b720fdc6cdddcb65062bfa05f0c3bb0a594cb5bbbd`  
		Last Modified: Wed, 27 Jun 2018 19:15:35 GMT  
		Size: 2.1 MB (2099514 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b4103359e1ecd9a7253d8b8a041d4e81db1ff4a5e1950bc0e02305d221c9e6c2`  
		Last Modified: Fri, 06 Jul 2018 08:42:09 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:437d5ea65f8f13faa3042893bc9dd0a4e5b68562c0eb1f9aeaf258936fe72140`  
		Last Modified: Wed, 11 Jul 2018 09:26:40 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cf835df21096513cbddcf69a9b532c79832f2cd1c8b47e78e9776fc76eb24340`  
		Last Modified: Wed, 11 Jul 2018 09:26:41 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:29b4e744483cc77038930b8fb4a44ab762ee1bb797a69fb2096e28cc3ef46e96`  
		Last Modified: Sat, 11 Aug 2018 13:07:28 GMT  
		Size: 26.1 MB (26057221 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:754968dc29e2f3c1377a2f10894b4710076dcc75f0ca210d339b7ece8b8cc2d8`  
		Last Modified: Sat, 11 Aug 2018 13:07:17 GMT  
		Size: 7.3 KB (7269 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d201cca107eb5796e3c00743e6623381535a085a7352e4cf721d73ab95a2361f`  
		Last Modified: Sat, 11 Aug 2018 13:07:17 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e88b1cfc6485b8b4e3693a2254bee99be74988aaf7aea95a48b1d61999a2c6df`  
		Last Modified: Sat, 11 Aug 2018 13:07:17 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95ec9bc2a7a450ab7c2712e8d268a7d74b4a93e4d282d6a26fc2d753d8d49414`  
		Last Modified: Sat, 11 Aug 2018 13:07:17 GMT  
		Size: 2.2 KB (2228 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c3ace28c13f82b7d65200807fbba18cd3c7ad8bd0046b3a925ccae72dd39574`  
		Last Modified: Sat, 11 Aug 2018 13:07:17 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `postgres:10-alpine` - linux; 386

```console
$ docker pull postgres@sha256:fb50656a2733df8c4d06f864904e44b8f87817ec9c3a91d5e8a559c5dce41697
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **30.2 MB (30206915 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0b6ad4b55bab3d474fd413d8b7d925e5147c5537c71405c14699b8a246cf294e`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Fri, 06 Jul 2018 15:02:06 GMT
ADD file:ebd40cda2f6087daf4d14e6dc1ee0b4a0fb5dc96c70129be8e07de0e5c628312 in / 
# Fri, 06 Jul 2018 15:02:07 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 15:02:07 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 10:50:41 GMT
RUN set -ex; 	postgresHome="$(getent passwd postgres)"; 	postgresHome="$(echo "$postgresHome" | cut -d: -f6)"; 	[ "$postgresHome" = '/var/lib/postgresql' ]; 	mkdir -p "$postgresHome"; 	chown -R postgres:postgres "$postgresHome"
# Wed, 11 Jul 2018 10:50:42 GMT
ENV LANG=en_US.utf8
# Wed, 11 Jul 2018 10:50:42 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 11 Jul 2018 10:53:45 GMT
ENV PG_MAJOR=10
# Sat, 11 Aug 2018 11:23:37 GMT
ENV PG_VERSION=10.5
# Sat, 11 Aug 2018 11:23:37 GMT
ENV PG_SHA256=6c8e616c91a45142b85c0aeb1f29ebba4a361309e86469e0fb4617b6a73c4011
# Sat, 11 Aug 2018 11:26:21 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		coreutils 		dpkg-dev dpkg 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl-utils 		perl-ipc-run 		util-linux-dev 		zlib-dev 		icu-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& wget -O config/config.guess 'https://git.savannah.gnu.org/cgit/config.git/plain/config.guess?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& wget -O config/config.sub 'https://git.savannah.gnu.org/cgit/config.git/plain/config.sub?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& ./configure 		--build="$gnuArch" 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 		--with-includes=/usr/local/include 		--with-libraries=/usr/local/lib 				--with-openssl 		--with-libxml 		--with-libxslt 		--with-icu 	&& make -j "$(nproc)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Sat, 11 Aug 2018 11:26:30 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Sat, 11 Aug 2018 11:26:31 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod 2777 /var/run/postgresql
# Sat, 11 Aug 2018 11:26:31 GMT
ENV PGDATA=/var/lib/postgresql/data
# Sat, 11 Aug 2018 11:26:32 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Sat, 11 Aug 2018 11:26:33 GMT
VOLUME [/var/lib/postgresql/data]
# Sat, 11 Aug 2018 11:26:33 GMT
COPY file:ea83254240307acb41cff4ba67980cb25f52871869af6e6c49a729ba283f82ed in /usr/local/bin/ 
# Sat, 11 Aug 2018 11:26:34 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 11 Aug 2018 11:26:47 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 11 Aug 2018 11:26:47 GMT
EXPOSE 5432/tcp
# Sat, 11 Aug 2018 11:26:48 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:ef15772113129a5330876ce10683bbf6509a4c4c99b3a99894dcbc7560975052`  
		Last Modified: Fri, 06 Jul 2018 15:02:46 GMT  
		Size: 2.3 MB (2270920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6df692b84cf35e6038d677f9ab7de2a3c671c57671043da1d20d99252e0d9c42`  
		Last Modified: Fri, 06 Jul 2018 15:02:43 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:68f1f64a5de43fc9cf3d68cbe05f2a18e17a39e44d1512ce0b3911f2bc59f77e`  
		Last Modified: Wed, 11 Jul 2018 11:09:05 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72347c8a13f638fd36f586cfa21f37b4da1dd04bab6b6204d3ce2dc8f04d98e8`  
		Last Modified: Wed, 11 Jul 2018 11:09:04 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5d77d752dd8d5285c3b238b977bfb904880664a418631ed82823bd09a740fc82`  
		Last Modified: Sat, 11 Aug 2018 11:49:20 GMT  
		Size: 27.9 MB (27925636 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a0888ccd39fdd5bc8f9ae6f9405fe08686f800b49a5462ee6b44b6130bd9001c`  
		Last Modified: Sat, 11 Aug 2018 11:49:06 GMT  
		Size: 7.3 KB (7268 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed8ebbfcefc9f01d6aaee0fde94081d52e04753de08d42d4dfd1f6d6a9eae1eb`  
		Last Modified: Sat, 11 Aug 2018 11:49:06 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4d8e4c3fa9c8b3fe05b713947a3f6f58609f7225c7ccd22871497ead758a1496`  
		Last Modified: Sat, 11 Aug 2018 11:49:06 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a830561d4bd81db660ec806dc70c7805dd91a2ec63cc0b355637444541313758`  
		Last Modified: Sat, 11 Aug 2018 11:49:06 GMT  
		Size: 2.2 KB (2232 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4dab066c68264b468f1fa23c9e4157d2d1585617a80bcb561205cfe8e60ace70`  
		Last Modified: Sat, 11 Aug 2018 11:49:06 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `postgres:10-alpine` - linux; ppc64le

```console
$ docker pull postgres@sha256:a7dd2577142086b3bb0846881ac0f44692dc7d789bf004ef1dc398ca0fa66982
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **29.2 MB (29151341 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:01e10ca0489826380bd647e3290100a1bd39a0053c1cc29c873f65df577c88d5`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Fri, 06 Jul 2018 08:18:09 GMT
ADD file:4ff20d593b16518d45b1b1d6efdab141199316dba7a53ce7459249f5de690dfd in / 
# Fri, 06 Jul 2018 08:18:10 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 08:18:11 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 10:01:28 GMT
RUN set -ex; 	postgresHome="$(getent passwd postgres)"; 	postgresHome="$(echo "$postgresHome" | cut -d: -f6)"; 	[ "$postgresHome" = '/var/lib/postgresql' ]; 	mkdir -p "$postgresHome"; 	chown -R postgres:postgres "$postgresHome"
# Wed, 11 Jul 2018 10:01:29 GMT
ENV LANG=en_US.utf8
# Wed, 11 Jul 2018 10:01:32 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 11 Jul 2018 10:07:00 GMT
ENV PG_MAJOR=10
# Sat, 11 Aug 2018 09:40:32 GMT
ENV PG_VERSION=10.5
# Sat, 11 Aug 2018 09:40:35 GMT
ENV PG_SHA256=6c8e616c91a45142b85c0aeb1f29ebba4a361309e86469e0fb4617b6a73c4011
# Sat, 11 Aug 2018 09:46:47 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		coreutils 		dpkg-dev dpkg 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl-utils 		perl-ipc-run 		util-linux-dev 		zlib-dev 		icu-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& wget -O config/config.guess 'https://git.savannah.gnu.org/cgit/config.git/plain/config.guess?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& wget -O config/config.sub 'https://git.savannah.gnu.org/cgit/config.git/plain/config.sub?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& ./configure 		--build="$gnuArch" 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 		--with-includes=/usr/local/include 		--with-libraries=/usr/local/lib 				--with-openssl 		--with-libxml 		--with-libxslt 		--with-icu 	&& make -j "$(nproc)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Sat, 11 Aug 2018 09:46:50 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Sat, 11 Aug 2018 09:46:52 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod 2777 /var/run/postgresql
# Sat, 11 Aug 2018 09:46:53 GMT
ENV PGDATA=/var/lib/postgresql/data
# Sat, 11 Aug 2018 09:46:56 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Sat, 11 Aug 2018 09:46:58 GMT
VOLUME [/var/lib/postgresql/data]
# Sat, 11 Aug 2018 09:47:00 GMT
COPY file:ea83254240307acb41cff4ba67980cb25f52871869af6e6c49a729ba283f82ed in /usr/local/bin/ 
# Sat, 11 Aug 2018 09:47:02 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 11 Aug 2018 09:47:04 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 11 Aug 2018 09:47:06 GMT
EXPOSE 5432/tcp
# Sat, 11 Aug 2018 09:47:07 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:e642bcb5b1890a07dd2fc8be2bc35edf5e2b651d4993e71caef03b4b43ace970`  
		Last Modified: Fri, 06 Jul 2018 08:18:44 GMT  
		Size: 2.2 MB (2194861 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2e09410b1fce4c4630b3bc57c6ee158ee9821ec415d0acaa1607b9e0bcf76d91`  
		Last Modified: Fri, 06 Jul 2018 08:18:43 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:99cf65db7a2a46b10230d6919606d6370a8f89f4126cb2e72c0e8e2b817cc9bd`  
		Last Modified: Wed, 11 Jul 2018 10:24:59 GMT  
		Size: 180.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:831e22a24061ee9561c3ce50ae211d56c4d735d93bc6f6ba82661c69ebaaea94`  
		Last Modified: Wed, 11 Jul 2018 10:24:59 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc13d067e3243929f148769ea65e730415b345aa69030b69dc3af2e47072e37a`  
		Last Modified: Sat, 11 Aug 2018 10:18:22 GMT  
		Size: 26.9 MB (26945998 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7959398ec44a859dfad07a4810bcfc0dac843b47c34be3681fd799582bb92b7e`  
		Last Modified: Sat, 11 Aug 2018 10:18:03 GMT  
		Size: 7.3 KB (7263 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e3dc869c82e2c858f2febd6ed77d5e144090f89b4da520b3c34f1fe5d29a5c55`  
		Last Modified: Sat, 11 Aug 2018 10:18:03 GMT  
		Size: 161.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a54076e44479aa2f70828aa758dbc2157f8edba9b731cade4f0861393b53012d`  
		Last Modified: Sat, 11 Aug 2018 10:18:03 GMT  
		Size: 202.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c447f3285a6ff327ac040a073aa3d2e323ebab8f617e7ab6f7b46eeca5d61ce`  
		Last Modified: Sat, 11 Aug 2018 10:18:03 GMT  
		Size: 2.2 KB (2230 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d347d85f86e1e6750af2c558a5cb39fde83b859cf015283bdb37489fb3169031`  
		Last Modified: Sat, 11 Aug 2018 10:18:03 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `postgres:10-alpine` - linux; s390x

```console
$ docker pull postgres@sha256:8075a85ede2a17a5a9df21936478a743e10c7e70b2654164238fe6be3167c1fb
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **29.5 MB (29474214 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:acc9b1d7247b2e9969a74c52c602246f0c5cd451ffe1c6de6bbf186895b6b8ab`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Fri, 06 Jul 2018 11:41:42 GMT
ADD file:376dd7fc34ad39570d2e20f3704305e788ae613c589445b3e8fb880147c3eb59 in / 
# Fri, 06 Jul 2018 11:41:43 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 11:41:43 GMT
CMD ["/bin/sh"]
# Wed, 11 Jul 2018 11:52:46 GMT
RUN set -ex; 	postgresHome="$(getent passwd postgres)"; 	postgresHome="$(echo "$postgresHome" | cut -d: -f6)"; 	[ "$postgresHome" = '/var/lib/postgresql' ]; 	mkdir -p "$postgresHome"; 	chown -R postgres:postgres "$postgresHome"
# Wed, 11 Jul 2018 11:52:46 GMT
ENV LANG=en_US.utf8
# Wed, 11 Jul 2018 11:52:47 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 11 Jul 2018 11:55:40 GMT
ENV PG_MAJOR=10
# Sat, 11 Aug 2018 12:25:22 GMT
ENV PG_VERSION=10.5
# Sat, 11 Aug 2018 12:25:22 GMT
ENV PG_SHA256=6c8e616c91a45142b85c0aeb1f29ebba4a361309e86469e0fb4617b6a73c4011
# Sat, 11 Aug 2018 12:27:57 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		coreutils 		dpkg-dev dpkg 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl-utils 		perl-ipc-run 		util-linux-dev 		zlib-dev 		icu-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& wget -O config/config.guess 'https://git.savannah.gnu.org/cgit/config.git/plain/config.guess?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& wget -O config/config.sub 'https://git.savannah.gnu.org/cgit/config.git/plain/config.sub?id=7d3d27baf8107b630586c962c057e22149653deb' 	&& ./configure 		--build="$gnuArch" 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 		--with-includes=/usr/local/include 		--with-libraries=/usr/local/lib 				--with-openssl 		--with-libxml 		--with-libxslt 		--with-icu 	&& make -j "$(nproc)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Sat, 11 Aug 2018 12:27:58 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Sat, 11 Aug 2018 12:27:59 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod 2777 /var/run/postgresql
# Sat, 11 Aug 2018 12:27:59 GMT
ENV PGDATA=/var/lib/postgresql/data
# Sat, 11 Aug 2018 12:27:59 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Sat, 11 Aug 2018 12:27:59 GMT
VOLUME [/var/lib/postgresql/data]
# Sat, 11 Aug 2018 12:28:00 GMT
COPY file:ea83254240307acb41cff4ba67980cb25f52871869af6e6c49a729ba283f82ed in /usr/local/bin/ 
# Sat, 11 Aug 2018 12:28:00 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Sat, 11 Aug 2018 12:28:00 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 11 Aug 2018 12:28:01 GMT
EXPOSE 5432/tcp
# Sat, 11 Aug 2018 12:28:01 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:cdf21ace94188d512903eea53ea8559677e0e6ffd5d6a180a1d88c118abc96fc`  
		Last Modified: Fri, 06 Jul 2018 11:42:01 GMT  
		Size: 2.3 MB (2307471 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea178433f2f09080fbbf77f09da1b16d588b7ced380d495a2f2ad00d28468338`  
		Last Modified: Fri, 06 Jul 2018 11:42:00 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:398fccf2ffccf7250c1715d26143118893acb524a48bced68b09ea5b8eec51d5`  
		Last Modified: Wed, 11 Jul 2018 12:07:23 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9218ec3eacdd51c0198b5043ce0115b269b534e8da4fd8aa0f07d1b7e3f1f1ab`  
		Last Modified: Wed, 11 Jul 2018 12:07:23 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c2af030b6361a1d210429175e5a975de83ff31121439a1a5c257b86600568145`  
		Last Modified: Sat, 11 Aug 2018 13:11:19 GMT  
		Size: 27.2 MB (27156391 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14aa2a2eaed2fc2aa0b6ec951f7c0a46b58dc5bf1de5e4a34b6744b304d52431`  
		Last Modified: Sat, 11 Aug 2018 13:11:13 GMT  
		Size: 7.3 KB (7265 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:44df75bb4398e3b231b785311bc7fd8087cbd79c6657441010272c76502eeb4f`  
		Last Modified: Sat, 11 Aug 2018 13:11:13 GMT  
		Size: 128.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36e4e319c24f736dd1d16ef53895387e1afc424fe2d9c16f9b43f73d525f38c5`  
		Last Modified: Sat, 11 Aug 2018 13:11:13 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70df74b34f6c1ca4b552c4f6616818d9dd2a7a19e762563c3b9b3e78c9518122`  
		Last Modified: Sat, 11 Aug 2018 13:11:15 GMT  
		Size: 2.2 KB (2230 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b99046badd7ef4212b271889e05aa431ef3a981cfe60c265856eda4325c2dd4c`  
		Last Modified: Sat, 11 Aug 2018 13:11:13 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
