# ☁️ Amirkabir University Cloud Services

> This is an *UNOFFICIAL* proof-of-concept project which aims to provide modern cloud tools and services such as image registry and mirrors.

**WARNING:: ALPHA PROJECT! Should NOT BE RELIED FOR PRODUCTION**

## Public Services

### Docker Hub
Unfortounatly docker-hub is not available in iran. You can use our hight-speed docker-hub cache mirror service for your docker hosts.

#### Setup
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

### NPM Registry
Enjoy high speed npm registry cache mirror.

#### Setup
For setting up in your project create a file `.npmrc` and add following line:

```ini
registry=https://nexus.cloud.aut.ac.ir/repository/npm/
```

## Ideas & More services
Feel free opening PR and share your ideas.
Please keep note that (at least for now) we have not any plans to provide public computing and hosting services like openstack and containers. 

## Contribution
/TBA
