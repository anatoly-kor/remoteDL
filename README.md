# Prepare your remote machine to DeepLearning(PyTorch)

## Checking

Check the availability GPU in the system.

`lspci | grep -i nvidia`

## Update system and install required packets

`sudo apt-get update`

`sudo apt-get dist-upgrade`

`sudo apt install -y build-essential git libgfortran3`

## Install CUDA

https://developer.nvidia.com/cuda-toolkit-archive

### Checking installation

`nvidia-smi`

## Install Conda

[Anaconda](https://www.anaconda.com/distribution/)

[Miniconda](https://docs.conda.io/en/latest/miniconda.html)

### Checking installation

`conda -V`

If `conda: command not found` then add env var to ~/.bashrc `export PATH="$HOME/anaconda3/bin:$PATH"`.

## Install PyTorch

`conda install pytorch torchvision cudatoolkit=10.0 -c pytorch`

## Install Jupyter

`conda install jupyter` or `conda install jupyterlab`

## If need prepare server to external connection

## Configure Jupyter

`echo c.NotebookApp.ip = '*' > ~/.jupyter/jupyter_notebook_config.py`

`echo c.NotebookApp.open_browser = False >> ~/.jupyter/jupyter_notebook_config.py`

`echo c.NotebookApp.port = 8888 >> ~/.jupyter/jupyter_notebook_config.py`

`jupyter notebook password`

## Run Jupyter

`jupyter-lab --ip=0.0.0.0 --port=8888 --no-browser &`

Enter in browser on client side `<ip>:8888`.

### OR

`jupyter-lab --port=9000 --no-browser &`

`ssh -N -f -L 8888:localhost:9000 name@server`
