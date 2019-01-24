# **Traffic Sign Recognition** 

## Writeup

## Pls refer to notebook Traffic_Sign_Classifier-V5

## The rubric of this project has 4 parts with (1,2,4,3) subparts respectively and I have written ->                  R < Part > < Subpart >       to show you all the parts in the jupyter notebook (ex: R21 is part 2 subpart 1 i.e. dataset summary in data exploration)

# R1

---

**Build a Traffic Sign Recognition Project**

The goals / steps of this project are the following:
* Load the data set 
* Visualize the data set
* Design, train and test a model architecture
* Use the model to make predictions on new images
* Analyze the softmax probabilities of the new images
* Summarize the results with a written report


[//]: # (Image References)


[image1]: ./writeupimgs/traingraph.png "training x is classes, y is frequency"

[image2]: ./writeupimgs/testgraph.png "testing x is classes, y is frequency"

[image3]: ./writeupimgs/validgraph.png "validation x is classes, y is frequency"



### Data Set Summary & Exploration

#### 1. Provide a basic summary of the data set. In the code, the analysis should be done using python, numpy and/or pandas methods rather than hardcoding results manually.

I used the pandas and numpy library to calculate summary statistics of the traffic
signs data set:

* The size of training set is 34799 
* The size of the validation set is 4410
* The size of test set is 12630
* The shape of a traffic sign image is 32*32*3
* The number of unique classes/labels in the data set is 43

#### 2. Include an exploratory visualization of the dataset.

Here is an exploratory visualization of the data set. It is a bar chart.

![alt text][image1]

![alt text][image2]

![alt text][image3]

### Design and Test a Model Architecture


Normalised X_train by (pixel-128)/128

I had problems initially as pixels were uint8. Then I converted them to float and normalised it.



My final model consisted of the following layers:


*Layer*						*Description*

Input						32x32x3 image

Convolution 5x5				2x2 stride, valid padding, outputs 28x28x6
RELU	
Max pooling					2x2 stride, outputs 14x14x6

Convolution 5x5				2x2 stride, valid padding, outputs 10x10x16
RELU	
Max pooling					2x2 stride, outputs 5x5x16

Flatten 					 output 400

Fully connected				input 400, output 120
Dropout
RELU	

Fully connected				input 120, output 84
Dropout
RELU	

Fully connected				input 84, output 43




To train the model, I used :
    epochs=20
    batch size=128
    learning rate=0.001
    optimizer=Adam



My final model results were:
* training set accuracy of 0.993
* validation set accuracy of 0.929 
* test set accuracy of 0.921



A well known architecture was chosen:

* I chose the LeNet architecture
* I made modification like adding dropout layers(which increased accuracy)



### Test a Model on New Images


Here are five German traffic signs that I found on the web:

They can be viewed in folder WebImages and they are resized to 32*32*3 which can be viewed in WebImages2.

The results of the prediction can be viewed in the notebook (do ctrl+f to find):
   
   Look for R42 


The code for making predictions on my final model is located in the Ipython notebook.

   Look for R43

