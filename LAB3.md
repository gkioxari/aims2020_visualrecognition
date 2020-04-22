# Lab 3: Building an Object Tracker 

For the thirt lab session, we will build a simple object tracker. Our tracker will detect objects on all frames of a video and then will link the predictions from one frame to the next.

In our first lab, we learned how to download a pretrained model from the D2 model zoo and run it on images. The predictions from the D2 model correspond to the input frame, and are agnostic to any links to predictions on other frames of the same video. In this task, we will work with the predictions of a D2 model, like the one you used in the first lab assignment, and we will explore algorithms to link these predictions across time frames.

## Prerequisites
* [Colab][colab]: Throughout this lab we will use colab notebooks to train detectron2 models. This is essential as the models will train much faster on the colab GPU compared to your personal laptops (which only have CPU). 

## Instructions
Please upload your short report `firstname_lastname.pdf` and your notebook `firstname_lastname.ipynb` to this [dropbox link][dropbox] by Sunday, May 3, EOD. 

## Part A: Detecting Objects in Frames

Download a small video clip of 41 frames from: https://github.com/gkioxari/aims2020_visualrecognition/releases/download/v1.0/videoclip.zip

Using the Colab notebook from the first lab assignment, you should be able to run and store the predictions for all frames in the video clip. Visualize the predictions from a random set of frames to make sure things look correct.

## Part B: Tracking Objects in Pairs of Frames

Now let's see how we can track objects in time based on the D2 predictions on each frame of the video. 

Assume P = {p<sub>1</sub>, p<sub>2</sub>, ..., p<sub>N</sub>} is the set of N predictions in frame I<sub>t</sub> and Q = {q<sub>1</sub>, q<sub>2</sub>, ..., q<sub>M</sub>} is the set of M predictions in frame I<sub>t+1</sub> (note that N does not have to be equal to M). These are the predictions you got from Part A. 

Let's define the matching score between p<sub>i</sub> in P and q<sub>j</sub> in Q to be `m(i, j)`. 

Potential `m(i, j)` functions can be 
```
m(i, j) = (category(i) == category(j))
```
which links two predictions if they belong to the same object categery, or 
```
m(i, j) = (category(i) == category(j)) * box_overlap(i, j)
```
which links two predictions if they belong to the same object category AND if their bounding box overlap is high. 

For each p<sub>i</sub> in P, the best match j* in Q can be found by
```
j* = argmax_j m(i, j)
```

Implement this pairwise tracker for consecutive pairs of frames in the video clip and visualize the pairs of predictions which were linked based on your linking algorithm and your linking function `m(i, j)`. You can show multiple pairwise tracks for the same two consecutive frames by colorcoding your predicted tracks, e.g. track1 with red, track2 with blue, etc.

## Part C: Tracking Objects in Videos

Part B produced pairs of objects linked between two consecutive frames (`dt=1`). If we want to predict tracks for longer horizons (`dt>1`) one could consecutively apply Part B to frames `(0, 1) -> (1, 2) -> (2, 3) -> (3, 4) -> ...` etc.

Extend Part B to perform pairwise links for a time horizon of 10 frames. Visualize examples of your 10-frame trackes by visualizing them on their corresponding frames. To visualize many tracks for the same set of 10 frames, you can colorcode the tracks, e.g. track1 is shown with red, track2 with blue etc. You might have to write your own visualizer for this.

## Part D: Report

We want you to summarize your findings with a short report. We ask the following:

* visualizations 2-frame tracks (Part B): Pick pairs of consecutive frames, one pair from the start, one pair from the middle and one pair from the end of the video. Visualize the pairwise tracks as computed in Part B for all predictions on the frames. Use colorcoding to indicate the two predictions that correspond to the same track. What do you observe?
* visualizations of 10-frame tracks (Part C): Pick a 10-frame clip from the video. Visualize the 10-frame tracks as computed in Part C. Use colorcoding to indicate the predictions belonding to the same track. What do you observe?

Note that we your notebook included in your submitted file should allow us to upload any 10 frames and get the corresponding tracks similar to what you show in your report.

[dropbox]: https://www.dropbox.com/request/jqSY2pQFqodIUCR9RPOZ
[d2]: https://github.com/facebookresearch/detectron2
[video]: https://github.com/gkioxari/aims2020_visualrecognition/releases/download/v1.0/videoclip.zip
[coco]: http://cocodataset.org/#home
[colab]: https://colab.research.google.com/