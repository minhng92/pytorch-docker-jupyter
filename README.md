# pytorch-docker-jupyter
Quickly set up Pytorch workspace with Jupyter Lab

# Usage

1. Build docker image

```
$ docker build . -t py35_gpu
```

2. Start workspace with docker-compose file

```
$ docker-compose up -d
```

3. Access the workspace on browser: `localhost:10010`
