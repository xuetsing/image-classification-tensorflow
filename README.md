# image-classification-tensorflow  
A generic image classification program that uses Google's Machine Learning library, [Tensorflow](https://www.tensorflow.org/) and a pre-trained Deep Learning Convolutional Neural Network model called [Inception](https://research.googleblog.com/2016/03/train-your-own-image-classifier-with.html).

This model has been pre-trained for the [ImageNet](http://image-net.org/) Large Visual Recognition Challenge using the data from 2012, and it can differentiate between 1,000 different classes, like Dalmatian, dishwasher etc.
The program applies Transfer Learning to this existing model and re-trains it to classify a new set of images.


## Installation
Make sure you have [Python](https://www.python.org/) installed, then install [Tensorflow](https://www.tensorflow.org/install/) on your system, and clone this repo.


## Usage

### Prepare the image data sets
In order to start the transfer learning process, a folder named ``dataset`` needs to be created in the root of the project folder. This folder will contain the image data sets for all the subjects, for whom the classification is to be performed.

Create the ``dataset`` folder and add the images for all the data sets in the following manner:

```
|
---- /dataset
|    |
|    |
|    ---- /A
|    |    A1.jpg
|    |    A2.jpg
|    |    ...
|    |
|    |
|    ---- /B
|         B1.jpg
|         B2.jpg
|         ...
|
```
This enables classification of images between the ``A`` and ``B`` data sets.


### Initiate transfer learning
Go to the project directory and run:

```
$ bash run.sh  
```

This script installs the ``Inception`` model and initiates the re-training process for the specified image data sets.

Once the process is complete, it will return a training accuracy somewhere between ``85% - 100%``.

The ``training summaries``, ``trained graphs`` and ``trained labels`` will be saved in a folder named ``logs``.

### Classify objects

```
python classify.py image.jpg
```

Where ``image.jpg`` is the input file which is to be classified.

The classifier will output the predictions for each data set. A prediction score between ``0.8`` to ``1`` is considered to be optimal.



