# Auto-Encoders

Auto-Encoders are Neural Networks that learns how to efficently encode a data and then also how to reconstruct this data back to something as similar as the original data.

If you recollect how [CNNs](https://github.com/abhijitramesh/cnn-under-the-hood) work under the hood, you know the convolutinal layers take in an input image and then reduces its dimentionality so but at the same time it becomes more aware of the pattens in this netowork this aspect of the neural netowork is what we are going to use in Auto-Encoders, if we consider the process of how the convolutional layers as an encoder, we can reverse the process to make a decoder.

## Simple Encoder 

Let us first create a Simple Encoder for this we are going to take the MNIST dataset which has Images of dimention 28*28*1 where the last value represents the dimention of the colour channel which is grayscale, 

* then we are going to flatten this images into a vector of 784.
#### Encoder
* We will pass this vector to a linear layer which gives an output to the dimention we specify.
* This linear layer is passed through a ReLU activation funtion.
#### Decorder
* Our next layer would have a linear layer which would inverse the change in the first linear layer it takes in an input of the dimention we specify and output a vector of dimention 784.
* We will apply sigmoid funtion to this layer.

[Click here](https://github.com/abhijitramesh/Auto-Encoders/blob/master/Simple_Autoencoder.ipynb) to checkout the notebook on Simple Autoencoder.
