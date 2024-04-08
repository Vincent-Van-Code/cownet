FROM quay.io/jupyter/pytorch-notebook:cuda12-pytorch-2.2.2
USER root
COPY cuda-keyring_1.1-1_all.deb .
RUN dpkg -i cuda-keyring_1.1-1_all.deb

RUN apt-get update && apt-get install -y cuda-toolkit-12-4
ENV LC_ALL="en_US.UTF-8"
ENV LIBRARY_PATH="/usr/local/cuda/lib64/stubs"
ENV LD_LIBRARY_PATH="/usr/lib64-nvidia"
RUN ldconfig /usr/lib64-nvidia

RUN pip install mamba-ssm
RUN pip install -U http://kermit.bounceme.net:8900/triton-3.0.0-cp311-cp311-linux_x86_64.whl

