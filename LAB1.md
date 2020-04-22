# Lab 1: Detectron2

In this practical session, we will familiarize ourselves with [Detectron2][d2], an object detection library written in PyTorch. Detectron2 implements state-of-the-art object detection models, like the ones you learned about in Lecture 1. It also provides a model zoo, a library of pre-trained models trained on a variety of datasets. This allows users to download models and apply them to their own dataset. 

We will be going through the Detectron2 [tutorials][d2tut] which offer a step-by-step exploration of Detectron2.

## Prerequisites
* [Colab][colab]: Throughout this lab we will use colab notebooks to run detectron2 models. This is essential as the models will run much faster on the colab GPU compared to your personal laptops (which only have CPU). 

## Instructions
Please upload your short report in the form of `firstname_lastname.pdf` to this [dropbox link][dropbox] by Sunday, May 3, EOD. 

## Part A: Install Detectron2 

You are asked to install Detectron2. The [install tutorial][d2inst] offers a step-by-step installation guidance. This should be relatively painless but if issues emerge myself and TAs are here to help!

## Part B: Run a pre-trained model for instance segmentation

You are asked to load a pre-trained model and use it on a set of images of your liking. This [example tutorial][d2run] in Detectron2 shows you how it's done; it loads a [Mark R-CNN][maskrcnn] model with a ResNet50 backbone pre-trained on the [COCO][coco] dataset for the task of instance segmentation and object detection and runs it on an image. COCO is a dataset of more than 300k images annoated with bounding boxes and instance masks of 80 object categories. 

Pick a set of images from your personal collection (you can take a few of pictures of your apartment, or images that are on your phone or anywhere on the internet) and run the pre-trained model on them. Visualize the predictions.

## Part C: Run a pre-trained model for pose estimation 

In Part B, you loaded a model for instance segmentatinon, ran it through a few images from your collection, and visualized the predictions. In Part C, you are asked to repeat this process but now for the task of human pose estimation.

For this part, the [Detectron2 Model Zoo][d2zoo] will prove to be very helpful. Again, take some images from your personal collection, run the model and visualize the predictions. 

## Part D: Report

We want you to summarize your findings and exploration with Detectron2 on a short report. 

__For each task__, namely instance segmentation (Part B) and human pose estimation (Part C), provide the following
* model architecture: This should include the method, the backbone architecture and the dataset it was pretrained on.
* examples: Visualizations of two examples of __correct__ predictions, and two examples of __false__ predictions. In the caption of the figures, say why the examples are correct or false.
* observations: From running the models on your images, you must have observed some interesting model behavior (remember these models do not achieve 100% accuracy!). Provide some interesting example cases and describe why the behavior of the model is interesting or unexpected. 
* error modes: In a short paragraph, describe the error modes that you have discovered when running the models. Have you seen a pattern of mistakes that keep occuring even on different images? Do you have any insight on what is causing the errors/confusions? 

The length of the report should not exceed 2 pages.


[dropbox]: https://www.dropbox.com/request/bnCx3ZJ6WP72m1rpBvSU
[d2]: https://github.com/facebookresearch/detectron2
[d2tut]: https://colab.research.google.com/drive/16jcaJoc6bCFAQ96jDe2HwtXj7BMD_-m5
[d2inst]: https://colab.research.google.com/drive/16jcaJoc6bCFAQ96jDe2HwtXj7BMD_-m5#scrollTo=vM54r6jlKTII
[d2run]: https://colab.research.google.com/drive/16jcaJoc6bCFAQ96jDe2HwtXj7BMD_-m5#scrollTo=Vk4gID50K03a
[coco]: http://cocodataset.org/#home
[d2zoo]: https://github.com/facebookresearch/detectron2/blob/master/MODEL_ZOO.md
[colab]: https://colab.research.google.com/