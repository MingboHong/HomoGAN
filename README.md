# Unsupervised Homography Estimation with Coplanarity-Aware GAN


## Requirements



```
Pytorch = 1.7.1
Python = 3.7.10
Cuda = 10.2
Numpy = 1.19.4
```
You can also use this command
```
pip install -r requirements.txt
```

## Download the Deep Homography Dataset

Please refer to [Content-Aware Unsupervised Deep Homography Estimation.](https://github.com/JirongZhang/DeepHomography).

- Download raw dataset
```
# GoogleDriver
https://drive.google.com/file/d/19d2ylBUPcMQBb_MNBBGl9rCAS7SU-oGm/view?usp=sharing
# BaiduYun
https://pan.baidu.com/s/1Dkmz4MEzMtBx-T7nG0ORqA (key: gvor)
```
- Unzip the data to directory "./dataset"

- Run "video2img.py"
```
Be sure to scale the image to (640, 360) since the point coordinate system is based on the (640, 360).
e.g. img = cv2.imresize(img, (640, 360))
```

##How to test?
```
python evaluate.py --model_dir ./experiments/HomoGAN/ --restore_file xxx.pth
```
##How to train?
You need to modify ```./dataset/data_loader.py``` slightly for your owner environment, and you can also refer to [Content-Aware Unsupervised Deep Homography Estimation](https://github.com/JirongZhang/DeepHomography).

Pre-training:
```
1) set "pretrain_phase" in ./experiments/HomoGAN/params.json as True
2) python train.py --model_dir ./experiments/HomoGAN/
```
Fine-tuning:
```
1) set "pretrain_phase" in ./experiments/HomoGAN/params.json as False
2) python train.py --model_dir ./experiments/HomoGAN/ --restore_file xxx.pth
```
##Note

hh
In the future, we will upload a detailed implementation code of this paper on GitHub, including the pre-trained model.