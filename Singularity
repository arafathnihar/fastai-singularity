Bootstrap: docker
From: nvidia/cuda:10.2-base-ubuntu18.04

%post
    apt-get update -y
    apt-get upgrade -y
    apt-get dist-upgrade -y
    
    apt-get install -y --no-install-recommends git\
    gcc\
    python3\
    python3-dev\
    python3-setuptools\
    python3-wheel\
    python3-pip

    pip3 install torch torchvision
    pip3 install fastai jupyter notebook jupyter_contrib_nbextensions

    #clean up
    apt --purge autoremove -y
    apt clean
    rm -rf /var/lib/apt/lists/*

%runscript
    echo "\n"
    echo "Open a terminal in your machine and type the following command to port forward"
    echo "ssh -N -L 9999:$(hostname -i):9999 $(id -un)@rider.case.edu"
    echo "\n"

    FOLDER="fastbook"
    URL="https://github.com/fastai/fastbook.git"
    if [ ! -d "$FOLDER" ] ; then
        git clone $URL $FOLDER
    fi
    cd fastbook
    jupyter notebook --ip=0.0.0.0 --port=8888 --allow-root --no-browser

%help
    Please follow the steps :
        sudo singularity build fastai.sif fastai.def
        singularity run --nv fastai.sif
