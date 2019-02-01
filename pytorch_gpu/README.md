# pytorch-docker-jupyter

Quickly set up Pytorch and Jupyter Lab with Docker

# Usage

```
$ git clone https://github.com/minhng92/pytorch-docker-jupyter
$ cd pytorch-docker-jupyter/pytorch_gpu

# modify PYTORCH_VERSION and PYTORCH_CUDA_VERSION environment in Dockerfile if needed!!

$ docker-compose build
$ docker-compose up -d
```

Enjoy your workspace @ `localhost:10010`

---

# Verify Pytorch environment

```
$ python
Python 3.5.5 |Anaconda, Inc.| (default, May 13 2018, 21:12:35)
[GCC 7.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import torch
>>> torch.__version__
'0.4.0'
```
