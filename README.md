# Reference

### CNN

[EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks](https://arxiv.org/abs/1905.11946) --> In this paper, we systematically study model scaling and identify that carefully balancing network depth, width, and resolution can lead to better performance.

--> Related Work --> Reference

[MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications](https://arxiv.org/abs/1704.04861) --> We introduce two simple global hyperparameters that efficiently trade off between latency and accuracy.

#### input, conv_layer, output formula example, for the simplicity omit batch dimension
<img src="https://github.com/sandokim/Reference/blob/main/images/Conv_formula.JPG" width="80%">

## Computer Vision Trend

In many real world applications such as robotics, self-driving car and augmented reality, the recognition tasks need to be carried out in a timely fashion on a computationally limited platform.

### Convolution operation

a 1×1 convolution called a pointwise convolution.

## Model Compression

A different approach for obtaining small networks is shrinking, factorizing or compressing pretrained networks. Compression based on product quantization [36], hashing [2], and pruning, vector quantization and Huffman coding [5] have been proposed in the literature. Additionally various factorizations have been proposed to speed up pretrained networks [14, 20]. Another method for training small networks is distillation [9] which uses a larger network to teach a smaller network. (MobileNets paper)

##### Huffman coding?

<img src="https://github.com/sandokim/Reference/blob/main/images/huffman coding.JPG" width="80%">
