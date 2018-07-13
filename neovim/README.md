# Neovim Docker

Runs neovim with python2, python3, and node support

### 1. Pull the image from docker hub

`docker pull deltaskelta/neovim`

### 2. Run the container and mount your plugin and init.vim directories `.local` and `.config`

```bash
NVIM_PYTHON_LOG_FILE=./.config/logs/python.log \
    NVIM_PYTHON_LOG_LEVEL=DEBUG \
    docker run \
    -it \
    -v [data dir containing files to edit]:/data \
    -v `pwd`/.local:/root/.local \
    -v `pwd`/.config:/root/.config \
    deltaskelta/neovim \
    -u /root/.config/init.vim
```
