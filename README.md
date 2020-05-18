# R-Net

# Description
  This is an implement of "R-Net: A Relationship Network for Efficient and Accurate Scene Text Detection". The paper is underreview.
  The released model is pre-trained on SynthText (1 epoch) and then finetune on ICDAR2015. 
  
## Result
|        Model       	| recall 	| precision 	| F-measure 	| TIoU-R 	| TIoU-P 	| TIoU-F 	|
|:------------------:	|:---------:	|:------:	|:---------:	|:---------:	|:------:	|:---------:	|   
|  This implementation (IC15)	|    84.5   	|     88.1   	|    86.3   	| 60.1   	|     67.9   	|    63.7   	| 

Reasults on other datasets (e.g. MSRA-TD500, ICDAR2013, MLT, etc.) can be easily obtained by following our training setting.
# Requirement

* Python3 
* PyTorch-0.4.1 
* torchvision-0.2.1 
* shapely-1.6.4.post2 
* lanms-1.0.2 
* opencv-python(4.1.0.25)
  
# Installation

## Data

Download data images and annotions from [ICDAR 2015 Challenge 4](https://rrc.cvc.uab.es/?ch=4&com=downloads). Prepare data as:

~~~
./dataset/train/imgs
./dataset/train/txt
./dataset/test/imgs
./dataset/test/txt
~~~

## Pre-trained Model and Our trained Model.

Download pre-trained [VGG16](https://drive.google.com/file/d/1HgDuFGd2q77Z6DcUlDEfBZgxeJv4tald/view) (must rename as vgg16.pth) and [our traind model](https://pan.baidu.com/s/1HE6Yqg-8YfgSDQori58wcQ) (passward:oowz) Put both models into output/


# Test
```bash
CUDA_VISIBLE_DEVICES=0 python test_rnet.py
```
# Train
```bash
CUDA_VISIBLE_DEVICES=0,1 python train_rnet.py
```
# Evaluation

We use [online tool(https://rrc.cvc.uab.es/?ch=4]) to evaluate our results. 

# Speed

Run 
```bash
CUDA_VISIBLE_DEVICES=0 python speed_eval.py.
```
We add the model prediction time and the NMS time as the inference speed.
