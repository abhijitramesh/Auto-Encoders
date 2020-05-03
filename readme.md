# Auto-Encoders

Auto-Encoders are Neural Networks that learns how to efficently encode a data and then also how to reconstruct this data back to something as similar as the original data.

If you recollect how [CNNs](https://github.com/abhijitramesh/cnn-under-the-hood) work under the hood, you know the convolutinal layers take in an input image and then reduces its dimentionality so but at the same time it becomes more aware of the pattens in this netowork this aspect of the neural netowork is what we are going to use in Auto-Encoders, if we consider the process of how the convolutional layers as an encoder, we can reverse the process to make a decoder.