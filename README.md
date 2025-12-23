# docker-pyenv-python-builder
A docker container for building python for pyenv

## Prerequisite
- docker
- pyenv

## Usage
1. ```bash
   git clone https://github.com/chungchungdev/docker-pyenv-python-builder.git
   ```
3. ```bash
   cd docker-pyenv-python-builder
   ```
5. ```bash
   docker build --build-arg RELEASE=$(lsb_release -cs) -t python-builder .
   ```
7. ```bash
   docker run --name my-python-builder -it python-builder:latest /bin/bash
   ```
9. In the container terminal,
   ```bash
   env PYTHON_CONFIGURE_OPTS="--disable-shared" pyenv install <python_version>
   ```
11. In the host terminal,
    ```bash
    docker cp my-python-builder:/root/.pyenv/versions/. ~/.pyenv/versions/
    ```
