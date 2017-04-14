# Mirros
Mirros are powered by special cache-miror microservices so are always updated with upstream.
If requested resource is not available in cache it may take a little more time for first fetch operation.
(TTL for checking newer packages is 5 Min)

For supporting other useful mirrors open an [issue](https://github.com/authq/cloud/issues/new) with following information:
- Usecase and enough reasons
- Suggested local upstream mirrors 

## NPM Registry Mirror
This service is specially useful for using in CI/CD environments. 

### Usage
Add following line to `.npmrc`:

```ini
registry=http://npm.cloud.aut.ac.ir
```

## APT Mirror
We directly mirror [fastmirror.ir](fastmirror.ir) which is official ubuntu mirror (Thanks to jadi :D).
It currently supports following distributions:

- Debian:
	- Jessie
	- Sid
	- Wheezy

- Ubuntu:
	- Precise
	- Trusty
	- Vivid
	- Wily
	- Xential
	- Yakkety
	- Zesty

### Usage
For ubuntu Use this mirror in `sources.list`
```
http://apt.cloud.aut.ac.ir/ubuntu
```

For debian:
```
http://apt.cloud.aut.ac.ir/debian
```
	
## Docker Hub Registry Mirror
Unfortounatly Docker Hub is not available in iran.
You can use our hight-speed Docker Hub mirror for your docker daemon.

### Usage
Edit `/etc/docker/daemon.json` file (or create new one if not exists)

```js
{
  "registry-mirrors": [
      "http://mirror.docker.cloud.aut.ac.ir"
  ],
}
```

Then restart docker daemon

```bash
systemctl restart docker
```

### Test functionality
You can test functionality by pulling hello-world image

```bash
$ docker pull hello-world

Using default tag: latest
latest: Pulling from library/hello-world
78445dd45222: Pull complete
Digest: sha256:c5515758d4c5e1e838e9cd307f6c6a0d620b5e07e6f927b07d05f6d12a1ac8d7
Status: Downloaded newer image for hello-world:latest
```