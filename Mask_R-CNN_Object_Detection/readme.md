
# Using the Mask R-CNN Object Detector

Applies the Mask R-CNN Object Detector to detect and classift 80 object types in a given image. 

### Requirements
   - Linux or macOS (Windows is not currently officially supported)
   -Python 3.6+
   - PyTorch 1.3+
   - CUDA 9.2+ (If you build PyTorch from source, CUDA 9.0 is also compatible)
   - GCC 5+
   - mmcv

### Install MMCV
```
!pip install mmcv-full -f https://download.openmmlab.com/mmcv/dist/cu111/torch1.10.0/index.html 
```
### Clone the mmdetection repository
```
!git clone https://github.com/open-mmlab/mmdetection.git 
!cd mmdetection; python setup.py install 
```
### MMDetection Results and Models
   - Backbone : R-101-FPN
   - Style : pytorch
 > https://github.com/open-mmlab/mmdetection/tree/master/configs/mask_rcnn
--------------------------------------------------------------------------------
## mask_rcnn_pascal_voc_train 
### PASCAL VOC Dataset download
```
!wget http://pjreddie.com/media/files/VOCtrainval_06-Nov-2007.tar
!tar -xvf VOCtrainval_06-Nov-2007.tar > /dev/null 2>&1
```
MMDetection converts PASCAL VOC Data to coco format because it prefers the COCO format the most to learn Mask RCNN.

### Dataset Converters
Dataset Converters is a conversion toolset between different object detection and instance segmentation annotation formats.

### Introduction
There are multiple different dataset annotation formats for object detection and instance segmentation.
This repository contains a system of scripts, which simplify the conversion process between those formats. We rely on COCO format as the main representation.

#### Clone the Dataset Converters repository
```
!git clone https://github.com/ISSResearch/Dataset-Converters.git
```
#### Installation
```
!cd Dataset-Converters; pip install -r requirements.txt
```
#### Usage
**Conversion**
To perform conversion between different dataset formats, we provide the script called convert.py.
For example, suppose, you have ADE20K dataset and you want to convert it into COCO format.
For that purpose, please type
```
python convert.py --input-folder <path_to_folder_ADE20K_2016_07_26> --output-folder <output_path> \
                  --input-format ADE20K --output-format COCO --copy
``` 
 > Note that the Dataset converter package downgrades the opencv to 3.4
--------------------------------------------------------------------------------------------------------------------
### Inference on images

**Source image**
![image](https://user-images.githubusercontent.com/69446702/174579317-cb452017-5d4e-4da1-8906-dd5b352ba287.png)
<img src="https://user-images.githubusercontent.com/69446702/174579317-cb452017-5d4e-4da1-8906-dd5b352ba287.png" width="70%" height="70%" title="px(픽셀) 크기 설정" ></img>

**Inference on images**
![image](https://user-images.githubusercontent.com/69446702/174499240-99c84685-77ef-459d-9944-c1a043302e93.png)

**Manual detection on images**
![image](https://user-images.githubusercontent.com/69446702/174502352-b0c71a24-ea3b-4434-9c07-369a6b66158c.png)
--------------------------------------------------------------------------------------------------------------------
## References
 > https://github.com/ISSResearch/Dataset-Converters \
 > https://github.com/open-mmlab/mmdetection
