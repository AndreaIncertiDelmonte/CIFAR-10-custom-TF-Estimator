# CIFAR-10 custom TF Estimator
[CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html) classifier based on [TensorFlow Estimator API](https://www.tensorflow.org/programmers_guide/estimators) and [TFRecords](https://www.tensorflow.org/programmers_guide/datasets#consuming_tfrecord_data).
<br/>The project contains two CNN models:
- [LeNet](http://yann.lecun.com/exdb/lenet/) from Prof. Y. LeCun
- A deeper version of LeNet with more convolutional filters and local response normalization. 

# Installation
Clone the GitHub repository and install dependencies through pip
```
$ git clone https://github.com/AndreaIncertiDelmonte/CIFAR-10-custom-TF-Estimator.git
$ cd CIFAR-10-custom-TF-Estimator
$ pip install -r requirements.txt
```

## Project dependencies
- Python 2.7
- TensorFlow 1.6
- Jupyter notebooks
- Numpy
- cPickle
- matplotlib

# Usage
The project consists into 3 Jupyter notebooks.
```
$ cd CIFAR-10-custom-TF-Estimator
$ jupiter notebook
```

## 01 data inspection and conversion pipeline
Main features:
- Download of [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html) dataset
- Load data with cPickle
- Print some records
- Create train, eval and test sets
- Check for the imbalanced dataset problem
- TFRecords creation.

## 02 train and eval pipeline
Main features:
- Input pipeline definition
- LeNet model definition
- DeepLeNet model definition
- Custom estimator definition
- Model training and evaluation on eval set
- Model evaluation on test set.

### Run configurations
Model selection:
```
# LeNet
FLAGS.model_name = FLAGS.lenet_model_name
# DeepLeNet
FLAGS.model_name = FLAGS.deep_lenet_model_name
```

## 03 inference pipeline
Main features:
- Load CIFAR-10 test data
- Load exported predictor
- Apply inference on test data.

### Run configurations
Model selection:
```
#LeNet
TRAINED_MODEL_EXPORT_DIR = “./trained_models/lenet/export/exported-lenet”
#DeepLeNet 
TRAINED_MODEL_EXPORT_DIR = "./trained_models/deep-lenet/export/exported-deep-lenet"
```

# License
The code is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).