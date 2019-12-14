# yolov3-trash-recognition

 image recognition technology for trash and bin (python on window) 

## Getting Started :)

These instructions will get a simple trash detection you can copy this project and run them on your local machine for development and testing purposes. 

This project use an implementation from https://github.com/zhaoyanglijoey/yolov3 

### Requirement

 python 3.5

 Pytorch 0.4 (see the installation below)

OSX 
```
pip install torch==1.2.0 torchvision==0.4.0
```
Linux and Windows

```
pip install torch==1.2.0+cpu torchvision==0.4.0+cpu -f https://download.pytorch.org/whl/torch_stable.html
```

### Installing

clone this model on your local machine

```
git clone https://github.com/bossmim/yolov3-trash-recognition
```
```
cd yolov3-trash-recognition
```

(optional) create python virtual environment
```
pip install virtualenvwrapper-win
```
```
mkvirtualenv myProject
```
install all the requires packages
```
pip install -r requirements.txt
```

download weights file on directory ./weights 

link to google drive https://drive.google.com/drive/folders/1Uu8NVT-gO5o5yrfz60iacZhfWXY1J_dH?usp=sharing


## Running the detection

### test on image

run detector.py and choose your input and output directory for example

```
python detector.py -i sample/sam1.jpg -o out
```

### test on video

```
python detector.py -i sampleVideo/vsam1.mp4 -v -o out
```

## Result

![GitHub Logo](/demo/sam1.jpg)

type| bin | plastic_bag | trash
--- | --- | --- | ---
accuracy(avg) | 99% | 98% | 99%
count| 3 | 10 | 9


## cratedit

this project use yolov3 to train the model
see more on https://pjreddie.com/darknet/yolo/

