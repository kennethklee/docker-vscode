# docker-vscode

Run Visual Studio Code on a docker container over X11.

## Running

Ensure you allow X11 connections: `xhost +local:docker`.

```
docker run -d --name vscode \
              -v /tmp/.X11-unix/:/tmp/.X11-unix/ \
              -v /dev/shm:/dev/shm \
              -v ${HOME}/.vscode:/root/.config/Code \
              -e DISPLAY \
              kennethkl/vscode
```

Don't forget to disallow X11 connections after: `xhost -local:docker`.