FROM ubuntu:16.04
LABEL com.nvidia.volumes.needed="nvidia_driver"
RUN apt-get update && apt-get install -y --no-install-recommends \
         build-essential \
         git \
         curl \
         ca-certificates \
         libjpeg-dev \
         libpng-dev \
         libglu1 \
         ssh \
         nano \
         htop \
         unzip \
         wget

ENV PYTHON_VERSION=3.5
# To decide which pytorch and cuda version, please checkout this link:
# https://anaconda.org/pytorch/repo
ENV PYTORCH_VERSION=1.0.0
ENV PYTORCH_CUDA_VERSION=cuda90

RUN curl -o ~/miniconda.sh -O  https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh  && \
     chmod +x ~/miniconda.sh && \
     ~/miniconda.sh -b -p /opt/conda && \
     rm ~/miniconda.sh && \
     /opt/conda/bin/conda install conda-build && \
     /opt/conda/bin/conda create -y --name pytorch-py$PYTHON_VERSION python=$PYTHON_VERSION numpy pyyaml scipy ipython mkl && \
     /opt/conda/bin/conda clean -ya
ENV PATH opt/conda/bin:/opt/conda/envs/pytorch-py$PYTHON_VERSION/bin:$PATH
RUN conda install --name pytorch-py$PYTHON_VERSION pytorch=$PYTORCH_VERSION torchvision $PYTORCH_CUDA_VERSION magma-$PYTORCH_CUDA_VERSION -c pytorch

ENV NVIDIA_VISIBLE_DEVICES all
ENV NVIDIA_DRIVER_CAPABILITIES compute,utility
ENV LD_LIBRARY_PATH /usr/local/nvidia/lib:/usr/local/nvidia/lib64

RUN conda install --name pytorch-py$PYTHON_VERSION ffmpeg matplotlib opencv
RUN conda install --name pytorch-py$PYTHON_VERSION lxml -c anaconda

RUN /opt/conda/envs/pytorch-py$PYTHON_VERSION/bin/pip install easydict ffmpy imutils requests flask onnx seaborn pandas

RUN conda install --name pytorch-py$PYTHON_VERSION --yes ipython notebook jupyter jupyterlab && conda clean -ya

EXPOSE 8888

WORKDIR /workspace
RUN chmod -R a+w /workspace

ENV JUPYTER_COMMAND "jupyter notebook --ip=0.0.0.0 --port=8888 --no-browser --allow-root --NotebookApp.token="
CMD $JUPYTER_COMMAND
