Bootstrap: docker
From: nvidia/cuda:10.2-base-ubuntu18.04

%post
    apt-get update -y
    apt-get upgrade -y
    apt-get dist-upgrade -y
    apt-get install -y --no-install-recommends git gcc python3 python3-dev python3-setuptools python3-wheel python3-pip 
    pip3 install fastai jupyter notebook jupyter_contrib_nbextensions

    #clean up
    apt --purge autoremove -y
    apt clean
    rm -rf /var/lib/apt/lists/*

%runscript
    echo "Open a terminal in your machine and type the following command to port forward"
    echo "ssh -N -L 9999:$(hostname -i):9999 $(id -un)@rider.case.edu"

    FOLDER="course-v3"
    URL="https://github.com/fastai/course-v3.git"
    if [ ! -d "$FOLDER" ] ; then
        git clone $URL $FOLDER
    fi
    cd course-v3/nbs
    jupyter notebook --no-browser --ip=$(hostname -i) --port=9999

%help
    Please follow the steps :
        sudo singularity build fastai.sif fastai.def
        singularity run --nv fastai.sif
