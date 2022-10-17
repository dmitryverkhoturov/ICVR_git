# ICVR_git

[![colab](https://user-images.githubusercontent.com/4096485/86174089-b2709f80-bb29-11ea-9faf-3d8dc668a1a5.png)](https://colab.research.google.com/drive/1fVSBbH-XKnDYIyEqdm5uvvggpiwfw5x4)

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
