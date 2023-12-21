# Bash Boilerplate Docker

Build and run Bash scripts via docker.

```
 docker build --build-arg VCS_REF=Github BUILD_DATE=21Dec2023 -t docker_bash .

 docker run --rm docker_bash
```