# fastai-singularity
- singularity container for fastai-v3

[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/4032)

For container interaction

- Choose your preference to pull the container from Singularity Hub (once)
```sh
singularity pull shub://arafathnihar/fastai-singularity
```

- Then interact with it
```sh
singularity shell --nv fastai-singularity.sif
```
- Creating a virtual environment
```sh
python -m venv env
source env/bin/activate
```
- Installing fastai packages
```sh
pip install fastai jupyter notebook jupyter_contrib_nbextensions
```
- Cloning fastai-v3 course
```sh
git clone https://github.com/fastai/course-v3.git
```
- start jupyter notebook
```sh
cd course-v3/nbs/dl1/
jupyter notebook
```
