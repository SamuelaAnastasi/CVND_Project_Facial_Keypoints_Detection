# CVND Project: Facial Keypoints Detection

This is the first project of the Udacity's Computer Vision Nanodegree. The project will be all about defining and training a convolutional neural network to perform facial keypoint detection, and using computer vision techniques to transform images of faces.

### 1. The Dataset

Facial keypoints mark important areas of the face: the eyes, corners of the mouth, the nose, etc. These keypoints are relevant for a variety of tasks, such as face filters, emotion recognition, pose recognition, and so on. In each training and test image, there is a single face and 68 keypoints, with coordinates (x, y), for that face. Here they are, numbered so that specific ranges of points match different portions of the face. The set of image data used has been
extracted from the YouTube Faces Dataset, which includes videos of people in YouTube videos.
These videos have been fed through some processing steps and turned into sets of image frames
containing one face and the associated keypoints. This set of image data has been
extracted from the YouTube Faces Dataset, which includes videos of people in YouTube videos.
These videos have been fed through some processing steps and turned into sets of image frames
containing one face and the associated keypoints.

### 2. CNN Architecture

CNN’s are defined by a few types of layers:
* Convolutional layers
* Maxpooling layers
* Fully-connected layers

In the second notebook and in models.py, we will:
1. Define a CNN with images as input and keypoints as output
2. Construct the transformed FaceKeypointsDataset, just as before
3. Train the CNN on the training data, tracking loss
4. See how the trained model performs on test data
5. If necessary, modify the CNN structure and model hyperparameters

### 3. Facial Keypoint Detection Pipeline
After the a neural network is trained, to detect facial keypoints, we can then apply it
to any image that includes faces. The neural network expects a Tensor of a certain size as input
and, so, to detect any face, we’ll first have to do some pre-processing.
1. Detect all the faces in an image using a face detector (we’ll be using a Haar Cascade detector
in this notebook.
2. Pre-process face images to grayscale and also rescale, normalize, and turn images into a
Tensor of the input size that the net expects.
3. Use the trained model to detect facial keypoints on the image.

### 4. Facial Keypoint Inference Sample
After each face has been appropriately converted into an input Tensor for the network to see as
input, we can apply the net to each face. The ouput should be the predicted the facial keypoints.
These keypoints will need to be "un-normalized" for display.

![Mona Lisa Facial Keypoints Detection](https://raw.githubusercontent.com/SamuelaAnastasi/CVND_Project_Facial_Keypoints_Detection/master/images/key_points_mona_lisa.jpg)

### 5. Facial Filters
Using the trained facial keypoint detector, we can do things like add filters to a person’s
face, automatically. We can play around with adding sunglasses or other funny elements to detected face’s in an image by using the keypoints detected around a person’s eyes, mouth, nose etc.

![Fun with Keypoints](https://raw.githubusercontent.com/SamuelaAnastasi/CVND_Project_Facial_Keypoints_Detection/master/images/fun_keypoints.jpg)
