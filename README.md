# Classic lightweight convolutional neural networks and their integral parts

## Introduction

<!-- - Why lightweight CNN(Convolutional Neural Networks) develop? -->
Lightweight Convolutional Neural Networks (Lwt-CNN) generally refer to CNN with fewer parameters. They have raised researchers' much attention and developed rapidly over the last decade due to the advantages such as feasible embeded deployment, real-time applications and less communication overhead.

<!-- - What is the first lightweight CNN? -->
The first lightweight CNN dates back to **SqueezeNet** which was proposed in ICLR 2017. 

## Development path
<!-- What is the development trend of lightweight CNN? -->
The picture below shows the development of lightweight CNN over the years.

![development_path](https://github.com/ardentyang/lwt-cnn/tree/main/images/develop_path.jpg)

## Quick tour of the core modules
<!-- What are the core modules in each lightweight CNN? -->
<!-- The following illustrates the core modules of each lightweight CNN in its original paper. It is recommended to read it in conjunction with the code in modules. -->

<!-- ### SqueezeNet

### Xception

### MobileNet

### ShuffleNet

### Summary -->

The following table summarizes the structure of the core modules in the lightweight neural networks. The usage of batch normalization (BN) and activation function (act) in these modules are particularly indicated.

|LWT-CNN|Module|Structure|BN|act|
|-|-|-|-|-|
|SqueezeNet|Fire|squeeze (k=1 nc:arrow_down:) <br> + expand (k=1 nc:arrow_up: + k=3 nc:arrow_up: concat)|❌|ReLU|
|Xception|SeparableConv2d <br> Block|pw (k=1 nc😐) + dw (k>1 nc:arrow_up:) <br> act + SeparableConv2d + BN|❌ <br> :heavy_check_mark:|❌ <br> :heavy_check_mark:|
|MobileNet|Block|dw (k=3 nc😐) + pw (k=1 nc:arrow_up:)|:heavy_check_mark:|:heavy_check_mark:|
|ShuffleNet|ShuffleUnit|gconv (k=1 nc:arrow_down:) <br> + channel shuffle <br> + dwconv (k=1 nc😐) <br> + gconv (k=1 nc:arrow_up:) <br> add/concat|:heavy_check_mark: <br> - <br> :heavy_check_mark: <br> :heavy_check_mark: <br> ❌|ReLU <br> - <br> ❌ <br> ❌ <br> ReLU|

