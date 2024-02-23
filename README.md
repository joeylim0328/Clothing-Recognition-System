# Clothing-Recognition-System
This is a simple clothing recognition system that classifies a clothing item into one of 10 classes by applying deep learning models. The 10 classes are belt, covered shoes, dress, high heels, pants, shirt, skirt, slippers, socks and spectacles. Two deep learning models are experimented, multilayer perceptron (MLP) and convolutional neural network (CNN).

# Data Description
There is a total of 6059 images. The number of images of each class is presented in the table below.
| Class Name | Number of Images| 
|----------|----------|
| Belt| 600|
| Dress| 600|
| High_Heels| 600|
| Pants| 612|
| Dress| 600|
| Shirt| 643|
| Shoes| 600|
| Skirt| 600|
| Slipper| 600|
| Socks| 604|
| Spectacles| 600|

The train_test_split funciton is used to split the data into training set and testing set. After that, part of the training set i used as the validation set.
For the Multilayer Perceptron model,
- Training samples = 4907
- Validation samples = 546
- Testing samples = 606

For the CNN model,
- Training samples = 5000
- Validation samples = 453
- Testing samples = 606

Before splitting the datasets, all images are resized to `84*84 pixels`. Numbers (1 to 10) are used to represent each class. For example, 0 for belt and 1 for shirt. 
![code_1](/Screenshots/code_1.png?raw=true)

# Authors
Joey Lim, Y.F.,Tan, J.C.,Tan, Z.X.,Ng, B.S.,Leong