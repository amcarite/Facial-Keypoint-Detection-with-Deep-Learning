# Facial Keypoint Detection 

## Colaborators: Alex Carite, Greg Rosen, Shehzad Shahbuddin, Oscar Linares


## Project Summary 
The objective of this project is to predict facial keypoints, using a set of labeled facial features dataset provided by the original Kaggle competition. The team expirimented with multiple models and archetctures in order to achieve the final accuracy of 95% and Mean Squared Error of 0.6. 

The project team used various transfer learning models, using Keras and TensorFlow, to leverage the pre-established weights that were trained with the imagenet dataset. The models were then future tuned with a much smaller learning rate to achieve a low loss

There are many applications for this type of model, including:
 - Biometrics and facial recognition
 - Facial tracking in video
 - Building block for facial expression analysis 

This repo contains the final development notebook, the trainging and test data, and the presentation slides that were used to present to our UC Berkeley Graduate program.


## The Data 
The training data is comprised of 7,049 black and white images with resolution of 96x96 pixels. Each image was designed to have 30 labels for 15 facial features, with one x label and one y label for each facial feature. Upon initial EDA, the team discoved a large amount of missing labels for more than half of the provided trainging data. See Figure 1 below. 

![Figure 1](https://github.com/[amcarite]/[facial_keypoint_detection]/blob/[main]/image.jpg?raw=true)

There were three approaches that were deployed to handle the large amount of missing labels. The first was to simply cleave any image from the dataset that did not include a fully labeled face (henceforth referred to as the 'noNA' dataset). The second and third approaches involved imputing these missing labels using k-nearest neighbors(KNN) and forward fill(ffill) techniques. As seen in later parts of the repo, while KNN and ffilll provided our data set with much more training examples, the more inacurate imputed labels led to a higher loss than the noNA training set across all models in which they were ran. 

## Setting a Baseline
