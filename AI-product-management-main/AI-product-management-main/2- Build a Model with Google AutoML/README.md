#  Project: Build a Model with Google AutoML

## Table of Contents 

- [Overview](#overview)
- [The Data](#data)
- [The Four Parts of the Project](#parts)
- [Project Structure](#structure)
- [Notes](#notes)
- [References](#references)

## Overview  <a name="overview"/>

In the [previous project](https://github.com/ErkanHatipoglu/AI-Product-Manager-Nanodegree-Program/tree/main/1-%20Create%20a%20Medical%20Image%20Annotation%20Job), We have created the instructions needed to build a labeled dataset that distinguishes between healthy and pneumonia x-ray images and filled the project proposal document. 

This dataset would later be used to build a product that helps doctors quickly identify cases of **pneumonia in children**. The goals of this product are to:

- Help flag serious cases,
- Quickly identify healthy cases,
- And, generally, act as a diagnostic aid for doctors.

In this project, we are going to take the next step and build the classification model that would serve as the backbone of this product. For this task, we will use [Google AutoML](https://cloud.google.com/automl/). To see how the training data impact the models, we will build models with 4 variants of the dataset.

## The Data  <a name="data"/>

We'll be using the same Kaggle [Chest x-ray dataset](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia) that we used in the [previous project](https://github.com/ErkanHatipoglu/AI-Product-Manager-Nanodegree-Program/tree/main/1-%20Create%20a%20Medical%20Image%20Annotation%20Job). We will use the original labels supplied with the data on [Kaggle](https://www.kaggle.com).

## The Four Parts of the Project <a name="parts"/>

We will train four different models using four variants of the [pneumonia dataset](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia). Recall that the dataset contains childrens' chest x-ray images and that they are classified into two classes, "normal" and "pneumonia". The following sections describe the steps we must take to create each model.

### Create a binary classifier to detect pneumonia using chest x-rays

We'll start by training a model simply using 100 images from the **'normal'** class and 100 images from the **'pneumoni'** class. We will evaluate the following:

- **Train/test split:** How much data is used for training and how much is used for testing?
- **Confusion matrix:** What do each of the cells in the confusion matrix describe?
- **Precision & recall:** What do these measure and how are they calculated?

### Create an unbalanced binary classifier

Next, we will use 100 images from the **'normal'** class, and add 200 more **'pneumonia'** class images. At this moment, the total count of images must be:

- **'normal'** class = 100
- **'pneumonia'** class = 300

The model will be trained on very unbalanced classes; this will show what happens when the number of images in different classes is very different. We will evaluate:

- **Confusion matrix:** What does the confusion matrix tell you about unbalanced data?
- **Precision & recall:** How are precision and recall affected?
- **Unbalanced classes:** How do unbalanced classes impact a machine learning model?

### Create a binary classifier with dirty data

In this iteration, we will start with the original dataset of 100 **normal** and 100 **pneumonia** images. Then switch the labels of 30 images in each class. After we've done this, 30% of the data are mislabeled. We will evaluate:

- **Confusion matrix:** How is the confusion matrix affected?
- **Precision & recall:** How are precision and recall affected?
- **Dirty data:** How do dirty data impact the model?

### Create a three-class model with the classes “normal”, “bacterial pneumonia”, and “viral pneumonia”

For the final model, note that the "pneumonia" images actually have two different classes: **bacterial** pneumonia and **viral** pneumonia. These labels are indicated in the image filenames. For this model, add 100 **normal** images, 100 **bacterial pneumonia** images, and 100 **viral pneumonia** images (for a total of 3 classes). We will evaluate:

- **Confusion matrix:** What does the 3-class confusion matrix look like?
- **Precision & recall:** What are the model's precision and recall? How are these measures calculated?
- **More data:** Can you continue to add data to each class (while keeping the data balanced) and get the model to 85% precision and recall? How much data did you end up using?

After we have trained each model, we will answer questions about it in the ***AutoML Modeling Report***.

## Project Structure <a name="structure"/>

- *Build_a_model_project_files* directory is the root directory. 
- *images* folder is for example images, 
- *automl-modeling-report.docx* is the report document filled by me.
- *automl-modeling-report.pdf* is the pdf version of the final modeling report document.

## Notes <a name="notes"/>
- Most of the parts of this README are directly copied from the Udacity project instructions.

## References <a name="references"/>

- [AI Product Manager Program - Udacity](https://www.udacity.com/course/ai-product-manager-nanodegree--nd088)
- [Udacity AI Product Manager Program Review (Part II)](https://medium.com/geekculture/udacity-ai-product-manager-program-review-part-ii-b9fb55d0314e)
- [Create a Medical Image Annotation Job](https://github.com/ErkanHatipoglu/AI-Product-Manager-Nanodegree-Program/tree/main/1-%20Create%20a%20Medical%20Image%20Annotation%20Job)
- [Kaggle](https://www.kaggle.com)
- [Chest x-ray dataset](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)
- [What is the Difference Between Test and Validation Datasets?](https://machinelearningmastery.com/difference-test-validation-datasets/)
- [Multi-Class Metrics Made Simple, Part II: the F1-score](https://towardsdatascience.com/multi-class-metrics-made-simple-part-ii-the-f1-score-ebe8b2c2ca1)