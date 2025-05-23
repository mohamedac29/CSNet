## CSNet: Cross-Stage Subtraction Network for Real-Time Semantic Segmentation in Autonomous Driving.

Accepted at IEEE Transactions on Intelligent Transportation Systems [T-ITS](https://ieeexplore.ieee.org/abstract/document/10817473)



You need to download the Cityscapes datasets. and rename the folder cityscapes, then put the data under data folder.

# Clone this repository

```
git clone https://github.com/mohamedac29/CSNet
cd CSNet
```

### Datasets Preparation

## 1. Cavmvid Dataset
You can download the Camvid dataset from [Kaggle](https://www.kaggle.com/datasets/carlolepelaars/camvid)

## Citysscapes Dataset
* You need to download the [Cityscapes](https://www.cityscapes-dataset.com/) datasets, unzip them and put the files in the `data` folder with following structure.

```
$SEG_ROOT/data\ 
├── Camvid
│       ├── images
│       ├── labels

│    ├── cityscapes
│        ├── gtFine
│            ├── test
│            ├── train
│            ├── val
│     ── ── leftImg8bit
│             ├── test
│             ├── train
│             └── val
│    ├── list
         ├── Camvid
│          ├── test.lst
│          ├── train.lst
│          ├── trainval.lst
│          └── val.lst
│       ├── cityscapes
│          ├── test.lst
│          ├── train.lst
│          ├── trainval.lst
│          └── val.lst
   
```

### Training

##  Training on Camvid datsaset

* For instance, train the CSNet-S on Camvid dataset with batch size of 8 on 2 GPUs:
````bash
python tools/train.py --cfg configs/camvid/CSNet_small_camvid.yaml GPUS (0,1) TRAIN.BATCH_SIZE_PER_GPU 4
````


* To evaluate the CSNet-S on Camvid set:

````bash
python tools/eval.py --cfg configs/camvid/CSNet_small_camvid.yaml \
                          TEST.MODEL_FILE checkpoints/camvid/CSNet_small_Camvid.pth \
                          DATASET.TEST_SET list/camvid/test.lst
````
### Citation

If you find this work useful in your research, please consider citing.

```
@article{elhassan2024p2at,
  title={P2AT: Pyramid pooling axial transformer for real-time semantic segmentation},
  author={Elhassan, Mohammed AM and Zhou, Changjun and Benabid, Amina and Adam, Abuzar BM},
  journal={Expert Systems with Applications},
  volume={255},
  pages={124610},
  year={2024},
  publisher={Elsevier}
}
```

```
@article{elhassan2024csnet,
  title={CSNet: Cross-Stage Subtraction Network for Real-Time Semantic Segmentation in Autonomous Driving},
  author={Elhassan, Mohammed AM and Zhou, Changjun and Zhu, Donglin and Adam, Abuzar BM and Benabid, Amina and Khan, Ali and Mehmood, Atif and Zhang, Jun and Jin, Hu and Jeon, Sang-Woon},
  journal={IEEE Transactions on Intelligent Transportation Systems},
  year={2024},
  publisher={IEEE}
}
```