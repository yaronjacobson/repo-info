## `websphere-liberty:beta`

```console
$ docker pull websphere-liberty@sha256:6861dfa1c4bb9c07e95b2ff71b6faf1e12cf58d62f361e105d231f32e35af8d3
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `websphere-liberty:beta` - linux; amd64

```console
$ docker pull websphere-liberty@sha256:881f276a4f4d5656831c31f73b855541964218cba51af4a70c7a0783c3c5214b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **273.3 MB (273283156 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a6081fdc680ba8ae1a72b418cacb2dda942ca15336e2ae301826367a8d045ed6`
-	Default Command: `["\/opt\/ibm\/wlp\/bin\/server","run","defaultServer"]`

```dockerfile
# Thu, 26 Jul 2018 22:23:08 GMT
ADD file:204fb7ccb19ff7e863331131138621ff4d22720b3718e8f296902cc7d4f635b5 in / 
# Thu, 26 Jul 2018 22:23:09 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 26 Jul 2018 22:23:09 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 26 Jul 2018 22:23:10 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 26 Jul 2018 22:23:11 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 26 Jul 2018 22:23:11 GMT
CMD ["/bin/bash"]
# Thu, 26 Jul 2018 23:14:00 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Thu, 26 Jul 2018 23:14:13 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Mon, 13 Aug 2018 22:21:13 GMT
ENV JAVA_VERSION=1.8.0_sr5fp20
# Mon, 13 Aug 2018 22:22:05 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='b2dfbdac0fda3fd8ecea6d9d145da7d6f9fa79fe5cfc13dd3862fc331b8698de';          YML_FILE='jre/linux/x86_64/index.yml';          ;;        i386)          ESUM='b4f525b885ca369b1ab626d552e3ed74f5c6ccc674fcaf5340ecbd9aa046c1eb';          YML_FILE='jre/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='bf824a43250b64a85f86e43ee75543de235a4e768f5cc540d4e8b0f4fae2ff18';          YML_FILE='jre/linux/ppc64le/index.yml';          ;;        s390)          ESUM='f216bf12f094e48c3bf05a45d27669f047670e734d4be3f4015257d42a6b1990';          YML_FILE='jre/linux/s390/index.yml';          ;;        s390x)          ESUM='24acc20c2487f2e3a3246c86a10b90b0d7ce6121d923bd7405a1c53e119094ac';          YML_FILE='jre/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(sed -n '/^'${JAVA_VERSION}:'/{n;s/\s*uri:\s//p}'< /tmp/index.yml);     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Mon, 13 Aug 2018 22:22:05 GMT
ENV JAVA_HOME=/opt/ibm/java/jre PATH=/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin IBM_JAVA_OPTIONS=-XX:+UseContainerSupport
# Mon, 13 Aug 2018 23:17:21 GMT
LABEL maintainer=Arthur De Magalhaes <arthurdm@ca.ibm.com> (@arthurdm)
# Mon, 13 Aug 2018 23:17:28 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends unzip     && rm -rf /var/lib/apt/lists/*
# Mon, 13 Aug 2018 23:33:01 GMT
ENV LIBERTY_VERSION=2018.8.0_0
# Mon, 13 Aug 2018 23:33:19 GMT
RUN LIBERTY_URL=$(wget -q -O - https://public.dhe.ibm.com/ibmdl/export/pub/software/websphere/wasdev/downloads/wlp/index.yml  | grep $LIBERTY_VERSION -A 3 | sed -n 's/\s*webProfile7:\s//p' | tr -d '\r')      && echo $LIBERTY_URL     && wget -q $LIBERTY_URL -U UA-IBM-WebSphere-Liberty-Docker -O /tmp/wlp-beta.zip     && unzip -q /tmp/wlp-beta.zip -d /opt/ibm     && rm /tmp/wlp-beta.zip
# Mon, 13 Aug 2018 23:33:20 GMT
ENV PATH=/opt/ibm/wlp/bin:/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 13 Aug 2018 23:33:20 GMT
ENV LOG_DIR=/logs WLP_OUTPUT_DIR=/opt/ibm/wlp/output
# Mon, 13 Aug 2018 23:33:21 GMT
RUN mkdir /logs     && ln -s $WLP_OUTPUT_DIR/defaultServer /output     && ln -s /opt/ibm/wlp/usr/servers/defaultServer /config     && ln -s /opt/ibm /liberty
# Mon, 13 Aug 2018 23:33:23 GMT
RUN /opt/ibm/wlp/bin/server create     && rm -rf $WLP_OUTPUT_DIR/.classCache /output/workarea
# Mon, 13 Aug 2018 23:33:23 GMT
COPY file:3b23d7d17672e2c49786942609f319a90591738e9dfd67f95b1df374561c29ce in /opt/ibm/wlp/usr/servers/defaultServer/ 
# Mon, 13 Aug 2018 23:33:23 GMT
EXPOSE 9080/tcp 9443/tcp
# Mon, 13 Aug 2018 23:33:23 GMT
CMD ["/opt/ibm/wlp/bin/server" "run" "defaultServer"]
```

-	Layers:
	-	`sha256:8ee29e426c26c79e7ba03ccc8bbc7fe99db00ffcbccb679d9c643b5546d8dc8a`  
		Last Modified: Thu, 26 Jul 2018 22:27:22 GMT  
		Size: 43.2 MB (43228646 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e83b260b73b908ebabde46b72fc5790bf4f029b53acbbfe35da8ff8fba795ac`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e26b65fd1143ee4f9b7b6b958aeafdb996172d10b723f0bba24335a8f7ae692c`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 618.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40dca07f8222e24aab97f026444d66a7604e4ae2b708cf079ff67a90c42efa60`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b420ae9e10b3f6a74f527914bc3c766b128435a62eca1061f41167205d5b0230`  
		Last Modified: Thu, 26 Jul 2018 22:26:54 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7a0a3902ea56575347cec98de9cdea35051edefa24d67eccb50d1883d1343fdb`  
		Last Modified: Thu, 26 Jul 2018 23:22:16 GMT  
		Size: 3.0 MB (3021010 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01da43ccf6625a7f02104b7b1e0d7d5830af2342d2325f3b602cb0348daf11a4`  
		Last Modified: Mon, 13 Aug 2018 22:28:41 GMT  
		Size: 127.7 MB (127680807 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:112122e37aaf233d36dffe8730b9e40099be847317cdaf295eabe7103c28ca29`  
		Last Modified: Mon, 13 Aug 2018 23:33:48 GMT  
		Size: 422.3 KB (422323 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:74ab4f9b1981e28c9652056810ec3910f5d8294bf7af509487cfe14520577100`  
		Last Modified: Mon, 13 Aug 2018 23:38:30 GMT  
		Size: 98.9 MB (98925650 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9046418943eec8e122db6c983b79f54da47d08d26e7abc0a313a6741781148ea`  
		Last Modified: Mon, 13 Aug 2018 23:38:16 GMT  
		Size: 195.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:463ddbc8d1b195268ee7e64384d5ead0a349e7546354d9de980b06b2c64755c7`  
		Last Modified: Mon, 13 Aug 2018 23:38:17 GMT  
		Size: 1.6 KB (1619 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11c05a811be444d41b933a9b48274316ce64648f5d164d3b5b1d0f1725cabcc6`  
		Last Modified: Mon, 13 Aug 2018 23:38:16 GMT  
		Size: 420.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `websphere-liberty:beta` - linux; 386

```console
$ docker pull websphere-liberty@sha256:dcdab7f3c707dccd8c99300b44c9e10db48f0b127a03e8eae51de3c5dad3619a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **261.6 MB (261551311 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e67440753d2d09ca6014bdd6f7e35a7e2945ecbc514f27e5166fbe4ca90779a1`
-	Default Command: `["\/opt\/ibm\/wlp\/bin\/server","run","defaultServer"]`

```dockerfile
# Fri, 27 Jul 2018 11:04:12 GMT
ADD file:bf213ed5365ee4c9a7f64ec5c337df6779168f609a0fb0ddd2cdf558df419aca in / 
# Fri, 27 Jul 2018 11:04:13 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Fri, 27 Jul 2018 11:04:14 GMT
RUN rm -rf /var/lib/apt/lists/*
# Fri, 27 Jul 2018 11:04:15 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Fri, 27 Jul 2018 11:04:16 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Fri, 27 Jul 2018 11:04:16 GMT
CMD ["/bin/bash"]
# Fri, 27 Jul 2018 11:38:49 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Fri, 27 Jul 2018 11:39:16 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 11:11:05 GMT
ENV JAVA_VERSION=1.8.0_sr5fp20
# Tue, 14 Aug 2018 11:11:55 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='b2dfbdac0fda3fd8ecea6d9d145da7d6f9fa79fe5cfc13dd3862fc331b8698de';          YML_FILE='jre/linux/x86_64/index.yml';          ;;        i386)          ESUM='b4f525b885ca369b1ab626d552e3ed74f5c6ccc674fcaf5340ecbd9aa046c1eb';          YML_FILE='jre/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='bf824a43250b64a85f86e43ee75543de235a4e768f5cc540d4e8b0f4fae2ff18';          YML_FILE='jre/linux/ppc64le/index.yml';          ;;        s390)          ESUM='f216bf12f094e48c3bf05a45d27669f047670e734d4be3f4015257d42a6b1990';          YML_FILE='jre/linux/s390/index.yml';          ;;        s390x)          ESUM='24acc20c2487f2e3a3246c86a10b90b0d7ce6121d923bd7405a1c53e119094ac';          YML_FILE='jre/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(sed -n '/^'${JAVA_VERSION}:'/{n;s/\s*uri:\s//p}'< /tmp/index.yml);     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Tue, 14 Aug 2018 11:11:55 GMT
ENV JAVA_HOME=/opt/ibm/java/jre PATH=/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin IBM_JAVA_OPTIONS=-XX:+UseContainerSupport
# Tue, 14 Aug 2018 11:41:00 GMT
LABEL maintainer=Arthur De Magalhaes <arthurdm@ca.ibm.com> (@arthurdm)
# Tue, 14 Aug 2018 11:41:18 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends unzip     && rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 11:54:30 GMT
ENV LIBERTY_VERSION=2018.8.0_0
# Tue, 14 Aug 2018 11:54:48 GMT
RUN LIBERTY_URL=$(wget -q -O - https://public.dhe.ibm.com/ibmdl/export/pub/software/websphere/wasdev/downloads/wlp/index.yml  | grep $LIBERTY_VERSION -A 3 | sed -n 's/\s*webProfile7:\s//p' | tr -d '\r')      && echo $LIBERTY_URL     && wget -q $LIBERTY_URL -U UA-IBM-WebSphere-Liberty-Docker -O /tmp/wlp-beta.zip     && unzip -q /tmp/wlp-beta.zip -d /opt/ibm     && rm /tmp/wlp-beta.zip
# Tue, 14 Aug 2018 11:54:48 GMT
ENV PATH=/opt/ibm/wlp/bin:/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 11:54:49 GMT
ENV LOG_DIR=/logs WLP_OUTPUT_DIR=/opt/ibm/wlp/output
# Tue, 14 Aug 2018 11:54:49 GMT
RUN mkdir /logs     && ln -s $WLP_OUTPUT_DIR/defaultServer /output     && ln -s /opt/ibm/wlp/usr/servers/defaultServer /config     && ln -s /opt/ibm /liberty
# Tue, 14 Aug 2018 11:54:51 GMT
RUN /opt/ibm/wlp/bin/server create     && rm -rf $WLP_OUTPUT_DIR/.classCache /output/workarea
# Tue, 14 Aug 2018 11:54:52 GMT
COPY file:3b23d7d17672e2c49786942609f319a90591738e9dfd67f95b1df374561c29ce in /opt/ibm/wlp/usr/servers/defaultServer/ 
# Tue, 14 Aug 2018 11:54:52 GMT
EXPOSE 9080/tcp 9443/tcp
# Tue, 14 Aug 2018 11:54:52 GMT
CMD ["/opt/ibm/wlp/bin/server" "run" "defaultServer"]
```

-	Layers:
	-	`sha256:79c3321cd1db5170b2b17e4e7904e999afc88c5ba9168e6632c722f0ced80f2b`  
		Last Modified: Fri, 27 Jul 2018 11:08:03 GMT  
		Size: 43.5 MB (43498084 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5dc08ce9a961adeec10d1eadfa16bc1cb9d2f8994e5d43432500a75cfaa09c6c`  
		Last Modified: Fri, 27 Jul 2018 11:07:46 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84d8c15b299b1de7aa1b6fb37d83b146c59e520ce7bfc25254544262ca705b48`  
		Last Modified: Fri, 27 Jul 2018 11:07:46 GMT  
		Size: 584.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a97a3925b890b18279fac470160ce2e973a10ef456dce7d174780d4e24550f3`  
		Last Modified: Fri, 27 Jul 2018 11:07:46 GMT  
		Size: 849.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c844083148ae3343326e2b07dc524e55fee4f261a1637e68ac86a32b97c4ce16`  
		Last Modified: Fri, 27 Jul 2018 11:07:46 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a671001a55a0ce3af1d3064a1d7f01929b03423102de31cd7a87dd86f9751cd1`  
		Last Modified: Fri, 27 Jul 2018 11:43:11 GMT  
		Size: 2.9 MB (2875978 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebf1c7d8d3570a128e852fb2ae238df36286ff940f972ef1e06ddf48c532eb1d`  
		Last Modified: Tue, 14 Aug 2018 11:14:55 GMT  
		Size: 115.8 MB (115826066 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c236c11960c0afaa57e2847a219cb26308cc4cd5a8c1b49e99454bd6cfb041b8`  
		Last Modified: Tue, 14 Aug 2018 11:55:16 GMT  
		Size: 420.9 KB (420854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7a79d050ccbcd92226ff5efdd9972442c48fc3ac5d7b084ef328bd004f6af954`  
		Last Modified: Tue, 14 Aug 2018 11:59:54 GMT  
		Size: 98.9 MB (98925652 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9e51ee2ece134272b2f838692fcad370535ef87b2b5ce906e1330a5fed76d3fe`  
		Last Modified: Tue, 14 Aug 2018 11:59:39 GMT  
		Size: 196.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:528fc60898b732bf2d98a3770d78146b1c49edd97fadd24e6e723eab52ce67ef`  
		Last Modified: Tue, 14 Aug 2018 11:59:40 GMT  
		Size: 1.6 KB (1619 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:064debbe07f0f477c94182dd55d545c553537b72a5164c2dff27739652a537bf`  
		Last Modified: Tue, 14 Aug 2018 11:59:39 GMT  
		Size: 416.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `websphere-liberty:beta` - linux; ppc64le

```console
$ docker pull websphere-liberty@sha256:83c58176c212888532e05d27e2360476eb3abf9aded70ca60d29c00fbc5da7e0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **288.9 MB (288887941 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5fb0587809c9c0086c65fc88f3119415d14de94b5e79610c599c7dcabe129162`
-	Default Command: `["\/opt\/ibm\/wlp\/bin\/server","run","defaultServer"]`

```dockerfile
# Tue, 21 Aug 2018 18:05:28 GMT
ADD file:9b4fe2a37936425ff1c2483bfa0ff02ada7e549481bd7d0377a94850e5152510 in / 
# Tue, 21 Aug 2018 18:05:53 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 21 Aug 2018 18:05:57 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 21 Aug 2018 18:06:00 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 21 Aug 2018 18:06:05 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 21 Aug 2018 18:06:12 GMT
CMD ["/bin/bash"]
# Tue, 21 Aug 2018 18:26:00 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Tue, 21 Aug 2018 18:27:33 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Tue, 21 Aug 2018 18:27:35 GMT
ENV JAVA_VERSION=1.8.0_sr5fp20
# Tue, 21 Aug 2018 18:31:50 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='b2dfbdac0fda3fd8ecea6d9d145da7d6f9fa79fe5cfc13dd3862fc331b8698de';          YML_FILE='jre/linux/x86_64/index.yml';          ;;        i386)          ESUM='b4f525b885ca369b1ab626d552e3ed74f5c6ccc674fcaf5340ecbd9aa046c1eb';          YML_FILE='jre/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='bf824a43250b64a85f86e43ee75543de235a4e768f5cc540d4e8b0f4fae2ff18';          YML_FILE='jre/linux/ppc64le/index.yml';          ;;        s390)          ESUM='f216bf12f094e48c3bf05a45d27669f047670e734d4be3f4015257d42a6b1990';          YML_FILE='jre/linux/s390/index.yml';          ;;        s390x)          ESUM='24acc20c2487f2e3a3246c86a10b90b0d7ce6121d923bd7405a1c53e119094ac';          YML_FILE='jre/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(sed -n '/^'${JAVA_VERSION}:'/{n;s/\s*uri:\s//p}'< /tmp/index.yml);     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Tue, 21 Aug 2018 18:31:51 GMT
ENV JAVA_HOME=/opt/ibm/java/jre PATH=/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin IBM_JAVA_OPTIONS=-XX:+UseContainerSupport
# Tue, 21 Aug 2018 19:22:47 GMT
LABEL maintainer=Arthur De Magalhaes <arthurdm@ca.ibm.com> (@arthurdm)
# Tue, 21 Aug 2018 19:23:13 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends unzip     && rm -rf /var/lib/apt/lists/*
# Tue, 21 Aug 2018 19:24:15 GMT
ENV LIBERTY_VERSION=2018.8.0_0
# Tue, 21 Aug 2018 19:25:19 GMT
RUN LIBERTY_URL=$(wget -q -O - https://public.dhe.ibm.com/ibmdl/export/pub/software/websphere/wasdev/downloads/wlp/index.yml  | grep $LIBERTY_VERSION -A 3 | sed -n 's/\s*webProfile7:\s//p' | tr -d '\r')      && echo $LIBERTY_URL     && wget -q $LIBERTY_URL -U UA-IBM-WebSphere-Liberty-Docker -O /tmp/wlp-beta.zip     && unzip -q /tmp/wlp-beta.zip -d /opt/ibm     && rm /tmp/wlp-beta.zip
# Tue, 21 Aug 2018 19:25:20 GMT
ENV PATH=/opt/ibm/wlp/bin:/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 21 Aug 2018 19:25:20 GMT
ENV LOG_DIR=/logs WLP_OUTPUT_DIR=/opt/ibm/wlp/output
# Tue, 21 Aug 2018 19:25:23 GMT
RUN mkdir /logs     && ln -s $WLP_OUTPUT_DIR/defaultServer /output     && ln -s /opt/ibm/wlp/usr/servers/defaultServer /config     && ln -s /opt/ibm /liberty
# Tue, 21 Aug 2018 19:25:29 GMT
RUN /opt/ibm/wlp/bin/server create     && rm -rf $WLP_OUTPUT_DIR/.classCache /output/workarea
# Tue, 21 Aug 2018 19:25:30 GMT
COPY file:3b23d7d17672e2c49786942609f319a90591738e9dfd67f95b1df374561c29ce in /opt/ibm/wlp/usr/servers/defaultServer/ 
# Tue, 21 Aug 2018 19:25:31 GMT
EXPOSE 9080/tcp 9443/tcp
# Tue, 21 Aug 2018 19:25:32 GMT
CMD ["/opt/ibm/wlp/bin/server" "run" "defaultServer"]
```

-	Layers:
	-	`sha256:c49a7289cd353210d298ff1a94ed78172275dc2b56d017327da7ff28811d329c`  
		Last Modified: Tue, 21 Aug 2018 18:08:49 GMT  
		Size: 45.6 MB (45574399 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72b7d965d16a8d691cee58762e03a8c962c909fb1d0d5e9a119c4090682496a7`  
		Last Modified: Tue, 21 Aug 2018 18:08:30 GMT  
		Size: 851.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b0c0736f8ab57b9c4640b9c7d527e33d818bedc6810943802c7e2d9519ef48f`  
		Last Modified: Tue, 21 Aug 2018 18:08:31 GMT  
		Size: 578.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cd1139f0572be9041270b915e4d26c2bacce14cbf6170aed13fdc2576eb3a375`  
		Last Modified: Tue, 21 Aug 2018 18:08:31 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f6e36fdb9e0e77331c1077fc18ac38bbe372020753346fe4bb763e36cb51aec`  
		Last Modified: Tue, 21 Aug 2018 18:08:30 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa74897960e4603b0e9daea1b0255e692fcef3738bb1504032d666584c0cbcb8`  
		Last Modified: Tue, 21 Aug 2018 18:40:15 GMT  
		Size: 2.9 MB (2880557 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9448ddd118d2feab95fd2c4833d7873c11452248f18005a3d06fa19564c586f6`  
		Last Modified: Tue, 21 Aug 2018 18:40:36 GMT  
		Size: 141.0 MB (141049598 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a776609c69410f0dcbbb782131a11ded5edd8b268e80e05072eafe6036cc403`  
		Last Modified: Tue, 21 Aug 2018 19:40:58 GMT  
		Size: 453.0 KB (453036 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:053bb3585b370dec52f4b75f956c6adc5a868377ed39d36e2553a911ffbc1719`  
		Last Modified: Tue, 21 Aug 2018 19:41:27 GMT  
		Size: 98.9 MB (98925588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b1a46637a54c7907e0410b965680fc46c00f34203e70cfe2092c81d50f34d5f`  
		Last Modified: Tue, 21 Aug 2018 19:41:14 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0fb27e29bd76662145abadd0f87ed19f42b5da845d086af17b4e524f142ac58f`  
		Last Modified: Tue, 21 Aug 2018 19:41:15 GMT  
		Size: 1.7 KB (1666 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d90ddab0a0f428822deab46d320d699c6a6c5868240e04ca512b9c3cbab55983`  
		Last Modified: Tue, 21 Aug 2018 19:41:14 GMT  
		Size: 419.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `websphere-liberty:beta` - linux; s390x

```console
$ docker pull websphere-liberty@sha256:91a4cb1ee10eab96f1fd8cc6a2ad97120dfac7b1e4523369fe957930d0d154b0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **271.3 MB (271313046 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d49ff94a11029636826720ba6f11bb1968dfc5e6ae3032004850cdc7f2e33cc5`
-	Default Command: `["\/opt\/ibm\/wlp\/bin\/server","run","defaultServer"]`

```dockerfile
# Fri, 27 Jul 2018 12:59:42 GMT
ADD file:3370b396b7b93b08d1f609f06e321c05d930dc00cb6ae8f0f65d4ed39166245b in / 
# Fri, 27 Jul 2018 12:59:42 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Fri, 27 Jul 2018 12:59:43 GMT
RUN rm -rf /var/lib/apt/lists/*
# Fri, 27 Jul 2018 12:59:44 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Fri, 27 Jul 2018 12:59:45 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Fri, 27 Jul 2018 12:59:45 GMT
CMD ["/bin/bash"]
# Fri, 27 Jul 2018 13:16:38 GMT
MAINTAINER Dinakar Guniguntala <dinakar.g@in.ibm.com> (@dinogun)
# Fri, 27 Jul 2018 13:16:46 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends wget ca-certificates     && rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 12:17:25 GMT
ENV JAVA_VERSION=1.8.0_sr5fp20
# Tue, 14 Aug 2018 12:18:06 GMT
RUN set -eux;     ARCH="$(dpkg --print-architecture)";     case "${ARCH}" in        amd64|x86_64)          ESUM='b2dfbdac0fda3fd8ecea6d9d145da7d6f9fa79fe5cfc13dd3862fc331b8698de';          YML_FILE='jre/linux/x86_64/index.yml';          ;;        i386)          ESUM='b4f525b885ca369b1ab626d552e3ed74f5c6ccc674fcaf5340ecbd9aa046c1eb';          YML_FILE='jre/linux/i386/index.yml';          ;;        ppc64el|ppc64le)          ESUM='bf824a43250b64a85f86e43ee75543de235a4e768f5cc540d4e8b0f4fae2ff18';          YML_FILE='jre/linux/ppc64le/index.yml';          ;;        s390)          ESUM='f216bf12f094e48c3bf05a45d27669f047670e734d4be3f4015257d42a6b1990';          YML_FILE='jre/linux/s390/index.yml';          ;;        s390x)          ESUM='24acc20c2487f2e3a3246c86a10b90b0d7ce6121d923bd7405a1c53e119094ac';          YML_FILE='jre/linux/s390x/index.yml';          ;;        *)          echo "Unsupported arch: ${ARCH}";          exit 1;          ;;     esac;     BASE_URL="https://public.dhe.ibm.com/ibmdl/export/pub/systems/cloud/runtimes/java/meta/";     wget -q -U UA_IBM_JAVA_Docker -O /tmp/index.yml ${BASE_URL}/${YML_FILE};     JAVA_URL=$(sed -n '/^'${JAVA_VERSION}:'/{n;s/\s*uri:\s//p}'< /tmp/index.yml);     wget -q -U UA_IBM_JAVA_Docker -O /tmp/ibm-java.bin ${JAVA_URL};     echo "${ESUM}  /tmp/ibm-java.bin" | sha256sum -c -;     echo "INSTALLER_UI=silent" > /tmp/response.properties;     echo "USER_INSTALL_DIR=/opt/ibm/java" >> /tmp/response.properties;     echo "LICENSE_ACCEPTED=TRUE" >> /tmp/response.properties;     mkdir -p /opt/ibm;     chmod +x /tmp/ibm-java.bin;     /tmp/ibm-java.bin -i silent -f /tmp/response.properties;     rm -f /tmp/response.properties;     rm -f /tmp/index.yml;     rm -f /tmp/ibm-java.bin;
# Tue, 14 Aug 2018 12:18:06 GMT
ENV JAVA_HOME=/opt/ibm/java/jre PATH=/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin IBM_JAVA_OPTIONS=-XX:+UseContainerSupport
# Tue, 14 Aug 2018 12:42:37 GMT
LABEL maintainer=Arthur De Magalhaes <arthurdm@ca.ibm.com> (@arthurdm)
# Tue, 14 Aug 2018 12:42:43 GMT
RUN apt-get update     && apt-get install -y --no-install-recommends unzip     && rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 12:58:10 GMT
ENV LIBERTY_VERSION=2018.8.0_0
# Tue, 14 Aug 2018 12:58:25 GMT
RUN LIBERTY_URL=$(wget -q -O - https://public.dhe.ibm.com/ibmdl/export/pub/software/websphere/wasdev/downloads/wlp/index.yml  | grep $LIBERTY_VERSION -A 3 | sed -n 's/\s*webProfile7:\s//p' | tr -d '\r')      && echo $LIBERTY_URL     && wget -q $LIBERTY_URL -U UA-IBM-WebSphere-Liberty-Docker -O /tmp/wlp-beta.zip     && unzip -q /tmp/wlp-beta.zip -d /opt/ibm     && rm /tmp/wlp-beta.zip
# Tue, 14 Aug 2018 12:58:26 GMT
ENV PATH=/opt/ibm/wlp/bin:/opt/ibm/java/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 12:58:26 GMT
ENV LOG_DIR=/logs WLP_OUTPUT_DIR=/opt/ibm/wlp/output
# Tue, 14 Aug 2018 12:58:26 GMT
RUN mkdir /logs     && ln -s $WLP_OUTPUT_DIR/defaultServer /output     && ln -s /opt/ibm/wlp/usr/servers/defaultServer /config     && ln -s /opt/ibm /liberty
# Tue, 14 Aug 2018 12:58:28 GMT
RUN /opt/ibm/wlp/bin/server create     && rm -rf $WLP_OUTPUT_DIR/.classCache /output/workarea
# Tue, 14 Aug 2018 12:58:28 GMT
COPY file:3b23d7d17672e2c49786942609f319a90591738e9dfd67f95b1df374561c29ce in /opt/ibm/wlp/usr/servers/defaultServer/ 
# Tue, 14 Aug 2018 12:58:28 GMT
EXPOSE 9080/tcp 9443/tcp
# Tue, 14 Aug 2018 12:58:28 GMT
CMD ["/opt/ibm/wlp/bin/server" "run" "defaultServer"]
```

-	Layers:
	-	`sha256:3c676c78c45c4416ba6a9c1bcadd5156f03d0bca9e31f85fc01fca458930cfd5`  
		Last Modified: Fri, 27 Jul 2018 13:01:00 GMT  
		Size: 42.2 MB (42233178 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a735e77c595422e7ecd0ca0e6359ba21a9769b86c1b6231aebfe8feacd95dcc7`  
		Last Modified: Fri, 27 Jul 2018 13:00:52 GMT  
		Size: 844.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ccb796144ba65e756e8cdfdf093072cbe9255706f96d95aad84fa242f1afb41`  
		Last Modified: Fri, 27 Jul 2018 13:00:52 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe28213b67e6813cbc89ec0b7034fb71c4896077f9cbfab52de63f4c0201fc1e`  
		Last Modified: Fri, 27 Jul 2018 13:00:52 GMT  
		Size: 857.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aefcb4b684bed9db0f7491ecade1c76f4268b4216658445ffa9942809ea5299d`  
		Last Modified: Fri, 27 Jul 2018 13:00:52 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c38506499c0863fa74e87358752273bd0f6b80ed1a533dfbbf8106533b5cfa2b`  
		Last Modified: Fri, 27 Jul 2018 13:19:25 GMT  
		Size: 2.8 MB (2764795 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:31b7c9c3592488d9c92e4304ffa5ed6cba0528fe123f114e9070ad9ca2a61d8c`  
		Last Modified: Tue, 14 Aug 2018 12:20:37 GMT  
		Size: 127.0 MB (126957355 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:073576dab032cab1aacb1ad08982bb8fb96c5daf60d793b889ed219a089dca3e`  
		Last Modified: Tue, 14 Aug 2018 12:58:45 GMT  
		Size: 427.5 KB (427473 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5b773b9ab17557106cf4b86b9d07d3c9591c35304bc931e55f6e4d55ecca6c5`  
		Last Modified: Tue, 14 Aug 2018 13:01:29 GMT  
		Size: 98.9 MB (98925614 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f821e8f1970e090935b8b8568866665edd29aa955e6824ed4dbc253a5aee99e1`  
		Last Modified: Tue, 14 Aug 2018 13:01:14 GMT  
		Size: 194.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c1afe59d852e6384ea0bc6263d9e029a3d371639903054eac56170d20cabfc97`  
		Last Modified: Tue, 14 Aug 2018 13:01:15 GMT  
		Size: 1.6 KB (1615 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dfde408b0b109faa117c9abef079134a6bbc80b5288e247e25a13728cce91264`  
		Last Modified: Tue, 14 Aug 2018 13:01:13 GMT  
		Size: 416.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
