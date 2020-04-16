# Lab 2: Training a D2 Model on a Custom Dataset

For the second lab session, we will explore [Detectron2](d2) in depth by preparing a custom dataset and training on it. 

The [Detectron2 tutorials](d2tut) offer an [example](d2new) on how to prepare and train on a custom dataset of balloons. 

## Prerequisites
* [Colab](colab): Throughout this lab we will use colab notebooks to train detectron2 models. This is essential as the models will train much faster on the colab GPU compared to your personal laptops (which only have CPU). 

## Instructions
Please upload your project in a zipped folder `firstname_lastname.zip`, which contains your short report `firstname_lastname.pdf` and your notebook `firstname_lastname.ipynb`, to this [dropbox link](dropbox) by Sunday midnight. 

## Part A: Data

We will use a dataset of nuts which has 3 classes: _date_, _fig_, and _hazelnut_, and which is annotated with instance masks (credit for the dataset to [@Tony607](https://github.com/Tony607)) 

### Download
Download the dataset from: https://github.com/gkioxari/aims2020_visualrecognition/releases/download/v1.0/nuts.zip

### Data Format
The data contains:
  * an `images` directory that has the images
  * a `train.json` file that contains the train annotations in COCO format
  * a `val.json` file that contains the val annotations in COCO format

### Data Preparation and Registration
Before training a model, we need to prepare and register the data. The training data should be registered as `nuts_train` and the val data as `nuts_val`. The metadata for both train and val should be in accordance with the following:
```
NUTS_CATEGORIES = [
    {"color": [0, 125, 92], "isthing": 1, "id": 1, "name": "date"},
    {"color": [119, 11, 32], "isthing": 1, "id": 2, "name": "fig"},
    {"color": [0, 0, 142], "isthing": 1, "id": 3, "name": "hazelnut"},
```

To verify the data loading is correct, visualize the annotations of randomly selected samples in the training set. 

## Part B: Model Initialization and Training Schedule

Now we proceed to training. We'll train a Mask R-CNN model, with a ResNet50 FPN backbone. We will initialize the model with two initialization schemes:
  * With an existing model pre-trained on the [COCO](coco) dataset, available in detectron2's model zoo. Note that the COCO dataset does not have the _date_, _fig_ and _hazelnut_ categories. We will call the model with this initialization scheme `COCOinit`.
  * With ImageNet weights. We will call the model with this initialization scheme `INinit`.

For ease of implementation, add a boolean flag `with_coco_init` which when set to `True` initializes with COCO pretrained weights, otherwise it uses ImageNet weights. This way you can switch between the initialization schemes by merely changing the flag.

For both models, namely `COCOinit` and `INinit`, you will train for 300 iterations, a start learning rate of 0.02, 2 images per batch, and 128 regions per batch.

Visualize the training curves for both models in tensorboard. 

## Part C: Inference and Evaluation of the Trained Model

Visualize predictions of both trained models, on the images of the `val` set. 

Evaluate the performance of both models using AP metric implemented in COCO API. 


## Part D: Report

We want you to summarize your findings with a short report. We ask the following:

* visualizations of the training annotations from Part A (2 images).
* training curves: Add the training curves as visualized by tensorboard for `COCOinit` and `INinit` side by side. What do you observe?
* visualizations of predictions: Visualize predictions on the val set and compare them side by side for the two models. What do you observe?
* evaluation: Add the evaluation results as returned by the COCO api for both models. Which model performs best? Can you briefly explain why that is the case?

The length of the report should not exceed 2 pages.

[d2]: https://github.com/facebookresearch/detectron2
[d2tut]: https://colab.research.google.com/drive/16jcaJoc6bCFAQ96jDe2HwtXj7BMD_-m5
[d2new]: https://colab.research.google.com/drive/16jcaJoc6bCFAQ96jDe2HwtXj7BMD_-m5#scrollTo=b2bjrfb2LDeo
[nuts]: https://github.com/gkioxari/aims2020_visualrecognition/releases/download/v1.0/nuts.zip
[coco]: http://cocodataset.org/#home
[colab]: https://colab.research.google.com/