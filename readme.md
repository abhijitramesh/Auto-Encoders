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

## Learnable Upsampling
Since we are in the topic of Image Compression let us bring in convolutionl neural networks into the talk, they are remarkably well when they are used for classifying images. This is mainly because they are a combination of convolutional and maxpooling layers, the convolutional layers understand a feature of the image while the maxpooling layer does is it will decrease the dimentionality of the image. So if we consider this as out encorder for our decorder we need to increase the dimention of out image or do some kind of _unpooling_. One thig we can do is something called as nearest neibours which is let us take the example of a matrix which has elements 1,2,3,4 in dimention 2x2, so if we have to upsample this we just copy the values four times 1,1,1,1,2,2,2,2,3,3,3,3,4,4,4,4 in dimention 4x4 which means we have upsampled our image but the problem here is we would not have something which is exactly the first image and every time we do unpooling the loss increases compared to the original image so we use somthing known as Learnable Upsampling one example of this is Transpose Convolutions which insted of copying values have weights that can learn what the values of the nebouring pixel values would be.

If you like to know about the math and working behind transpose convolutional layers check [this](https://towardsdatascience.com/what-is-transposed-convolutional-layer-40e5e6e31c11) link from towards data-science.

## Convolutional Encoder

Let us try and encode our data using a convolutional encorder and maxpooling in between and de-code the same using a transpose convolutional layer.

[click here](https://github.com/abhijitramesh/Auto-Encoders/blob/master/Convolutional_Autoencoder_Exercise.ipynb)

## Denoicing Encoder
Since we see that convolutional encorders kind of removes the noise in the image we can actully modify its purpose to do the same, training the model with a noisy image and then using it to predict the image without the noise.

[click here](https://github.com/abhijitramesh/Auto-Encoders/blob/master/Denoising_Autoencoder.ipynb)
