# pytorch-docker-jupyter

Quickly set up Pytorch and Jupyter Lab with Docker

# Usage

## Pytorch GPU version

```
$ git clone https://github.com/minhng92/pytorch-docker-jupyter
$ cd pytorch-docker-jupyter/pytorch_gpu

# modify PYTORCH_VERSION and PYTORCH_CUDA_VERSION environment in Dockerfile if needed!!

$ docker-compose build
$ docker-compose up -d
```

Enjoy your workspace @ `localhost:10010`

## Pytorch CPU version

```
$ git clone https://github.com/minhng92/pytorch-docker-jupyter
$ cd pytorch-docker-jupyter/pytorch_cpu

# modify PYTORCH_VERSION environment in Dockerfile if needed!!

$ docker-compose build
$ docker-compose up -d
```

Enjoy your workspace @ `localhost:10011`

