# Instructions
Please upload a txt file in the form of `firstname_lastname.txt`. Each line will have your answer to the corresponding question, e.g. `Q1: 1`. Note that there can be multiple correct answers per question, in which case separate your answers with a comma, e.g. `Q1: 1, 2, 3`. Example file:
```
Q1: 1
Q2: 1, 2
Q3: 3, 4
...
```
Upload your answers to this [dropbox link][dropbox] by Thursday, April 30, EOD. 

# Test
### Question 1
The [Two-Stream CNN][twostream] work trained two separate CNNs, one operating on RGB frames and the other operating on
  1. Edges
  2. Optical flow
  3. Depth maps

### Question 2
The [Two-Stream CNN][twostream] paper showed that CNNs with single frame inputs are better than inputs of multiple consecutive frames 
  1. True
  2. False

### Question 3
The [Two-Stream CNN][twostream] paper tackles the task of action recognition, which involves
  1. Predicting an action for the whole video
  2. Predicting an action and its duration in time for a test video
  3. Predicting an action and detecting the human performing it in a video

### Question 4
The [Long-Term recurent CNN][lstm] paper tackles the tasks of
  1. Action recognition
  2. Object detection
  3. Captioning

### Question 5
The [Long-Term recurent CNN][lstm] paper trains its memory layers (LSTMs) for infinitely long video sequences
  1. True
  2. False

### Question 6
The [Slow-Fast][slowfast] paper consists of two parallel networks operating on 
  1. different image resolutions
  2. images and optical flow 
  3. video streams of different frame rates

### Question 7
The [Slow-Fast][slowfast] paper consists of CNNs with 3D convolutions
  1. True
  2. False

### Question 8
The input to the slow-fast streams consists of `B` batches of `T` consecutive video frames stacked to have shape
  1. `[B, T, 3, H, W]`
  2. `[B, 3 * T, H, W]`

### Question 9
In the [Slow-Fast][slowfast] paper, the networks are initialized from ImageNet pretrained weights
  1. True
  2. False

### Question 10
How does the [Slow-Fast][slowfast] paper perform fusion?
  1. From the Slow to the Fast stream, after the last residual stage
  2. From the Slow to the Fast stream, after every residual stage
  3. From the Fast to the Slow stream, after the last residual stage
  4. From the Fast to the Slow stream, after every residual stage

### Question 11
In the [I3D][i3d] paper, when training two-stream models on Kinetics dataset, which stream could benefit from the ImageNet pretraining?
  1. RGB stream
  2. Flow stream
  3. Both of the above streams
  4. None

### Question 12
In SlowFast, which of the following lateral connections for fusion obtains the best performance on Kinetics-400?
  1. Time-to-channel by element-wise summation
  2. Time-to-channel by concatenation
  3. Time-strided sampling
  4. Time-strided convolution

### Question 13
How is testing for comparing against the state-of-the-art methods in the [SlowFast][slowfast] paper performed:
  1. A video is cut into spatial and temporal clips that are individually processed and combined for prediction
  2. A video is cut into temporal clips that are individually processed and combined  for prediction
  3. A video is cut into spatial clips and that are individually processed and combined for prediction
  4. A video is processed in full duration using fully convolutional spatio-temporal processing for prediction

### Question 14
What is the technique to expand filters and pooling kernels of very deep image classification ConvNets into 3D, making it possible to learn seamless spatio-temporal feature extractors from video while leveraging successful ImageNet architecture designs and even their parameters:
  1. Inception
  2. Inflation
  3. Ensemble 
  4. Expand

### Question 15
What is the correct result when expanding a learnable scalar `torch.tensor([1])` to `3x1x1` with temporal dimension of `T=3`:
  1. `[1, 1, 1]`
  2. `[3, 3, 3]`
  3. `[1, 3, 1]`
  4. `[1 / 3, 1 / 3, 1 / 3]`

[dropbox]: https://www.dropbox.com/request/blyoN5hoNIDyK8HB5Ylp
[twostream]: https://arxiv.org/abs/1406.2199
[lstm]: https://arxiv.org/abs/1411.4389
[i3d]: https://arxiv.org/abs/1705.07750
[slowfast]: https://arxiv.org/abs/1812.03982



