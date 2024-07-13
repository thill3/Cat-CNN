# Cat-CNN
Cat Picture CNN - Image Exploration

I'm embarking on a project to create a Convolutional Neural Network (CN) to label the thousands of pictures I have of my cats.

The code in this repository is some preliminary analysis to determine the pictures I have and their various sizes.

Some reading suggests that in most cases pictures for CNNs have the same dimensions (height and width) and number of channels (sets of color depths for the basic colors). This is because general practice in CNN architectures follows up the convolutions with fully-connected (dense) neural network processing layers. Because any given network can only have one set of dense layers it is the case that any CNN that includes those dense layers near the end of the network can accept only one size of input (any other size would require more or fewer training weights, and those would likely result in different values than in another size of dense layers).

This propblem can be dealt with in multiuple ways. I'm still learning, so I may discover more.
  1. The brute force approach is to, if the different sizes of inputs are known beforehand, is to create and train individual networks for each potential set of image dimensions and number of channels.
  2. Some crude options exist for adjusting all of the images to one size before feeding them into the network. The two that come most readily to mind are cropping or resizing the images to all have the same dimensions.
  3. A more technical option is to set up the convolution sections of the network architecture to output a consistent value regardless of the size of the input image. My understanding is that this is often a Global Average Pooling (or something similar) layer in the network that reduces the entire input down to a single pixel.

My reactions to these options are as follows:
  1. The preliminary image size analysis generated by this notebook suggests that I have 22 different sets of image dimensions in my training data (more may arise as I add photos to the training data or do more analysis). This preliminary analysis also shows that I have 35 distinct combinations of cat_name, height, and width. I may be able to handle coding this in a reasonable amount of time using dictionaries and looping constructions. The coding here could turn out rather complex.
  2. This option worries me. It necessitates the loss of image data, and this may render some of the pictures unable properly to describe a particular cat.
  3. This option still needs more research. It makes me nervous for reasons similar to why I am uncomfortable with number 2, yet I may be convinced when I've learned more.
