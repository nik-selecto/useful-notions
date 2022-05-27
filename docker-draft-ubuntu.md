[HOME](./README.md)


#### ubuntu container for any drafts with spacevim, tmux, rust
* create:
```
docker run -d -t --name ubu ubuntu
```
* enter inside:
```
docker exec -it ubu env TERM=xterm-256color script -q -c "/bin/bash" /dev/null
```
* install _spacevim_, _git_, _tmux_, _rust_ (should click '1' during installation)
> only for first time
```
apt update \
      && apt upgrade -y \
      && apt install curl -y \
      && apt install git -y \
      && apt install vim -y \
      && apt install build-essential -y \
      && apt install tmux -y \
      && cd \
      && git clone https://github.com/gpakosz/.tmux.git \
      && ln -s -f .tmux/.tmux.conf \
      && cp .tmux/.tmux.conf.local . \
      && curl -sLf https://spacevim.org/install.sh | bash \
      && curl --proto '=https' \
        --tlsv1.2 -sSf https://sh.rustup.rs | sh \
      && source $HOME/.cargo/env
```
