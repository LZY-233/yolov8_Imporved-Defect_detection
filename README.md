# Industrial defect auxiliary detection system based on improved YOLOv8 algorithm(基于改进YOLOv8算法的工业瑕疵辅助检测系统)
Traditional industrial defect detection mainly relies on manual visual inspection or the use of simple machine vision systems, but these methods have problems such as low efficiency, low accuracy, high labor intensity, and susceptibility to human factors. so I developed a PCB defect auxiliary detection system based on the improved YOLOv8 algorithm. 
## Methonds
The project proposed an improved YOLOv8 algorithm. First, a residual attention mechanism, namely the CBAM attention mechanism ResCBAM with residual connection, was proposed and added to the head of the YOLOv8 model to improve the model's ability to extract features while preventing the model from overfitting. GhostConv was used to replace the ordinary convolution in the backbone to make the model more lightweight while ensuring performance. At the same time, the WIOU loss function was introduced to replace the original CIOU loss function to avoid the problem of small targets having too much influence on the loss function and alleviate the problem of imbalanced data sets. The experimental results show that compared with the original YOLOv8 model, the proposed improved YOLOv8 model has improved Precision, Recall, F1score, and mAP50 by 5.6%, 0.9%, 3.1%, and 1.5% on the public NEU-DET dataset, respectively. The mAP50 is 79.2%, reaching the state-of-the-art (SOTA) level, significantly improving the detection accuracy and efficiency, which is of great significance to ensuring product quality and reducing production costs. The model is also deployed on the WEB side, and users can access the web page to upload pictures or take photos for detection, and can save the results.

Project deployment website: https://huggingface.co/spaces/llzzyy233/

## Architecture
<p align="center">
  <img src="imgs/YOLOV8+GhostConv+Res_CBAM+WIOU.jpg" width="1024" title="details">
</p>

## Table : Comparisons with other detection models on the NEU-DET dataset models
| Model | Test Size | Param. | FLOPs |  mAP<sub>50</sub><sup>val</sup> | mAP<sub>50-95</sub><sup>val</sup> |
| :--: | :-: | :-: | :-: | :-: | :-: |
| YOLOv5s | 640 | 7.04M | 15.9G |  70.87% | 35.02%|
| YOLOv5m | 640 | 20.89M | 183.5G |  71.74% | 36.67%  |
| YOLOv5l | 640 | 46.17M | 183.5G |  72.23% | 36.74%  |
| YOLOv7 | 640 | 37.22M | 196.2G |  71.92% | 37.2% |
| YOLOv8 | 640 | 3.01M | 8.1G |  77.7% | 46.2%  |
| **Our model** | **640** | **4.05M** | **10.2G** | **79.2%** | **47%** |

## FIgure: Comparison of accuracy before and after improvement
<p align="center">
  <img src="imgs/compare.jpg" width="1024" title="details">
</p>

## Dataset
You can download the NEU-DET Dataset from this website https://pan.baidu.com/s/1K-mTgSJfhFrcVSO8MUqHbQ?pwd=6666 

The dataset had already been divided into training, validation, and testing set (80-10-10%) 

## Results
### PR_Curve
<p align="center">
  <img src="imgs/PR_Curve.png" width="1024" title="details">
</p>

### confusion__matrix_normalized
<p align="center">
  <img src="imgs/confusion_matrix_normalized.png" width="1024" title="details">
</p>