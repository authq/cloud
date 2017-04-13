### Docker Hub Registry Mirror
Unfortounatly Docker Hub is not available in iran.
You can use our hight-speed Docker Hub mirror for your docker daemon.

#### Usage
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

You can test functionality by pulling hello-world image

```bash
$ docker pull hello-world

Using default tag: latest
latest: Pulling from library/hello-world
78445dd45222: Pull complete
Digest: sha256:c5515758d4c5e1e838e9cd307f6c6a0d620b5e07e6f927b07d05f6d12a1ac8d7
Status: Downloaded newer image for hello-world:latest
```