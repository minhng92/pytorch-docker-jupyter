# pytorch-docker-jupyter
Quickly set up Pytorch workspace with Jupyter Lab

# Usage

1. Build docker image. Pytorch version is stable version at the time you build the image. The current stable Pytorch version is **0.4.0** (June 24, 2018)

```
$ docker build . -t py35_gpu
```

2. Create empty "workspace" and "home" directories
```
$ mkdir home
$ mkdir workspace
```

3. Start workspace with docker-compose file

```
$ docker-compose up -d
```

4. Access the workspace on browser: `localhost:10010`

5. [Optional] Verify pytorch environment
```
$ python
Python 3.5.5 |Anaconda, Inc.| (default, May 13 2018, 21:12:35)
[GCC 7.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import torch
>>> torch.__version__
'0.4.0'
```
