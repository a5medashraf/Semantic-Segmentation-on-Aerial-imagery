# Semantic-Segmentation-On-Aerial-imagery
 
## Introduction
By using deep learning, Semantic Segmentation on Aerial Imagery deciphers landscapes from above, pinpointing objects and features with remarkable accuracy. This innovative method transforms aerial mapping, providing crucial insights for urban planning, environmental monitoring, and more.
This project aims to segment **6 classes** (Building, Land, Road, Vegetation, Water & Unlabeled) in the satellite image.

### DataSet: 1305 images divided into 8 groups (Tiles), Each group has its image Size as follows:

<img src="https://github.com/a5medashraf/Semantic-Segmentation-on-Aerial-imagery/assets/72763763/b3309699-a10b-48b7-972f-5984ff84f033" width="500" height="450">


## Methodology
The methodology consists of **5** methods.

### Method 1: Patching
 
The first method is patching the images to have the same image shape of 256x256 by Cropping the column and the width to be divisible by 256 and then patching the image.
For Example:
The image of 797 x 644 will be 768 x 512 and then crop the image into 6 patches.
![image](https://github.com/a5medashraf/Semantic-Segmentation-on-Aerial-imagery/assets/72763763/98b491fb-0352-469d-bf2d-1c35011b308d)

### Method 2: Mask Encoding

This Mask Encoding focuses on a specific step within a 6-class semantic segmentation process. It takes a mask image, where each pixel represents a class (1 to 6), and converts it into a format suitable for training a model. This conversion involves creating a one-hot vector for each pixel, where only the element corresponding to the class (1-6) has a value of 1, and all others are 0.

![image](https://github.com/a5medashraf/Semantic-Segmentation-on-Aerial-imagery/assets/72763763/f111a4ad-1f22-4ea9-a353-30ea3e963901)

### Method 3: Modeling & Evaluation

## Modeling:
SegNet Architecture and SegNet: Skip-Connection with depthwise convolution were used to train  on the data.
**Training Arguments:**
- Epochs: 100
- Batch Size: 16
- Optimizer: Adam
- Loss: Dice-Loss

## Evaluation:
The Evaluation was Done using Dice-Coeffient.
![image](https://github.com/a5medashraf/Semantic-Segmentation-on-Aerial-imagery/assets/72763763/ff1523d8-4586-4993-9844-39fcac339d02)



### Results

According to human observation and testing the program has a **good** result. However, more data are required to be apple to measure the error using a **metric** and to better **tune the Thresholds**.

### How to use it

just download the code.py file and import the required libraries and run it on the python editor.

### References
- https://www.researchgate.net/publication/365977982_COUNTERFEIT_CURRENCY_DETECTION_USING_IMAGE_PROCESSING
- https://iopscience.iop.org/article/10.1088/1757-899X/263/5/052047
- https://ijcsmc.com/docs/papers/April2019/V8I4201914.pdf
- https://www.mintageworld.com/knowledge-base/security-features-on-current-banknotes/


