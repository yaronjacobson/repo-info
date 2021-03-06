## `mongo:unstable-windowsservercore-ltsc2016`

```console
$ docker pull mongo@sha256:c82b3c6b01946754aebb0a7729eed8b7739256137303ad0397032b249ea9894e
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2430; amd64

### `mongo:unstable-windowsservercore-ltsc2016` - windows version 10.0.14393.2430; amd64

```console
$ docker pull mongo@sha256:0bc129c635ad2acbe17d3a80dc3392487c7aefd808d1eefa61f264c225536399
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.6 GB (5585501666 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d81e80042e4448eedcd700327c04b9a5287aaa53eaa4c49d5404f0c623668019`
-	Default Command: `["mongod","--bind_ip_all"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Mon, 13 Aug 2018 17:52:23 GMT
RUN Install update 10.0.14393.2430
# Fri, 17 Aug 2018 09:21:39 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Fri, 17 Aug 2018 10:45:07 GMT
ENV MONGO_VERSION=4.1.2
# Fri, 17 Aug 2018 10:45:08 GMT
ENV MONGO_DOWNLOAD_URL=https://downloads.mongodb.org/win32/mongodb-win32-x86_64-2012plus-4.1.2-signed.msi
# Fri, 17 Aug 2018 10:45:09 GMT
ENV MONGO_DOWNLOAD_SHA256=4e327fa11d290fc755b92b9c8d16102f0f3984c6bee3da5630839c2a6448dd6e
# Fri, 17 Aug 2018 10:55:08 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:MONGO_DOWNLOAD_URL); 	(New-Object System.Net.WebClient).DownloadFile($env:MONGO_DOWNLOAD_URL, 'mongo.msi'); 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:MONGO_DOWNLOAD_SHA256); 	if ((Get-FileHash mongo.msi -Algorithm sha256).Hash -ne $env:MONGO_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'mongo.msi', 			'/quiet', 			'/qn', 			'INSTALLLOCATION=C:\mongodb', 			'ADDLOCAL=all' 		); 	$env:PATH = 'C:\mongodb\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  mongo --version'; mongo --version; 	Write-Host '  mongod --version'; mongod --version; 		Write-Host 'Removing ...'; 	Remove-Item C:\mongodb\bin\*.pdb -Force; 	Remove-Item C:\windows\installer\*.msi -Force; 	Remove-Item mongo.msi -Force; 		Write-Host 'Complete.';
# Fri, 17 Aug 2018 10:55:09 GMT
VOLUME [C:\data\db C:\data\configdb]
# Fri, 17 Aug 2018 10:55:11 GMT
EXPOSE 27017/tcp
# Fri, 17 Aug 2018 10:55:12 GMT
CMD ["mongod" "--bind_ip_all"]
```

-	Layers:
	-	`sha256:3889bb8d808bbae6fa5a33e07093e65c31371bcf9e4c38c21be6b9af52ad1548`  
		Last Modified: Tue, 13 Dec 2016 10:53:31 GMT  
		Size: 4.1 GB (4069985900 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:6631c2d2a60cd7ee5b334c2725b03e4d4976abb9a19c8e8dc9b806b3752745a6`  
		Last Modified: Mon, 13 Aug 2018 17:52:23 GMT  
		Size: 1.4 GB (1441905067 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:b95dd3ea2455375b05a0040130b4b3f2bd839787743ff33b9d31af75610902b1`  
		Last Modified: Fri, 17 Aug 2018 11:36:08 GMT  
		Size: 1.2 KB (1199 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10c184870c8982c660789a489268df7ddfdef51c141feb2c7c6f36fc0d5a471a`  
		Last Modified: Fri, 17 Aug 2018 11:43:40 GMT  
		Size: 1.2 KB (1205 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b0969323e0bba850411205804f7ea1efc10883c864d21c3dd304b6f8e711afd`  
		Last Modified: Fri, 17 Aug 2018 11:43:39 GMT  
		Size: 1.2 KB (1191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea8dd95435fa72fc227eefde902aa80469266b36e5fa3ab0366a79b7150ab3da`  
		Last Modified: Fri, 17 Aug 2018 11:43:37 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0deca888dc735ae61621661b24b4d727edd31c6d9d3bf48197c991f48eb7571`  
		Last Modified: Fri, 17 Aug 2018 11:43:54 GMT  
		Size: 73.6 MB (73602319 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:af9b4a3ff8572e6d6e870a49113224d0575268c200f1c1973a78ab026a69a65f`  
		Last Modified: Fri, 17 Aug 2018 11:43:37 GMT  
		Size: 1.2 KB (1194 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:abede38d2118a1d0e7740ebf76ea9813165247bea4520cd1f351b0f6a84503ad`  
		Last Modified: Fri, 17 Aug 2018 11:43:37 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a21d8911bbee32f9bf896ba3b11dab4aac531adbef2e604a8595ca61c157dfa7`  
		Last Modified: Fri, 17 Aug 2018 11:43:37 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
