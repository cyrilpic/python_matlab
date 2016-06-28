FROM python:3.4
MAINTAINER Cyril Picard <cyril.picard@epfl.ch>
RUN apt-get update && apt-get install -y wget unzip && rm -rf /var/lib/apt/lists/*
RUN cd /root \
  && mkdir mcr \
  && cd mcr \
  && wget -qO- -O tmp.zip \
    http://www.mathworks.com/supportfiles/downloads/R2016a/deployment_files/R2016a/installers/glnxa64/MCR_R2016a_glnxa64_installer.zip \
  && unzip tmp.zip \
  && rm tmp.zip \
  && ./install -mode silent -agreeToLicense yes \
  && cd / \
  && rm -Rf /root/mcr
ENV LD_LIBRARY_PATH /usr/local/MATLAB/MATLAB_Runtime/v901/runtime/glnxa64:/usr/local/MATLAB/MATLAB_Runtime/v901/bin/glnxa64:/usr/local/MATLAB/MATLAB_Runtime/v901/sys/os/glnxa64:$LD_LIBRARY_PATH
