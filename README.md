# Synaptic Flow


## Getting Started
First clone this repo, then install all dependencies
```
pip install -r requirements.txt
```
The code was tested with Python 3.6.0.

## Code Base
Below is a description of the major sections of the code base. Run `python main.py --help` for a complete description of flags and hyperparameters.

### Datasets
This code base supports the following datasets: MNIST, CIFAR-10, CIFAR-100, Tiny ImageNet, ImageNet. 

All datasets except Tiny ImagNet and ImageNet will download automatically.  For Tiny ImageNet, download the data directly from [https://tiny-imagenet.herokuapp.com](https://tiny-imagenet.herokuapp.com), move the unzipped folder ``tiny-imagnet-200`` into the ```Data``` folder, run the script `python Utils/tiny-imagenet-setup.py` from the home folder. For ImageNet setup locally in the ```Data``` folder.

### Models

There are four model classes each defining a variety of model architectures:
 - Default models support basic dense and convolutional model.
 - Lottery ticket models support VGG/ResNet architectures based on [OpenLTH](https://github.com/facebookresearch/open_lth).
 - Tiny ImageNet models support VGG/ResNet architectures based on this Github [repository](https://github.com/weiaicunzai/pytorch-cifar100).
 - ImageNet models supports VGG/ResNet architectures from [torchvision](https://pytorch.org/docs/stable/torchvision/models.html).

### Layers

Custom dense, convolutional, batchnorm, and residual layers implementing masked parameters can be found in the `Layers` folder.

### Pruners

All pruning algorithms are implemented in the `Pruners` folder.

### Experiments

Below is a list and description of the experiment files found in the `Experiment` folder:
 - `example.py`: used to test code.
 - `singleshot.py`: used to make figure 1, 2, and 6.
 - `unit-conservation.py`: used to make figure 3.
 - `layer-conservation.py`: used to make figure 4.
 - `lottery.py`: used to make figure 5a.
 - `lottery-layer-conservation.py`: used to make figure 5b.
 - `synaptic-flow-ratio.py`: used to make figure 7.


### Results

All data used to generate the figures in our paper can be found in the `Results/data` folder.  Run the notebook `figures.ipynb` to generate the figures.

## Citation
If you use this code for your research, please cite our paper,
["Pruning neural networks without any data by iteratively conserving synaptic flow"](https://arxiv.org/abs/2006.05467).
