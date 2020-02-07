Bootstrap: docker
From: nvidia/cuda:10.2-base-ubuntu18.04

%post
    apt-get -qq -y update
    apt-get install --no-install-recommends -y libjpeg-dev zip unzip libpng-dev libopenmpi-dev python3.8 python3.8-dev python3.8-venv python3-pip
    cp /usr/bin/python3.8 /usr/bin/python
    cp /usr/bin/pip3 /usr/bin/pip
    apt-get -qq -y autoremove
    apt-get -qq -y autoclean

%labels
    Author arafathnihar@gmail.com
    Version v0.0.1

%help
    Please follow the steps :
		sudo singularity build fastai.sif fastai.def
		singularity shell --nv fastai.sif
		python -m venv env
		source env/bin/activate
		pip install fastai jupyter notebook jupyter_contrib_nbextensions
