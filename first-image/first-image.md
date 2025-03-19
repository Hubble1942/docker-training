# Build the image

```bash
docker build --tag my-first-image .
```

Observe the image being created

```bash
docker images
```

# Run it

```bash
docker run --rm -it my-first-image bash
```

Check `nano` is installed

```bash
nano hello-world.txt
```
