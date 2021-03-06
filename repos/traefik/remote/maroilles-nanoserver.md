## `traefik:maroilles-nanoserver`

```console
$ docker pull traefik@sha256:debba1884c044f27861d706adfc4f8106ad2cf814f6bbed2b6272a13979ba41d
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2430; amd64

### `traefik:maroilles-nanoserver` - windows version 10.0.14393.2430; amd64

```console
$ docker pull traefik@sha256:cadfa1176dd039b361fdadee56a10b7795d9c8f2cae213b826ba03b83de283e3
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **436.5 MB (436517803 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:eaf162278b4ca0c2ed2defb77f03f7328f3d826b2a1a29e6d09209f39204575d`
-	Entrypoint: `["\/traefik"]`

```dockerfile
# Tue, 13 Dec 2016 10:47:17 GMT
RUN Apply image 10.0.14393.0
# Mon, 13 Aug 2018 17:51:52 GMT
RUN Install update 10.0.14393.2430
# Tue, 21 Aug 2018 09:16:57 GMT
RUN cmd /S /C #(nop) COPY file:4c94379aa4d378c3412fd0a5ac3edfef56d6836d9638f135e43481fdbadf297c in \traefik.exe 
# Tue, 21 Aug 2018 09:17:00 GMT
RUN cmd /S /C #(nop)  VOLUME [C:/etc/traefik]
# Tue, 21 Aug 2018 09:17:01 GMT
RUN cmd /S /C #(nop)  VOLUME [C:/etc/ssl]
# Tue, 21 Aug 2018 09:17:02 GMT
RUN cmd /S /C #(nop)  EXPOSE 80/tcp
# Tue, 21 Aug 2018 09:17:03 GMT
RUN cmd /S /C #(nop)  ENTRYPOINT ["/traefik"]
# Tue, 21 Aug 2018 09:17:04 GMT
RUN cmd /S /C #(nop)  LABEL org.label-schema.vendor=Containous org.label-schema.url=https://traefik.io org.label-schema.name=Traefik org.label-schema.description=A modern reverse-proxy org.label-schema.version=v1.7.0-rc3 org.label-schema.docker.schema-version=1.0
```

-	Layers:
	-	`sha256:bce2fbc256ea437a87dadac2f69aabd25bed4f56255549090056c1131fad0277`  
		Last Modified: Tue, 13 Dec 2016 10:47:17 GMT  
		Size: 252.7 MB (252691002 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:4a14bdf6da80603aa5007acea8d5ea659958b0bd1b31d31078023ca0d1c8ee05`  
		Last Modified: Mon, 13 Aug 2018 17:51:52 GMT  
		Size: 167.8 MB (167784035 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:46d151ccc57c66b81533f08eac23921137138ab6cbe08ce1ebdd16f53e32c418`  
		Last Modified: Tue, 21 Aug 2018 09:17:49 GMT  
		Size: 16.0 MB (16038019 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b4a13815a4bd4125fc9b4f43a991468472e584d829f4826885b302a57487bb9`  
		Last Modified: Tue, 21 Aug 2018 09:17:42 GMT  
		Size: 951.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c18f20c67e0d78856ae46fde0622ca19b8e2eee77950da788adc44bbc9b31a1`  
		Last Modified: Tue, 21 Aug 2018 09:17:42 GMT  
		Size: 951.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a379df6ee7c75f776527876236959161344c2469e9e2ee54dcafe6acb92e198e`  
		Last Modified: Tue, 21 Aug 2018 09:17:42 GMT  
		Size: 947.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e5f5df4671a88bd9e59f8952857b56eb0bcf69de947b9dead277bfbbb1a20b6`  
		Last Modified: Tue, 21 Aug 2018 09:17:42 GMT  
		Size: 952.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03bc7fd5919672325eb397a20c966165e54a47b968f38f3faf675c3985095c30`  
		Last Modified: Tue, 21 Aug 2018 09:17:43 GMT  
		Size: 946.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
