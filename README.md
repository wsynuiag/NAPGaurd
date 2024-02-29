# NAPGuard: Towards Detecting Naturalistic Adversarial Patches
Welcome to the official implementation for the CVPR2024 paper _NAPGuard: Towards Detecting Naturalistic Adversarial Patches_. We will keep updating our source code.
![image](https://github.com/wsynuiag/NAPGaurd/blob/main/figure/framework.png)

# Usage 

## Download the dataset
Our GAP dataset will be available soon.

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

