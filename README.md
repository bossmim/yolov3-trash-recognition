# yolov3-trash-recognition

 image recognition technology for trash and bin (python) 

## Getting Started :)

These instructions will get a simple trash detection you can copy this project and run them on your local machine for development and testing purposes. 

This project use an implementation from https://github.com/zhaoyanglijoey/yolov3 

### Requirement

python 3.7 or Anaconda3

### (optional) create python virtual environment

```
pip install virtualenvwrapper-win
```
```
mkvirtualenv myProject
```
### Installing

Clone this model on your local machine

```
git clone https://github.com/bossmim/yolov3-trash-recognition
```
```
cd yolov3-trash-recognition
```
Install all the requires packages
```
pip install -r requirements.txt
```
Install Pytorch 0.4

OSX 
```
pip install torch==1.2.0 torchvision==0.4.0
```
Linux and Windows

```
pip install torch==1.2.0+cpu torchvision==0.4.0+cpu -f https://download.pytorch.org/whl/torch_stable.html
```

download weights file on directory ./weights 

link to google drive https://drive.google.com/file/d/19fPCqVHgl850OrRJvEdIXKzE5FdCkz0R/view

or using this command

```
wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=19fPCqVHgl850OrRJvEdIXKzE5FdCkz0R' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=19fPCqVHgl850OrRJvEdIXKzE5FdCkz0R" -O yolov3_3c_7400.weights && rm -rf /tmp/cookies.txt
```

## Running the detection

### test on image

Run detector.py and choose your input and output directory for example

```
python detector.py -i sample/sam1.jpg -o out
```

### test on video

Recommend to run on gpu with CUDA installed

```
python detector.py -i sampleVideo/vsam1.mp4 -v -o out
```

## Result

![GitHub Logo](/demo/sam1.jpg) 

type| bin | plastic_bag | trash
--- | --- | --- | ---
accuracy(avg) | 99% | 98% | 99%
count| 3 | 10 | 9

## Let see our model accuracy 
From the result, the accuracy of trash class is quite low, this is beacuse we use too small particle on the training process so the model cannot different between the actual trash and the reflection of light or the small rock. these can be solve by useing the bigger dataset or using a clear shape of images

Next is plastic bag class, the accuracy is quite acceptable, aalthough the accuracy is not high but the measurement of true positive is much higher than false positive which means that it has a high chance to detect correctly. The model can be improve by training more kinds of plastic bag images.

Last is bin class, which has the highest accuracy because it has the most clearly shape which can easily be identify by the model(CNNs)

### Detection result graph
![GitHub Logo](/error/detection-results-info.png)
### Average Precision graph
![GitHub Logo](/error/mAP.png)
### Precision-Recall graph of bin class
![GitHub Logo](/error/bin.png)
### Precision-Recall graph of plastic_bag class
![GitHub Logo](/error/plastic_bag.png)
### Precision-Recall graph of trash class
![GitHub Logo](/error/trash.png)

## credit

This project use yolov3 to train the model
see more on https://pjreddie.com/darknet/yolo/

