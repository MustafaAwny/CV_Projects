# Project : Facial Keypoint Detection

## Description
In this project, we build a facial keypoint detection system 
that takes in any image with faces, and predicts the location
of 68 distinguishing keypoints on each face.

Facial keypoints include points around the eyes, nose, and mouth on a face and are used in many applications. These applications include: facial tracking, facial pose recognition, facial filters, and emotion recognition. 

Some examples of these keypoints are pictured below.

![Center Image](images-readme/sample.PNG)

## Files

* `Notebook 1`: Loading and visualizing the facial keypoint data
* `Notebook 2`: Defining and Training a Convolutional Neural Network (CNN) to predict facial keypoints
* `Notebook 3`: Facial keypoint detection using haar cascades and the trained CNN
* `Notebook 4`: Fun filters and keypoints uses
* `models.py`: Define the neural network architectures 
* `data_load.py`: Data transforms classes

## Data Augmentation

A common strategy for training neural networks is to introduce randomness in the input data itself. For example, you can randomly rotate, mirror, scale, and/or crop your images during training. This will help your network generalize as it's seeing the same images but in different locations, with different sizes, in different orientations, etc.


### Train dataset
With that in mind, here is how the pipeline to transform the train dataset looks like:
* Rescale the image to (250, 250) for the width and height
* Random crop the image to (227, 227)
* Normalize : convert color image to grayscale and normalize the color range to [0, 1] as well as scale keypoints around 0 with a range of [-1, 1]
* Convert to tensor

### Test dataset
 * Rescale the image to (227, 227) for the width and height
 *  Normalize : convert color image to grayscale and normalize the color range to [0, 1] as well as scale keypoints around 0 with a range of [-1, 1]
* Convert to tensor

## Model architecture
I tried **Naimish** architecture from the paper 
`Facial Key Points Detection using Deep Convolutional Neural Network, N. Agarwal et al. (2016)`
Link: https://arxiv.org/pdf/1710.00977.pdf

And **AlexNet**. `ImageNet Classification with Deep Convolutional Neural Networks, A. Krizhevsky et al. (2012)`
Link: https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf
