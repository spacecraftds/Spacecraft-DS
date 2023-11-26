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

* TheSpacecraft detection and segmentation models and their equipments diagrams in our paper could be downloaded here

* Detection
* [Baidu disk](https://pan.baidu.com/s/15iQRhna1JqZQ2r8gI-O4GA)  Password：BUAA
* Segmentation
* [Baidu disk](https://drive.google.com/file/d/1Sn8xSardyq-7ZL3bU_3CHaXIM8ZFRRr8/view?usp=sharing)
* If you can not download, please contact caoyi20@seu.edu.cn

---
For more information, please check our paper(Spacecraft-DS: A Spacecraft Dataset for Key Components Detection and Segmentation via Hardware-in-the-loop Capture)
## Abstract

The detection and segmentation of key spacecraft components is a crucial prerequisite for the successful execution of on-orbit capture tasks. However, the existing spacecraft datasets are plagued by several problems. These include a lack of a unified dataset for component detection and segmentation, a lack of consideration of the motion states of the spacecraft, and a lack of consideration of extreme illuminations. These problems hinder the development of related research. In response to the above problems, this paper aims to bridge this gap by releasing a dataset for detecting and segmenting key spacecraft components. In contrast to synthetic images, the proposed dataset is built via hardware-in-the-loop capture. The dataset contains 2 types of spacecrafts, 9 types of key components, 3 types of illuminations (normal illumination, low illumination, and high saturation), and 2 types of motion states (approaching phase and hovering phase). Furthermore, we conduct extensive experiments on Spacecraft-DS with state-of-the-art methods for detection and segmentation tasks and provide comprehensive analysis. In addition, the dataset can also be used to evaluate many computer vision tasks, such as small object detection, etc. 
<br><br>

## Detection Benchmark
| Method | BG | Panel | Antenna | Instrument | Thruster | Optical Payload | mIoU | mIoU(no bg) |
| :---: | :---: | :---: | :---: | :---: | :---: |:---: | :---: | :---: |
| Danet| 99.6 | 85.69 | 77.65 | 54.24 | 46.16 | 64.64 | 71.33 | 65.68 |
| Deeplabv3+| 99.83 | 88.67 | 84.98 | 66.53 | 62.25 | 76.99 | 76.99 | 75.88 |
| Ocrnet| 99.69 | 89.03| 83.33 | 63.3 | 56.21 | 73.9 | 77.58 | 73.15 |
| Sfnet| 99.74 | 89.51 | 86.6 | 68.77 | 67.66 | 78.42 | 81.78 | 78.19 |
| VAN-B| 99.77 | 90.97 | 84.99 | 71.24 | 66.65 | 78.36 | 82.0 | 78.44 |
| ConvNext-B| 99.83 | 93.85 | 89.66 | 72.98 | 72.92 | 83.87 | 85.52 | 82.66 |
| Our method | 99.85 | 94.18 | 89.85 | 77.06 | 76.19 | 85.71 | 87.14 | 84.60 |  

---
## Segmentation Benchmark
| Method | BG | Panel | Antenna | Instrument | Thruster | Optical Payload | mIoU | mIoU(no bg) |
| :---: | :---: | :---: | :---: | :---: | :---: |:---: | :---: | :---: |
| Danet| 99.6 | 85.69 | 77.65 | 54.24 | 46.16 | 64.64 | 71.33 | 65.68 |
| Deeplabv3+| 99.83 | 88.67 | 84.98 | 66.53 | 62.25 | 76.99 | 76.99 | 75.88 |
| Ocrnet| 99.69 | 89.03| 83.33 | 63.3 | 56.21 | 73.9 | 77.58 | 73.15 |
| Sfnet| 99.74 | 89.51 | 86.6 | 68.77 | 67.66 | 78.42 | 81.78 | 78.19 |
| VAN-B| 99.77 | 90.97 | 84.99 | 71.24 | 66.65 | 78.36 | 82.0 | 78.44 |
| ConvNext-B| 99.83 | 93.85 | 89.66 | 72.98 | 72.92 | 83.87 | 85.52 | 82.66 |
| Our method | 99.85 | 94.18 | 89.85 | 77.06 | 76.19 | 85.71 | 87.14 | 84.60 |  

---

## Experiment results

* Our dataset
<p align="center"><img src="figure/result3.png" width="800"></p>

* [URSO](https://pedropro.github.io/project/urso/) dataset
<p align="center"><img src="figure/urso_results.png" width="800"></p>

* NASA Results
<p align="center"><img src="figure/nasa.png" width="800"></p>

---

## Setup Environment
For this project, we follow the settings of mmsegmentation.

```shell
conda create --name open-mmlab python=3.7 -y
conda activate open-mmlab
```

Find the correct pytorch version of your cuda version from [here](https://pytorch.org/get-started/previous-versions/).

For our computer, the cuda version is 10.1. 
And the mmcv version can be found [here](https://github.com/open-mmlab/mmcv/blob/master/README_zh-CN.md).

```shell
pip install torch==1.8.1+cu101 torchvision==0.9.1+cu101 -f https://download.pytorch.org/whl/torch_stable.html
pip install mmcv-full==1.6.0 -f https://download.openmmlab.com/mmcv/dist/cu101/torch1.8.0/index.html
pip install mmsegmentation==0.27.0
pip install mmcls
```


## Setup Datasets
Download the UESD dataset and extract the folder them to data/cityscapes. The final folder structure should look like this:
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



## Framework Structure

Our project is based on [mmsegmentation](https://github.com/open-mmlab/mmsegmentation).
Replace the files in mmsegmentation with our project.

The most important files are :
```shell
configs/convnext/upernet_convnext_base_fp16_512x512_160k_ade20k.py

configs/base/datasets/cityscapes.py

configs/base/models/upernet_convnext.py 

mmseg/models/decode_heads/LUper_head.py

mmseg/datasets/cityscapes.py

```

## Training

```shell
bash tools/dist_train.sh configs/convnext/upernet_convnext_base_fp16_512x512_160k_ade20k.py 4
```

## Val and Test

After the training, you will find a folder named work_dirs/upernet_convnext_base_fp16_512x512_160k_ade20k

```shell
bash ./tools/dist_test.sh configs/convnext/upernet_convnext_base_fp16_512x512_160k_ade20k.py workdirs/upernet_convnext_base_fp16_512x512_160k_ade20k/iter_80000.pyth  --eval mIoU --eval_options "imgfile_prefix=./UESD_results"
```

## Acknowledgements

Our project is based on the following open-source projects.
* [MMSegmentation](https://github.com/open-mmlab/mmsegmentation)

## Citation
If you find this paper useful in your research, please consider cite:

```
@Article{ZYP2022UESD,
title={Intelligent Recognition of Spacecraft Components from Photorealistic Images Based on Unreal Engine 4},
author={Yunpeng Zhao, Rui Zhong and Linyan Cui},
journal={Advances in Space Research},
year={2022}
}
```


