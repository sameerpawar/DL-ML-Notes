Rnd = Q
Scratch = S
scratch2 = T
home = u


# Semantic segmentation task
1. Input is image and output is ``category for each pixel" for the image.
1. Does not differentiate instances of categories.

# Papers
1. Long, Shell

# Approaches

## Sliding window based
1. Take differnt crops and classify the central pixel of the crop
1. Computationally expensive, since it does not share weights and compute across different crops.

## Fully convolutional network
1. Giant stack of conv layers that operate on the input image
1. last layer output tensor Categories (hot encoding vector) X H X W, with classification loss of cross-entropy for each pixel, sum across image and batches.
1. Too complex since conv is done at full resolution at all layers


## Fully conv network with downsampling and upsampling

### Upsampling
1. nearest neighbor unpooling: repeat the samples in the unpooling region
1. bed of nails unpooling: zero pad the unpooling region
1. max unpooling: Each unpooling layer is associated with a max pooling layer. The location of the max element is memorized and used in the corresponding unpooling layer.
1. Learnable upsampling/Deconv/upconv/fractionally strided conv/backward strided conv 


# Miscellaneous ideas
1. Dialated conv is used to capture multi-scale contextual information.



