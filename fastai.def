Bootstrap: docker
From: nvidia/cuda

%post
    apt-get update -y
    apt-get upgrade -y
    apt-get install build-essential cmake git curl vim ca-certificates libjpeg-dev zip unzip libpng-dev libopenmpi-dev python3.8 python3.8-dev python3.8-venv python3-pip -y
    apt-get dist-upgrade -y
    cp /usr/bin/python3.8 /usr/bin/python
    cp /usr/bin/pip3 /usr/bin/pip

%help
    Please follow the steps :
		sudo singularity build fastai.sif fastai.def
		singularity shell --nv fastai.sif
		python -m venv env
		source env/bin/activate
		pip install fastai jupyter notebook jupyter_contrib_nbextensions