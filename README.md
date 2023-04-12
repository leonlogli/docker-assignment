# Docker first assignment

Dockerize BOTH apps - the Python and the Node app.

1. Create appropriate images for both apps (two separate images!).
   HINT: Have a brief look at the app code to configure your images correctly!

```bash
# build python image
docker build -t python-app ./python-app/.
```

2. Launch a container for each created image, making sure,
   that the app inside the container works correctly and is usable.

```bash
# run python-app container with `it` flag because the app need pseudo terminal for input/output
docker run -it python-app
```

3. Re-create both containers and assign names to both containers.
   Use these names to stop and restart both containers.

```bash
# run python-app container
docker run -it --name python-app python-app
# Stop containers
docker stop python-app
```

4. Clean up (remove) all stopped (and running) containers,
   clean up all created images.

```bash
# First stop containers
docker stop python-app
# Clean up all stopped containers
docker container prune
# clean up all created images
docker image prune
```

5. Re-build the images - this time with names and tags assigned to them.

```bash
docker build -t python-app:latest ./python-app/.
```

6. Run new containers based on the re-built images, ensuring that the containers
   are removed automatically when stopped.

```bash
# --rm flag remove the container on stop
docker run -it --rm --name python-app python-app
```
