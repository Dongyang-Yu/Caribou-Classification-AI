# Smart Software Caribou Classification Tool

Developed for our client Katie Orndahl as a NAU Computer Science Capstone Project. This project is being created in order to make sorting through tens of thousands of videos easier for our client. The videos in question are shot using camera collars that have been applied to Alaskan/Canadia caribou. Currently, these videos are only being analyzed by tens of volunteers, but there are +90,000 videos currently with more on the way, meaning that tens of volunteers will not be enough. 

Our client has issued us this project to make the work of sorting videos both easier on her and her time, as well as the volunteers. Our job is to create a Smart Software Caribou Classification Tool, or as we decided a Convolutional Nerual Network (CNN), in order to sort videos based on their quality of view. This file will discuss in broad terms how our team has desided to design and create this model. If you are looking for a more indepth view of our process, please visit (https://www.cefns.nau.edu/capstone/projects/CS/2020/Caribou-Cams-S20/).

Below we have listed the different stages of our model. As of December 11, 2019, our team finished Stage One of the model. Currently, we are working on gettig Stage Two to work and plan to have it mostly working by February 28th.

### stage one
This is a CNN project that was built with the hopes of it being able to successfully differentiate between four different animals just based on pictures. These animals are: cat, dog, koala, and duck. The CNN was built using Keras with Tensorflow and contains two main files built by us: testing.py and executeTest.py. This CNN was developed in this repository and thus the different version have been saved here, but if you wish to only see the final version of this stage, please go to (https://github.com/Sam-the-Unwise/Four-category-CNN).

### stage two -- where we are now
The CNN is then upgraded in order to work with video instead of pictures. Our team has done this by separating the videos by frames, running each frame against the AI, and then averaging the results from all the frames in order to get a result of the video. This is likewise done when training the model, which will break down the video into frames and use each frame to train the model.

### stage three -- coming soon
Our group is then going to upgrade the CNN in order to successfully be able to determine between four different types of video qualities: "Excellent", "Good", "Fair/Poor", and "Extremely Obstructed". In this stage, we will work with the model in order to develop the most accurate output we possibly can.

## Getting Started

<i> Please note, most of this code was downloaded from or created by the Python library Keras and we are not claiming any of it to be our own work. The only things that were created by us are the testing.py and executeTest.py files </i>

The following instructions are meant to help you understand the code in broad detail. For a more detailed explanation, please see the file notes_on_training_CNN.py, which has extensive comments that explain the code. Also please sea

### Prerequisites

```
python
```
Install
```
pip install  tensorflow, Keras, numpy, os, math, random
```
<i> please note that for our model we had to download specific things that needed to be added to the Keras library but as many of these were different for our individual machines, I have chosen to leave them off </i>

# The below files can be found beneath the folder "source" -- A copy of these descriptions has been made in this files own README for convenience

### deleteVideoFrames.py

A script that will go through the folders our video frames have been saved in and delete them once training the model has been finished


### organizingTrainAndValidation.py

This script is only used to separate data that has already been classified into the train and validation datasets. It will sort 20% of the data into the validation set and 80% of the data into the training set.


### runCNN.py

This is our <b>main</b> script that will run all the code from other files


### splitVideosIntoFrames.py

This script contains all the necessary methods to split our videos into frames. This script is specifically used for the <i> training </i> and <i> validation </i> data as we need to save these frames for a longer period of time than the testing frames. For splitting testing videos into frames, please reference <i> testingVideosToFrames.py </i>. 

This script will split the videos into the desired amount of frames and save them each to the according folder (for example, a frame from '../dataset/training_set/Excellent' will be saved to '../dataset/training_set_frames/Excellent'). These frames will then be deleted by <i>deleteVideoFrames.py</i>


### testingCNN.py

This script contains all the necessary methods for testing our AI against desired photoes. The program accesses the folder 'Dataset/single_prediction' and tests each of the pictures in the folder against the saved model. The program will then output a prediction of what it thinks the picture is of (between the choices of cat, dog, duck, and koala).


### testingVideosToFrames.py

This script contains all the methods necessary to split a single video into frames, which are thus stored in an array. This is used by the <i>testing.py</i> script in order to analyze each from of the video individually. The script will also delete the array once the analyzation has been finished. 

<i> Note: the analyzation takes place in testing.py </i>


### trainingCNN.py

This script contains all the methods necessary for training the AI. This script creates the CNN model and then trains the CNN based on the images that have been placed in the 'Dataset/training' folder. While training the CNN, the program will also test the CNN for accuracy using images from the 'Dataset/test' folder, which will allow the program to display an accuracy of how well the model is predicting. The data of the model is then saved underneath the folder 'models' in the files 'model.h5' and 'weights.h5'.

<i> Note that with our current set up of 25 epochs, 3000 training batch size, and 100 test batch size, the model was roughly at 78% accuracy. </i>


### variables.py

A helpful script that contains all the common variables used throughout the other program files in this repository. If anyone is to change the names of their folder locations, they should change them in this script and only this script.



# Authors

* **Samantha Muellner** - *Team Lead* - [GitHub](https://github.com/Sam-the-Unwise)

* **Keenan Swanson** - *Customer Communicator* - [GitHub](https://github.com/Keenanks)

* **Dongyang Yu** - *Recorder* - [Github](https://github.com/Dongyang-Yu)

* **Shuyue Qiao** - *Architect* - [Github](https://github.com/SHUYUEQIAO)

## Acknowledgments

* **Katie Orndah, Ecoinformatics PhD. Student** - *Client*
