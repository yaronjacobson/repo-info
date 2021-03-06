## `python:3-windowsservercore-ltsc2016`

```console
$ docker pull python@sha256:f6746946582a4106c95bea097ac4014c72bde5c67771bdb1a1bbd833d93f79af
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2363; amd64

### `python:3-windowsservercore-ltsc2016` - windows version 10.0.14393.2363; amd64

```console
$ docker pull python@sha256:6be8faf11f92e4bdeba0b8f36bd9b6dab09a3574c41981fb74eda2707c198442
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.6 GB (5552054177 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b999f1d939ede7dd7fae581c6aa082937e6a90e21bb90ddb3fcb8d3cbb7ab230`
-	Default Command: `["python"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Tue, 10 Jul 2018 21:16:33 GMT
RUN Install update 10.0.14393.2363
# Wed, 11 Jul 2018 09:36:34 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Tue, 17 Jul 2018 09:51:08 GMT
ENV PYTHON_VERSION=3.7.0
# Tue, 17 Jul 2018 09:51:09 GMT
ENV PYTHON_RELEASE=3.7.0
# Tue, 17 Jul 2018 09:53:55 GMT
RUN $url = ('https://www.python.org/ftp/python/{0}/python-{1}-amd64.exe' -f $env:PYTHON_RELEASE, $env:PYTHON_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri $url -OutFile 'python.exe'; 		Write-Host 'Installing ...'; 	Start-Process python.exe -Wait 		-ArgumentList @( 			'/quiet', 			'InstallAllUsers=1', 			'TargetDir=C:\Python', 			'PrependPath=1', 			'Shortcuts=0', 			'Include_doc=0', 			'Include_pip=0', 			'Include_test=0' 		); 		$env:PATH = [Environment]::GetEnvironmentVariable('PATH', [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  python --version'; python --version; 		Write-Host 'Removing ...'; 	Remove-Item python.exe -Force; 		Write-Host 'Complete.';
# Thu, 26 Jul 2018 09:25:33 GMT
ENV PYTHON_PIP_VERSION=18.0
# Thu, 26 Jul 2018 09:27:51 GMT
RUN Write-Host ('Installing pip=={0} ...' -f $env:PYTHON_PIP_VERSION); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri 'https://bootstrap.pypa.io/get-pip.py' -OutFile 'get-pip.py'; 	python get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		('pip=={0}' -f $env:PYTHON_PIP_VERSION) 	; 	Remove-Item get-pip.py -Force; 		Write-Host 'Verifying pip install ...'; 	pip --version; 		Write-Host 'Complete.';
# Thu, 26 Jul 2018 09:27:52 GMT
CMD ["python"]
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
	-	`sha256:394b335e0ef92a6dd70bb2dc5c22b5a2a33777cfa19b10c1aceb8c2de849d479`  
		Last Modified: Tue, 17 Jul 2018 10:19:02 GMT  
		Size: 1.2 KB (1206 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0854e29c185f02ff30e576a708b26472ecf20e1ba23738446b83dcea4c106286`  
		Last Modified: Tue, 17 Jul 2018 10:18:58 GMT  
		Size: 1.2 KB (1191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c81f5e4d48f604e9874b536ed428c28a349d0e0e5039f476d3251b935de0a2d`  
		Last Modified: Tue, 17 Jul 2018 10:19:22 GMT  
		Size: 53.0 MB (52971403 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:08d6a499e7464cec311ff7ce624c79d44d5cd6e415abcb706202d6ca16b07cf4`  
		Last Modified: Thu, 26 Jul 2018 09:42:20 GMT  
		Size: 1.2 KB (1202 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6a89448f17de05b3becc5f7c3fd6c1baa3e403e05debedc51cae58daf8b13b`  
		Last Modified: Thu, 26 Jul 2018 09:42:30 GMT  
		Size: 9.8 MB (9792593 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b52476c33aea4f66401fc9880cbcdb947a09281694a0bb58e935bc5d0eeadf85`  
		Last Modified: Thu, 26 Jul 2018 09:42:20 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
