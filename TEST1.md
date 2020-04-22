# Instructions
Please upload a txt file in the form of `firstname_lastname.txt`. Each line will have your answer to the corresponding question, e.g. `Q1: 1`. Note that there can be multiple correct answers per question, in which case separate your answers with a comma, e.g. `Q1: 1, 2, 3`. Example file:
```
Q1: 1
Q2: 1, 2
Q3: 3, 4
...
```
Upload your answers to this [dropbox link][dropbox] by Tuesday, April 28, EOD. 

# Test
### Question 1
Object detection from an image tackles the task of:
  1. Predicting wether an object category is present in the image
  2. Predicting the number of object instances in the image
  3. Predicting the bounding boxes and object category of all object instances in the image

### Question 2
Semantic segmentation from an image tackles the task of:
  1. Marking each pixel in the image with _foreground_ vs. _background_
  2. Marking each pixel in the image with the object category it belongs to
  3. Marking each pixel in the image with depth ordering, starting from closest in the camera to furthest

 ### Question 3
 Instance segmentation from an image tackles the task of:
   1. Detecting all objects in the image and predicting their silhouette
   2. Predicting the transformation of an object silhouette to fit a target mask
   3. Predicting the instances in an image that could be replaced by other similar shapes 

### Question 4
[R-CNN][rcnn] trains a CNN to classify object region candidates into `C` classes, which are produced by a bottom-up region proposal pipeline.
  1. True 
  2. False

### Question 5
For an image `I` with `M` object candidates, [R-CNN][rcnn] will make this number of forward passes with the CNN:
  1. `M/2`
  2. `M`
  3. 1

### Question 6
[Faster R-CNN][fasterrcnn] trains a region proposal network (RPN), which shares the same network with the object detector:
  1. True
  2. False

### Question 7
In [Faster R-CNN][fasterrcnn], the RPN predicts object regions which are:
  1. Category agnostic
  2. Category specific

### Question 8
In [Faster R-CNN][fasterrcnn], the RPN places anchors at each location in the image of different aspect ratio and sizes. How many anchors per location are there:
  1. 3
  2. 9
  3. 128

### Question 9
[Mask R-CNN][maskrcnn] introduces an ROIAlign layer which pools features from an input feature map for each proposed region by:
  1. Rounding the region box coordinates to integer grid locations and then sampling the features using bilinear interpolation
  2. Sampling features from a region using bilinear interpolation and without any rounding of the box coordinates.

## Question 10
ROIAlign mantains a one-to-one alignment between:
  1. The color of the predicted object and the object in the image
  2. The pooled region features and the corresponding feature to the image feature map
  3. The depth ordering of the predicted object and the object in the image

## Question 11
In [FCN][fcn], the final output of predicted the semantic masks has the same resolution as the image input
  1. True
  2. False 

## Question 12
In [FCN][fcn], the Deconvolution layer (or Transpose Convolution) with stride `s` results in an output of resolution
  1. `s` times the one of the input 
  2. `1/s` times the one of the input
  3. `+s` of the input resolution

## Question 13
Consider the following little net: `nn.Conv2d(3, 8, 3, stride=2) -> F.relu -> nn.Conv2d(8, 128, 3, stride=2) -> F.relu -> nn.ConvTranspose2d(128, 16, 3, stride=2)`. If the input to the net is `[B, 3, H, W]`. Then the output shape is
  1. `[B, 128, H, W]`
  2. `[B, 16, H/2, W/2]`
  3. `[B, 16, H/4, W/4]`
  4. `[B, 128, H/2, W/2]`
  5. `[B, 128, H/4, W/4]`
  6. `[B, 16, H, W]`

## Question 14
Your next project mandates that you automatically predict how many chairs there are in any unseen image. What do you do?
  1. You run a FCN model pretrained on COCO
  2. You run a Mask R-CNN model pretrained on COCO
  3. Neither of the above

## Question 15
Your next project mandates that you automatically predict how many buffalos there are in any unseen image. What do you do?
  1. You run a FCN model pretrained on COCO
  2. You run a Mask R-CNN model pretrained on COCO
  3. Neither of the above

[dropbox]: https://www.dropbox.com/request/RNMfnuysdDLzGu5oZJJF
[rcnn]: https://arxiv.org/abs/1311.2524
[fasterrcnn]: https://arxiv.org/abs/1506.01497
[maskrcnn]: https://arxiv.org/abs/1703.06870
[fcn]: https://arxiv.org/abs/1411.4038
[unet]: https://arxiv.org/abs/1505.04597

