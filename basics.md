# The very first container

```bash
docker run hello-world
```

Observe the exited containers:

```bash
docker ps -a
```

And remove them:

```bash
docker rm <container-id>
```

The container may be removed implicitly by adding `--rm` to the command line:

```bash
docker run --rm hello-world
```

# Let's go interactive

```bash
docker run --rm -it ubuntu bash
```

Now you may run some commands inside of the container, like:

```bash
apt update
apt upgrade
apt install nano
nano hello-world.txt
ls
```

To terminate it, call `exit`

# Work with images

You may pull images from any registry. Default is https://hub.docker.com/

```bash
docker pull postgres
```

The local images may be observed:

```bash
docker images
```

And removed:

```bash
docker rmi postgres
```

# Volumes
## Map host directory into container

```bash
mkdir c:\volume-test
docker run --rm -it --volume c:\volume-test:/opt ubuntu bash
```

In the container, create some files:

```bash
cd /opt
touch test1
touch test2
```

- Observe `c:\volume-test` for the files being created.
- Stop/restart the container and check the files are back in `/opt`

## Named volume

```bash
docker run --rm -it --volume volume-demo:/opt ubuntu bash
```

Again, create some files in the container:

```bash
cd /opt
touch test1
touch test2
```

Stop/restart the container and check the files are back in `/opt`

Check the named volumes on your host

```bash
docker volume list
```

And clean up

```bash
docker volume rm volume-demo
```
