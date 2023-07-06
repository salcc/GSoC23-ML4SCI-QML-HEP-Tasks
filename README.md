# GSoC 2023 ML4SCI QML-HEP Tasks

This repository contains my test solutions for the tasks to apply for the [Machine Learning for Science (ML4SCI)](https://ml4sci.org/) [Quantum Machine Learning for High Energy Physics (QML-HEP) projects](https://ml4sci.org/gsoc/projects/2023/project_QMLHEP.html)
in [Google Summer of Code](https://summerofcode.withgoogle.com/) 2023. The task statemets can be found in [this link](https://docs.google.com/document/d/1dqBGbH44Eu3W432oRxpOCfI5Dy2pgh2E21JcHeD0fng/edit?usp=sharing).

In particular, I completed the following tasks:

- [Task I: Quantum Computing Part](Task_I.ipynb)
- [Task II: Classical Graph Neural Network (GNN)](Task_II.ipynb)
- [Task III: Open Task](Task_III.md)
<!-- - [Task IV: Quantum Generative Adversarial Network (QGAN)](Task_IV.ipynb) -->
<!-- - [Task V: Quantum Graph Neural Network (QGNN)](Task_V.ipynb) -->
- [Task VI: Quantum Representation Learning](Task_VI.ipynb)
- [Task VII: Equivariant Quantum Neural Networks](Task_VII.ipynb)
- [Task VIII: Vision Transformer / Quantum Vision Transformer](Task_VIII.ipynb)

Due to my other commitments during this time of the year and to the constrained time frame for completing all the tasks, I was unable to finish tasks IV, and V.

## Installation instructions

To execute the notebooks I used a computer with an Intel Core i7-6700K CPU, 16 GB of RAM, and an NVIDIA GeForce GTX 1080 GPU
running Ubuntu 22.04 LTS.

Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) if you do not have it:

```
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -o Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh 
```

Create a Conda environment called `qml-gsoc` and install the required packages.
```
conda create --name qml-gsoc python=3.9
conda activate qml-gsoc
conda install -c conda-forge cudatoolkit=11.2.2 cudnn=8.1.0
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/
mkdir -p $CONDA_PREFIX/etc/conda/activate.d
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/' > $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
pip install --upgrade pip
pip install jupyterlab ipywidgets tensorflow==2.11.0 tensorflow-quantum pennylane ray hpbandster scikit-learn
conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
```

Considerations:
- The version of Python is set to 3.9 because that is the latest version of Python supported by TensorFlow Quantum.
- The version of TensorFlow is fixed to 2.11.0 because that is the version supported by the last version of TensorFlow Quantum.
- CUDA Toolkit 11.2.2 and cuDNN 8.1.0 are installed because those are the latest versions supported by Tensorflow 2.11.0. However, note that PyTorch will use CUDA 11.8.
- Cirq, NumPy, and other packages used in the notebooks are already installed as dependencies automatically.

To execute the notebooks open Jupyter Lab:

```
jupyter lab
```
