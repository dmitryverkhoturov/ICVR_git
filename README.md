# ICVR_git

[![colab](https://user-images.githubusercontent.com/4096485/86174089-b2709f80-bb29-11ea-9faf-3d8dc668a1a5.png)](https://colab.research.google.com/drive/1fVSBbH-XKnDYIyEqdm5uvvggpiwfw5x4)

## How to run it

This project is based on [Darknet Framework](https://github.com/AlexeyAB/darknet). You should go there first to see how to compile Darknet on your platform. If you’re on Linux, you can just launch YOLOv4_Custom.ipynb from my repository. Also you can use [this link](https://colab.research.google.com/drive/1fVSBbH-XKnDYIyEqdm5uvvggpiwfw5x4) to run custom object detection in Google Colab.

To run our custom object detection after cloning Darknet repo
```bash
git clone https://github.com/AlexeyAB/darknet
```

We should clone current repo
```bash
git clone https://github.com/dmitryverkhoturov/ICVR_git
```

And run this code to merge folders

```bash
import subprocess as sbp
import os

path='ICVR_git/darknet'
fol = os.listdir(path)
p2 = 'darknet'

for i in fol:
    p1 = os.path.join(path,i)
    p3 = 'cp -r ' + p1 +' ' + p2+'/.'
    sbp.Popen(p3,shell=True)
```

To get custom weights run this

```bash
wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=1dnLded_oAvy7ksK45Ud9eCnPxugPZASw' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=1dnLded_oAvy7ksK45Ud9eCnPxugPZASw" -O yolov4-custom_2000.weights && rm -rf /tmp/cookies.txt
```

Everything else is similar to the Darknet guide.

To detect your own image, you should run this line and change **IMAGE** to the path of an image you want to run detection on

```markdown
./darknet detector test data/obj.data cfg/yolov4-custom.cfg yolov4-custom_2000.weights **IMAGE** -thresh 0.3
imShow('predictions.jpg')
```

## Detection examples
<div align="center">
	<img src="predictions.jpg" width="80%" height="10%"/>
</div>
<div align="center">
	<img src="predictions (1).jpg" width="80%" height="10%"/>
</div>

## Test results

Safety vest, ap = 97.59%   	 (TP = 1956, FP = 510)  
Hard hat,    ap = 96.78%   	 (TP = 2001, FP = 64)  
Person,      ap = 99.86%   	 (TP = 2101, FP = 632)


For conf_thresh = 0.25, precision = 0.83, recall = 0.97, F1-score = 0.90  
For conf_thresh = 0.25, TP = 6058, FP = 1206, FN = 197, average IoU = 67.58 %  

IoU threshold = 50 %, used Area-Under-Curve for each unique Recall  
Mean average precision (mAP@0.50) = 0.980792, or 98.08 %
