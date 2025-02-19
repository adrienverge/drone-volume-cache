# drone-volume-cache
This is a pure Bash [Drone](https://github.com/drone/drone) 0.5 plugin to cache files and/or folders to a locally mounted volume.

For more information on how to use the plugin, please take a look at [the docs](https://github.com/Drillster/drone-volume-cache/blob/master/DOCS.md).

## Docker
Build the docker image by running:

```bash
docker build --rm=true -t drillster/drone-volume-cache .
```

## Usage
Execute from the working directory:

```bash
docker run --rm \
  -e PLUGIN_REBUILD=true \
  -e PLUGIN_MOUNT="./node_modules" \
  -e DRONE_REPO_OWNER="foo" \
  -e DRONE_REPO_NAME="bar" \
  -v $(pwd):$(pwd) \
  -v /tmp/cache:/cache \
  -w $(pwd) \
  drillster/drone-volume-cache
```
