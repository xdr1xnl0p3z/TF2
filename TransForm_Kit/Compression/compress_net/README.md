# INQ-Opt

## Introduction

Deep Compression is an implementation of the paper Incremental Network Quantization (https://arxiv.org/abs/1702.03044). We optimied the algorithm by improve the model data storage format. Implemented using the pytorch framework and ultimately used for FPGA platform computing. You can install pytorch and torchvision to use this demo and control the quantization step by changing the parameter "pre_percentage and cur_percentage".

## Installation

1. Python version shuold be 3.6+. 
2. Install PyTorch-0.4.1(the tested version) follows the instructions on the official website. 
3. Clone this repository. 

## Run

Before run the demo,  you need to understand the basic steps of using pytorch to train the cnn network.

Use Imagenet to train and compress resnet50 (torchvision model): (you can train any model from torchvision on imagenet)

```
./run.sh
```

After five steps, the model will be generated where all conv and innerproduct parameters are powers of two, for example:

```
$/models/part1_model_best.pth.tar 
$/models/part2_model_best.pth.tar 
... 
$/models/part5_model_best.pth.tar
```
## Test
You can run these models(The parameters of the convolution and fully connected layersare all powers of 2) on caffe and download these models from https://1drv.ms/u/s!Am9Mk04MA_K1aVMJj0sTWk0x7Bw?e=KHYmfy.

## Usage

According to the range of parameters of each layer, the parameters of the power of 2 can be saved in the form of 4 bits. Here is a way to save the model compression. (code will be available soon)

Model data storage format see 4bit_data_format.txt.

## Reference

1. https://arxiv.org/abs/1702.03044