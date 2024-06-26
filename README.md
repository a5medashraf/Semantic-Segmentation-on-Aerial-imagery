# Semantic-Segmentation-On-Aerial-imagery
 
## Introduction
By using deep learning, Semantic Segmentation on Aerial Imagery deciphers landscapes from above, pinpointing objects and features with remarkable accuracy. This innovative method transforms aerial mapping, providing crucial insights for urban planning, environmental monitoring, and more.
This project aims to segment **6 classes** (Building, Land, Road, Vegetation, Water & Unlabeled) in the satellite image.

### DataSet: 1305 images divided into 8 groups (Tiles), Each group has its image Size as follows:
#### Data_Link: https://www.kaggle.com/datasets/humansintheloop/semantic-segmentation-of-aerial-imagery
<img src="https://github.com/a5medashraf/Semantic-Segmentation-on-Aerial-imagery/assets/72763763/b3309699-a10b-48b7-972f-5984ff84f033" width="500" height="450">


## Methodology
The methodology consists of **4** methods.

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

### Method 4: Post-Processing

We have tried to use post-processing to overcome the effect of the patchy image that has something that looks like there is a Grid on the image so we have used the following methodology:
1- Detect edges using the Sobel filter
2- Inpainting edges with neighbor pixels

### Final Result of SegNet: Skip-Connections:
![image](https://github.com/a5medashraf/Semantic-Segmentation-on-Aerial-imagery/assets/72763763/e6bc4c31-f26f-4f35-8278-d226817234c8)



#### Kaggle_Notebook: [https://www.kaggle.com/datasets/humansintheloop/semantic-segmentation-of-aerial-imagery](https://www.kaggle.com/code/a5medashraf/semantic-segmentation-using-segnet-skip-connection)

### References
- https://arxiv.org/abs/1511.00561
- https://www.kaggle.com/datasets/humansintheloop/semantic-segmentation-of-aerial-imagery
- https://www.researchgate.net/publication/358867978_Fully_convolutional_neural_network_with_attention_gate_and_fuzzy_active_contour_model_for_skin_lesion_segmentation





