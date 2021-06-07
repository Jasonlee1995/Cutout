# Cutout Implementation with Pytorch
- Unofficial implementation of the paper *Improved Regularization of Convolutional Neural Networks with Cutout*


## 0. Develop Environment
```
Docker Image
- pytorch/pytorch:1.8.1-cuda11.1-cudnn8-devel
```


## 1. Implementation Details
- augmentation.py : Cutout implementation
- model.py : Wide ResNet model
- train.py : train Wide ResNet
- utils.py : count correct prediction
- Cutout - Wide ResNet 28 10 - Cifar 10 : install library, download dataset, preprocessing, train
  * Cutout - Wide ResNet 28 10 - Cifar 10 (0.5 prob, 5 Average).ipynb : average 5 runs, 0.5 probability to apply Cutout
  * Cutout - Wide ResNet 28 10 - Cifar 10 (0.5 prob, Single).ipynb : single run with plots, 0.5 probability to apply Cutout
  * Cutout - Wide ResNet 28 10 - Cifar 10 (5 Average).ipynb : average 5 runs, always apply Cutout
  * Cutout - Wide ResNet 28 10 - Cifar 10 (Single).ipynb : single run with plots, always apply Cutout
- Details
  * Follow CIFAR-10 train details
    * batch size 128, learning rate 0.1, nesterov momentum 0.9, weight decay 0.0005
    * learning rate schedulers on [60, 120, 160] with 0.2 learning rate drop
    * augmentation : mean/std preprocessing, pad and crop


## 2. Result Comparison on CIFAR-10
|Source|Score|Detail|
|:-:|:-:|:-|
|Paper|96.92|Cutout, WRN-28-10, Average 5 runs|
|Current Repo|96.92|Cutout, WRN-28-10, Average 5 runs|
|Current Repo|96.90|Cutout with 0.5 probability, WRN-28-10, Average 5 runs|


## 3. Reference
- Improved Regularization of Convolutional Neural Networks with Cutout [[paper]](https://arxiv.org/pdf/1708.04552.pdf) [[official code]](https://github.com/uoguelph-mlrg/Cutout)
