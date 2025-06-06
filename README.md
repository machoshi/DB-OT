# Double-Bounded Optimal Transport for Advanced Clustering and Classification

This code provides a PyTorch implementation and pretrained models for DB-OT, and will be updated with advanced contrastive learning applications.

## Setup

Follow the steps below to construct the environment for DB-OT.

### Requirements

+ Python 3

+ PyTorch (version >= 1.4)

+ yaml

+ higher(version == 0.2.1)

## Usage

## Introduction

(1) "cls_freq"
the Long Tail list argments. It's used to build the long tail data in training and testing. You don't need 
to change .

(2) "clustering"
the code of clustering

(3) "config"
It stores the configs of training. All the parameter in each file can change. The parameter in each file can 
get the best result.

(4) "data"
You don't need to change this folder.
It stores the file that builds the training and testing data sets

(5) "dataset"
It stores the CIFAR10, CIFAR100, ImageNet data.

(6) "logs"
It stores the result

(7) "loss"
It stores the loss function. You can choose which to use or write your own loss function.

(8) "models"
It stores the models that could be used to train.

(9) "logger.py", "utils.py"
You don't need to change.
It's the tool functions that helps to train.

(10)"main.py"
The main function to train.
You could train the data by 
"python main.py --cfg ./config/CIFAR10_LT/softmax_imba200.yaml"

You could test the model by
"python main.py --cfg ./config/CIFAR10_LT/softmax_imba200.yaml --test"

If you want to test the long tail data set, you could use "--long_tail".

"long_tail" has three value. "0" means using uniform testing dataset.
"1" means using long tail dataset. "2" means using reverse long tail dataset.

(11)"run.py"
The actual training function.
You can change the inference function at 723-726 line. 
723 is the Softmax function. 724 is our DBOT function. 725 is Classifier Normalization.
726 is Class Aware Bias.

q at 718 line is the delta of bounds.

You can also change the number of iteration at 722 to try different inference itreation.

## Citation
If you find this repository useful in your research, please cite:
```
@inproceedings{shi2024double,
  title={Double-bounded optimal transport for advanced clustering and classification},
  author={Shi, Liangliang and Shen, Zhaoqi and Yan, Junchi},
  booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},
  volume={38},
  number={13},
  pages={14982--14990},
  year={2024}
}
```
