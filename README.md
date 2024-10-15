# NAPGuard: Towards Detecting Naturalistic Adversarial Patches
Welcome to the official implementation for the CVPR2024 paper _NAPGuard: Towards Detecting Naturalistic Adversarial Patches_. 

In this paper, we propose NAPGuard to provide strong detection capability against naturalistic adversarial patches (NAPs) via the elaborated critical feature modulation framework. For improving precision, we propose the aggressive feature aligned learning to enhance the model's capability in capturing accurate aggressive patterns. To enhance generalization, we design the natural feature suppressed inference to universally mitigate the disturbance from different NAPs.
![image](https://github.com/wsynuiag/NAPGaurd/blob/main/figure/framework.png)

# Usage 

## Download the Generalized Adversarial Patch (GAP) dataset
To address the lack of datasets in physical adversarial patch detection, we introduce the Generalized physical Adversarial Patch detection (GAP) dataset, aiming to provide an evaluation benchmark for future detection approaches.

The GAP dataset contains 9266 images and 25 types of adversarial patches in total. Every adversarial patch is located with a bounding-box annotation. Detailed statistics of adversarial patches in training set and testing set are shown in the paper. All images are stored in PNG format with a fixed size of 416 $\times$ 416 pixels by padding or resizing. The dataset is partitioned into a training set (5617 images) and a testing set (3649 images). The original images are derived from [INRIA-Person](https://inria.hal.science/file/index/docid/548512/filename/hog_cvpr2005.pdf) and [MS COCO](https://cocodataset.org/#home).

Our GAP dataset can be downloaded at https://drive.google.com/drive/folders/1xk9C6rFFSDPLUa1162EyxwodEsl7tfxD?usp=drive_link.

## Training Stage
To train a patch detector, run
```python
python train_NAPGuard.py --AFAL
```
Results will be saved in `runs/NAPGuard_train/`



## Inference Stage
To evaluate the trained patch detector, run:
```python
python val_NAPGuard.py --NFSI
```
or adjust the hyper-parameters by running:
```python
python val_NAPGuard.py --NFSI --thres_factor thres --sigma sigma
```
Results will be saved in `runs/NAPGuard_val/`

## Updates
We also provide the patch detector `NAPGuard.pt` used in our paper.
You can download it at https://drive.google.com/drive/folders/1glJfqmxaM9qCy01jbsMOTww8HhlRwtY3?usp=sharing

## Citation
If our work or this repo is useful for your research, please cite our paper as follows:
```
@InProceedings{Wu_2024_CVPR,
    author    = {Wu, Siyang and Wang, Jiakai and Zhao, Jiejie and Wang, Yazhe and Liu, Xianglong},
    title     = {NAPGuard: Towards Detecting Naturalistic Adversarial Patches},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2024},
    pages     = {24367-24376}
}
```
