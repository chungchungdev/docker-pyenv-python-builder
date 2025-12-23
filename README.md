# docker-pyenv-python-builder
A docker container for building python for pyenv

## Prerequisite
- docker
- pyenv

## Usage
1. `git clone https://github.com/chungchungdev/docker-pyenv-python-builder.git`
2. `cd docker-pyenv-python-builder`
3. `docker build --build-arg RELEASE=$(lsb_release -cs) -t python-builder .`
4. `docker run --name my-python-builder -it python-builder:latest /bin/bash`
5. In the container terminal, `env PYTHON_CONFIGURE_OPTS="--disable-shared" pyenv install <python_version>`
6. In the host terminal, `docker cp my-python-builder:/root/.pyenv/versions/. ~/.pyenv/versions/`
