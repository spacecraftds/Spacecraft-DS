### Spacecraft-DS: A Spacecraft Dataset for Key Components Detection and Segmentation via Hardware-in-the-loop Capture

## News
* 2022.11.23 Update 500 Spacecraft images.
* 2022.9.26 Our paper is submmited to IEEE Sensors Journa!

## Spacecraft-DS

* Spacecraft-DS  contains 2 types of spacecrafts, 9 types of key components, 3 types of illuminations (normal illumination, low illumination, and high saturation), and 2 types of motion states (approaching phase and hovering phase) <br><br>
* Spacecraft-DS can be downloaded here
* [Baidu disk](https://pan.baidu.com/s/16LHmym9-RBQ7trlmRnkI4Q)  Password:Spacecraft


---

## Spacecraft detection and segmentation models

* The Spacecraft detection and segmentation models in our paper could be downloaded here

* Detection
* [Baidu disk](https://pan.baidu.com/s/15iQRhna1JqZQ2r8gI-O4GA)  Password：Spacecraft
* Segmentation
* [Baidu disk](https://drive.google.com/file/d/1Sn8xSardyq-7ZL3bU_3CHaXIM8ZFRRr8/view?usp=sharing)
* If you can not download, please contact caoyi20@seu.edu.cn

---
For more information, please check our paper(Spacecraft-DS: A Spacecraft Dataset for Key Components Detection and Segmentation via Hardware-in-the-loop Capture)
## Abstract

The detection and segmentation of key spacecraft components is a crucial prerequisite for the successful execution of on-orbit capture tasks. However, the existing spacecraft datasets are plagued by several problems. These include a lack of a unified dataset for component detection and segmentation, a lack of consideration of the motion states of the spacecraft, and a lack of consideration of extreme illuminations. These problems hinder the development of related research. In response to the above problems, this paper aims to bridge this gap by releasing a dataset for detecting and segmenting key spacecraft components. In contrast to synthetic images, the proposed dataset is built via hardware-in-the-loop capture. The dataset contains 2 types of spacecrafts, 9 types of key components, 3 types of illuminations (normal illumination, low illumination, and high saturation), and 2 types of motion states (approaching phase and hovering phase). Furthermore, we conduct extensive experiments on Spacecraft-DS with state-of-the-art methods for detection and segmentation tasks and provide comprehensive analysis. In addition, the dataset can also be used to evaluate many computer vision tasks, such as small object detection, etc. 
<br><br>

## Detection Benchmark(AP)
| Model | 2 |3| 5 | 11 | 12 |13| 14| 15| 17|
| :---: | :---: | :---: | :---: | :---: | :---: |:---: | :---: | :---: | :---: |
| Faster R-CNN |0.607 | 0.708| 0.644 | 0.629| 0.884| 0.696| 0.792 | 0.847 | 0.708|
| Cascade R-CNN| 0.609 | 0.725 | 0.665| 0.632 | 0.923 | 0.713 | 0.815 | 0.87|0.747|
| Grid R-CNN|  0.602| 0.702 | 0.648| 0.621 |0.874 | 0.707 | 0.787 | 0.823 |0.724|
| Sparse R-CNN| 0.561 | 0.702 | 0.618| 0.574 | 0.920 | 0.668 | 0.798 | 0.896 |0.700|
|SSD| 0.565 | 0678 | 0.614| 0.595 | 0.835 | 0.674 | 0.749 | 0.813|0.653|
| YOLOV3| 0.450 | 0.500 | 0.433| 0.475 | 0.677 | 0.494 | 0.357 | 0.553 | 0.423 |
| YOLOF | 0.541 | 0.671 | 0.572| 0.536 | 0.847 | 0.633 | 0.728 | 0.801 | 0.617 |
| YOLOX |  0.575 | 0.709 | 0.627| 0.605 | 0.904 | 0.684 | 0.757 | 0.822 | 0.726 |

---
## Segmentation Benchmark(MIoU)
| Model | 2 |3| 5 | 11 | 12 |13| 14| 15| 17| MIoU|
| :---: | :---: | :---: | :---: | :---: | :---: |:---: | :---: | :---: | :---: | :---: |
| FCN |0.991 | 0.780| 0.792| 0.788| 0.957| 0.821| 0.925 | 0.872 | 0.969|0.877|
| PSPNet| 0.990 | 0.740 | 0.740| 0.777 | 0.956 | 0.788 | 0.925 | 0.872|0.959|0.861|
| DeeplabV3+|  0.981| 0.618 | 0.558| 0.718 |0.906 | 0.760 | 0.924| 0.862 |0.936|0.807|
| DANet| 0.991 | 0.770 | 0.782| 0.767 | 0.960 | 0.785 | 0.927 | 0.875 |0.943|0.867|
|CGNet| 0.985 | 0.668 | 0.548| 0.729 | 0.943 | 0.783 | 0.932 | 0.860 |0.908|0.817|
| OCRNet| 0.989 | 0.727 | 0.642| 0.741 | 0.956 | 0.756 | 0.936 | 0.869 | 0.959 |0.842|
| BiSeNetV2 | 0.989 | 0.946| 0.724| 0.708 | 0.953 | 0.739 | 0.917 | 0.862 | 0.945 |0.837|

---

## Experiment results

![](https://github.com/spacecraftds/Spacecraft-DS/blob/main/figure/16000020.jpg)



---

## Setup Environment
For this project, we follow the settings of mmsegmentation/mmdetection.

```shell
conda create --name open-mmlab python=3.8 -y
conda activate openmmlab
```

Find the correct pytorch version of your cuda version from [here](https://pytorch.org/get-started/previous-versions/).


And the mmcv version can be found [here](https://github.com/open-mmlab/mmcv/blob/master/README_zh-CN.md).




## Setup Datasets
Download the Spacecraft-DS dataset and extract the folder them to data/cityscapes or data/coco. The final folder structure should look like this:
```none
mmsegmentation
├── configs
├── data
│   ├── cityscapes
│   │   ├── leftImg8bit
│   │   │   ├── train
│   │   │   ├── val
│   │   ├── gtFine
│   │   │   ├── train
│   │   │   ├── val
├── ...
```
```none
mmdetection
├── mmdet
├── tools
├── configs
├── data
│   ├── coco
│   │   ├── annotations
│   │   ├── train2017
│   │   ├── val2017
│   │   ├── test2017
├── ...
```

## Framework Structure

Our project is based on [mmsegmentation](https://github.com/open-mmlab/mmsegmentation) and [mmdetection](https://github.com/openmmlab/mmdetection/tree/v2.2.1)).
Replace the files in mmsegmentation with our project.

The most important files are( spacecraft segmentation ):
```shell
mmsegmentation/configs/hrnet/fcn_hr18_4xb2-40k_cityscapes-512x1024.py
mmsegmentation/configs/_base_/datasets/cityscapes.py
mmsegmentation/configs/_base_/models/fcn_hr18.py
mmsegmentation/datasets/cityscapes.py


```
The most important files are( spacecraft detection ):
```shell
mmdetection/configs/hrnet/cascade_rcnn_hrnetv2p_w18_20e_coco.py
mmdetection/configs/_base_/datasets/coco_detection.py
mmdetection/configs/_base_/models/cascade_rcnn_r50_fpn.py
mmdetection/mmdet/datasets/coco.py



```
## Training

```shell
bash tools/dist_train.sh configs/cascade_rcnn/cascade_mask_rcnn_r50_fpn_1x_coco.py
```




## Acknowledgements

Our project is based on the following open-source projects.
* [MMSegmentation](https://github.com/open-mmlab/mmsegmentation)
* [MMDetection](https://github.com/openmmlab/mmdetection/tree/v2.2.1)
## Citation
If you find this paper useful in your research, please consider cite:

```
@Article{
title={Spacecraft-DS: A Spacecraft Dataset for Key Components Detection and Segmentation via Hardware-in-the-loop Capture},
author={Yi Cao, Jinzhen Mu, Xianghong Cheng, and Fengyu Liu},
}
```


