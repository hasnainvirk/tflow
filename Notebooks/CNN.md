# Convolutional Neural Nets

Mnist data sets are cool for a concept learning tool but they pose constraints that will render your model trained on them, useless. Life wouldn't be that simple, would it ?

## Limitations of DNNs
For example, each image in mnist data set is 28x28, greyscale and perfectly centered. Reality would be hell lot different. Size could be just about anything, coulours could be anything, image might be centered, scaled, zoomed or what not. 

![mnistFashionExample](img/mnist_fashion_example.png)

Our mnist trained DNN will fail miserably if we show it something like this:

![boot](img/boot.jpg)

Basically, we cannot rely on symmetry, order and predictability of mnist data set in the real world scenarios. So we have to come up with something smarter than this.

## Big question ?

So the question is what we can do about it. Maybe we should ask ourselves, what is a boot if we are classifying boots ?
What makes a boot, 'boot' ?
Ofcourse a computer does not see what a human sees. But can it somehow differentiate among some naked or hidden features of the object which would help to classify the object correctly ?

And the answer is, yes, use convolutional NNs dummy.

## Main idea

A convolution is basically a filter that when applied, processes the image and extract common features.  

Here is how it's done:

- Scan every pixel in the image and multiply it's neighbours with corresponding weights of the filter. 
- Add all the results of multiplications. 
- Assign this new value to the pixel.

For example here is an example of 3x3 convolution:

![convolution](img/convolution.png)

Note that there can be manny such filters defined in the network and the application of a filter results in a new image. So we should be mindful of the image size. We should use techniques to compress the image without losing feature information.

One such technique is called Pooling. There are many types of pooling. Here we can discuss about MAX Pooling which simply says:

- Divide the pixels into blocks of a given size 
- Find the maximum value of the block and use extract that out
- Reconstruct image with the given maxed out values

For example:

![pooling](img/pooling.png)

