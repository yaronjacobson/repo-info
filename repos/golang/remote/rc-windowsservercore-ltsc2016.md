## `golang:rc-windowsservercore-ltsc2016`

```console
$ docker pull golang@sha256:a793bffb078f4ce4f73aee661db70076656dbee2859e8b3c3db812c74fdaad35
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2363; amd64

### `golang:rc-windowsservercore-ltsc2016` - windows version 10.0.14393.2363; amd64

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
