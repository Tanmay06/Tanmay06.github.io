---
layout: post
title: "Face recognition using neural networks."
subtitle: "A simple guide to developing face recognition program using HAAR feature-based cascade classifier for face detection and an Artificial Neural Network for face recognition."
background: '/img/posts/writings/face-recognition/face-recog-bg.jpg'
category: 'Writings'
---

> *All the code for this project can be found in this [repo](https://github.com/Tanmay06/face-recognition).*

It is pretty easy for human to recognise each person individually because we are able to understand and remember human facial features like eyes, nose, shape, e.t.c; but it is difficult for the machines as for them  the input, basically image or video frame, is a grid of random numbers arranged together. To make machines able to recognise faces we need to train them to understand the facial features of a person. Fundamentally, this is done by training machines to look for group of pixels which act as a facial feature and use them to understand the image. Here, we are using a HAAR cascade classifier to detect faces in the image and then feeding these faces to our Neural Network to recognise the person for whom our network is trained for.

## Steps Involved
  1. Generating the Data
  2. Training and Testing the Model
  3. Running the Model

## 1. Generating the Data

The reposistory contains the script *get_data.py* which can be used to generate data. I had used data consisting of around 5,000 face samples from 5 people where 4 of them were labeled negative and 1 was positive. Each sample in the dataset was a *21X21* grayscale image totalling to 441 pixels each. The program is built to work with these numbers, but can be easily tweaked according to the requirements.

While generating the data, the program expects that your current directory should have two label directories named positive and negative. It will ask for label and name(person's name whose face is being recorded), and will store the images in directory *cur_dir\label\name*. Once the required positive and negative data is generated, running *set_data.py* will generate *data_set.csv* with *mX442* table size. Where *m* is number of samples, combining positive and negative, 0-441 is pixel values for each sample and 442 is label associated with the sample.

## 2. Training the Model

The data from *data_set.csv* file is extracted by *train_model.py* script and used to train a three layer Artificial Neural Network. The neural network uses a 20 units hidden layer and the logistic function for activation of each unit. The l-bfgs , quasi-Newton family methods, solver is used to optimise weights in the network and the generated model is regularised by 0.3 lambda L2 regularisation.

![neural network](/img/posts/writings/face-recognition/NN.png)

The *train_model.py* along with training the model also tests the model and generates *learning curve* by leveraging *plot_learning_curve.py*. The curve plotting method in *plot_learning_curve.py* is provided by Scikit team and documented [here](https://scikit-learn.org/stable/auto_examples/model_selection/plot_learning_curve.html#sphx-glr-auto-examples-model-selection-plot-learning-curve-py).

![learning curve](/img/posts/writings/face-recognition/learning_curve.png)

From the above graph we can say that our classifier is not the best but performs good on our data and there is room for improvement by increasing our dataset. The train_model.py stores the classifier in *nn_clf.joblib* file for further use.

## 3. Running the Model

Using our classifier from *nn_clf.joblib* in *predict_face.py* script we can now recognise face from our video feed. The recognised face is marked by blue square and others are marked by red square.

![recognised 1](/img/posts/writings/face-recognition/capture_1.png)
![unrecognised 1](/img/posts/writings/face-recognition/capture_2.png)
![recognised 2](/img/posts/writings/face-recognition/capture_3.png)


As you can see in images 1st and 2nd, the program detects blue for positive and red for negative. In the 3rd the classifier is able to pick-out positive and negative classes together.
