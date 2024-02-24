# Clothing-Recognition-System
This is a simple clothing recognition system that classifies a clothing item into one of 10 classes by applying deep learning models. The 10 classes are belt, covered shoes, dress, high heels, pants, shirt, skirt, slippers, socks and spectacles. Two deep learning models are experimented, multilayer perceptron (MLP) and convolutional neural network (CNN).

# Data Description
There is a total of 6059 images. The number of images of each class is presented in the table below.
| Class Name | Number of Images| Image Sample|
|----------|----------|----------|
| Belt| 600|![belt](/Screenshots/belt_094.jpg?raw=true)|
| Dress| 600|![dress](/Screenshots/Dress_327.jpg?raw=true)|
| High_Heels| 600|![Heels](/Screenshots/heels_001.jpg?raw=true)|
| Pants| 612|![Pants](/Screenshots/pants_012.jpg?raw=true)|
| Shirt| 643|![Shirt](/Screenshots/shirt_057.jpg?raw=true)|
| Shoes| 600|![Shoes](/Screenshots/shoe_002.jpg?raw=true)|
| Skirt| 600|![Skirt](/Screenshots/Skirt_074.jpg?raw=true)|
| Slipper| 600|![Slipper](/Screenshots/slipper_032.jpeg?raw=true)|
| Socks| 604|![Socks](/Screenshots/socks_040.jpg?raw=true)|
| Spectacles| 600|![Spectacles](/Screenshots/specs_016.jpg?raw=true)|

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

# Methods
1. Multilayer Perceptrons (MLP)
- 4 hidden layers (300 nuerons, 300 neurons, 100 neurons, and 10 neurons respectively)
- Activation function for first 3 hidden layers are 'relu', meanwhile the activation funciton for the last hidden layer is 'softmax'
- Optimiser used is SGD

![code_2](/Screenshots/code_2.png?raw=true)
![MLP architecture](/Screenshots/arch_1.jpg?raw=true)

2. Convolutional Neural Network
- This model has 3 convolutional layers and 3 pooling layers
![code_3](/Screenshots/code_3.png?raw=true)
![CNN architecture](/Screenshots/arch_2.jpg?raw=true)

_Convolutional Layer 1_<br>
![conv_layer1](/Screenshots/conv_layer1.jpg?raw=true)<br>
The input image is `84 * 84 pixels`. The filter kernel is `7 * 7 pixels`. The 64 filter kernels will convolve with the input images with stride=1, and produce 64 `78 * 78 pixels` feature maps.
The output size of 1 feature map can be calculated as below,
Output size = [84 – 7]/1 + 1 = 78

_Pooling Layer 1_<br>
![pool_layer1](/Screenshots/pool_layer1.jpg?raw=true)<br>
After the first convolutional layer, the feature maps are pooled with `2 * 2` max pool layer with stride=2, and produce 64 `39 * 39 pixels` feature maps.
Output size = [78 – 2]/2 + 1 = 39

_Convolutional Layer 2_<br>
![conv_layer2](/Screenshots/conv_layer2.jpg?raw=true)<br>
After the first pooling layer, the feature map is `39 * 39 pixels`. The filter kernel is `7 * 7 pixels`. The 128 filter kernels will convolve with the feature maps with stride=1, and produce 8192 `33 * 33 pixels` feature maps.
Output size = [39 – 7]/1 +1 = 33

_Pooling Layer 2_<br>
![pool_layer2](/Screenshots/pool_layer2.jpg?raw=true)<br>
After the second convolutional layer, the feature maps are pooled with `2 * 2` max pool layer with stride=2, and produce 8192 `16 * 16 pixels` feature maps.
Output size = [33 – 2]/2 + 1 = 16

_Convolutional Layer 3_<br>
![conv_layer3](/Screenshots/conv_layer3.jpg?raw=true)<br>
After the second pooling layer, the feature map is `16 * 16 pixels`. The filter kernel is `7 * 7 pixels`. The 128 filter kernels will convolve with the feature maps with stride=1, and produce 1048576 `10 * 10 pixels` feature maps.
Output size = [16 – 7]/1 +1 = 10

_Pooling Layer 3_<br>
![pool_layer3](/Screenshots/pool_layer3.jpg?raw=true)<br>
After the third convolutional layer, the feature maps are pooled with `2 * 2` max pool layer with stride=2, and produce 1048576 `5 * 5 pixels` feature maps.
Output size = [10 - 2]/2 + 1 = 5

# Result
MLP <br>
![MLP_result](/Screenshots/mlp_graph.png?raw=true)<br>
CNN <br>
![CNN_result](/Screenshots/cnn_graph.png?raw=true)<br>

# Authors
Joey Lim, Y.F.,Tan, J.C.,Tan, Z.X.,Ng, B.S.,Leong

# Others
This project is made for my `TML 2221 Machine Learning` subject. The original program of this assignment is modified and updated.