## `golang:rc-nanoserver`

```console
$ docker pull golang@sha256:f86e9ae3a59efe9ac167a3d3328fd81d55f9429d67e997b8ba691a4f76eb651e
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2363; amd64

### `golang:rc-nanoserver` - windows version 10.0.14393.2363; amd64

```console
$ docker pull golang@sha256:79da45fb0cec996d298f129b10b3a1f2438ceacdfc39e54de43171f76b5c9f9c
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **605.3 MB (605268636 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8593d100229b78e89e54ed3636cc1bfc9c0d3ddbe80df4acdae56408133b00b5`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:47:17 GMT
RUN Apply image 10.0.14393.0
# Tue, 10 Jul 2018 21:16:01 GMT
RUN Install update 10.0.14393.2363
# Wed, 11 Jul 2018 09:44:58 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Fri, 13 Jul 2018 10:15:39 GMT
ENV GOPATH=C:\gopath
# Fri, 13 Jul 2018 10:16:28 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Tue, 14 Aug 2018 16:57:41 GMT
ENV GOLANG_VERSION=1.11rc1
# Tue, 14 Aug 2018 17:03:48 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = 'bcd482bdae421c580897ce0bb350f56679ebe676817ead572ee3a5942611bcc9'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Tue, 14 Aug 2018 17:03:49 GMT
WORKDIR C:\gopath
```

-	Layers:
	-	`sha256:bce2fbc256ea437a87dadac2f69aabd25bed4f56255549090056c1131fad0277`  
		Last Modified: Tue, 13 Dec 2016 10:47:17 GMT  
		Size: 252.7 MB (252691002 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:d4a9b16fd154d065649f42ee7ac674690d46dbe6ad2398a58166c37c85ca64ed`  
		Last Modified: Tue, 10 Jul 2018 21:16:01 GMT  
		Size: 166.8 MB (166830055 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:c00083f7064e157d9aa12ed2cde81fc21da017ab3b1d2d05cf45ee282d465ddd`  
		Last Modified: Wed, 11 Jul 2018 09:56:07 GMT  
		Size: 952.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef6f6a14ad0e696cedcbe505e01a2bf1818e607a6ec5a52345bea2ceea9958a5`  
		Last Modified: Fri, 13 Jul 2018 11:09:33 GMT  
		Size: 954.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f096412574b846b311a8fc2b4f4e10b0d97a38c502b8db601d0d5f3b31ed8e0`  
		Last Modified: Fri, 13 Jul 2018 11:09:34 GMT  
		Size: 929.3 KB (929303 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d51e87d412f6019b0ee12f57c01647ae4a329c5082d7d74c9d1c097e1521a9d`  
		Last Modified: Tue, 14 Aug 2018 17:10:12 GMT  
		Size: 951.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f778498b4280feb51f9029e6b08e310a657d3e5196f20cc10017ceff162fe54`  
		Last Modified: Tue, 14 Aug 2018 17:11:38 GMT  
		Size: 184.8 MB (184814274 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28e2683c28fa7c4a33fdcd450a806c8f3d7c374c2bcaaf7bf20658c8a7b82a74`  
		Last Modified: Tue, 14 Aug 2018 17:10:12 GMT  
		Size: 1.1 KB (1145 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
